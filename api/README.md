# API Security Documentation

## Chat API (`/api/chat`)

This API endpoint provides AI chat functionality for the career website using OpenAI's GPT models.

### Security Measures Implemented

#### 1. **Strict CORS Policy**
- Only allows requests from `hiddevanheijst.nl` and `www.hiddevanheijst.nl` in production
- Localhost allowed only when `NODE_ENV=development` or `VERCEL_ENV=development`
- Rejects requests without valid origin headers (prevents direct API calls via curl/Postman)
- Rejects requests from unauthorized origins with 403 Forbidden

#### 2. **Request Validation**
- Message length limited to 1000 characters (prevents token abuse)
- History limited to 20 messages maximum (prevents excessive context usage)
- Type validation for all inputs

#### 3. **Rate Limiting**
- OpenAI API configured with `max_tokens: 500` to limit response size
- History sliced to last 10 messages for context (reduces token usage)
- Vercel provides built-in DDoS protection and rate limiting

#### 4. **Environment Variables**
- `OPENAI_API_KEY` stored securely in Vercel environment variables
- Never committed to git (protected by `.gitignore`)
- Different keys can be used for preview vs production environments

### Cost Protection

**Estimated Costs** (with current limits):
- Max tokens per request: ~1500 tokens (500 response + ~1000 context)
- Model: gpt-4o-mini (~$0.15 per 1M tokens)
- **Cost per request: ~$0.0002**
- Even with 1000 requests/day: ~$0.20/day or $6/month

**Additional Protections:**
1. Monitor usage in [OpenAI Dashboard](https://platform.openai.com/usage)
2. Set up usage limits in OpenAI account settings
3. Enable email alerts for unusual usage patterns
4. Review Vercel Analytics for traffic spikes

### Setup Instructions

#### Local Development
1. Create `.env.local` file (never commit this):
   ```bash
   OPENAI_API_KEY=sk-your-key-here
   NODE_ENV=development
   ```

2. Test locally:
   ```bash
   vercel dev
   ```

#### Production Deployment
1. Add environment variable in Vercel Dashboard:
   - Go to Project Settings → Environment Variables
   - Add `OPENAI_API_KEY` with your production key
   - Mark as "Sensitive" to hide from logs
   - Select "Production" environment only

2. Deploy:
   ```bash
   git push origin main
   ```

### Monitoring & Alerts

**Recommended monitoring:**
1. **OpenAI Dashboard**: Track API usage and costs
2. **Vercel Analytics**: Monitor request patterns and origins
3. **Vercel Logs**: Check for rejected requests (403 errors)

**Set up alerts for:**
- Unusual spike in API requests
- OpenAI usage exceeding $10/month
- High rate of 403 Forbidden responses (indicates attack attempts)

### Security Best Practices

✅ **Currently Implemented:**
- Environment variables for secrets
- Strict CORS policy
- Request validation and limits
- Origin verification
- Input sanitization

⚠️ **Consider Adding (if needed):**
- IP-based rate limiting (using Upstash Redis)
- Request signing/HMAC validation
- Honeypot fields for bot detection
- CAPTCHA for suspicious traffic

### Troubleshooting

**403 Forbidden errors:**
- Check that you're accessing from `hiddevanheijst.nl` or `www.hiddevanheijst.nl`
- For local development, ensure `NODE_ENV=development` is set

**500 Internal Server Error:**
- Verify `OPENAI_API_KEY` is set in Vercel environment variables
- Check OpenAI API status and account balance
- Review Vercel function logs for detailed errors

### Emergency Response

**If you suspect API abuse:**
1. Rotate OpenAI API key immediately in OpenAI Dashboard
2. Update `OPENAI_API_KEY` in Vercel environment variables
3. Redeploy to apply new key
4. Review usage patterns in OpenAI and Vercel dashboards
5. Consider temporarily disabling the chat feature

**Quick disable:**
```javascript
// Add at top of handler function
return res.status(503).json({ error: 'Chat temporarily unavailable' });
```
