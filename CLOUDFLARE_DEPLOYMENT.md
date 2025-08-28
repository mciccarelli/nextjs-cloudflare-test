# Cloudflare Pages Deployment Guide

## API Token Requirements

Your Cloudflare API token needs the following permissions:

### Required Permissions:
1. **Account** - Cloudflare Pages:Edit
2. **Zone** - Page Rules:Edit (if using custom domain)
3. **Zone** - DNS:Edit (if using custom domain)

### Creating a New API Token:
1. Go to https://dash.cloudflare.com/profile/api-tokens
2. Click "Create Token"
3. Use "Custom token" template
4. Set these permissions:
   - Account > Cloudflare Pages > Edit
   - Account > Account Settings > Read (optional but recommended)
   - Zone > Zone Settings > Read (if using custom domain)
   - Zone > DNS > Edit (if using custom domain)
5. Set Account Resources to include your account
6. Set Zone Resources to "All zones" or specific zone if using custom domain

## Environment Variables

Set in your CI/CD or local environment:
```bash
CLOUDFLARE_API_TOKEN=your_token_here
CLOUDFLARE_ACCOUNT_ID=d716da3a9f02e4588e0f79391d494224
```

## Build Settings for Cloudflare Pages

- **Build command**: `npm run build`
- **Build output directory**: `dist`
- **Framework preset**: None (manual configuration)

## Troubleshooting

If you get authentication errors:
1. Verify token permissions at https://dash.cloudflare.com/profile/api-tokens
2. Ensure the token has "Cloudflare Pages:Edit" permission
3. Check that the account ID matches your account
4. Try regenerating the token with correct permissions