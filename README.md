# 🚂 Vercel Remote Cache on Railway 

Deploy your own self-hosted Turborepo remote cache on Railway with just a few clicks. This solution provides a secure alternative to Vercel's Remote Cache. 🔒

## How to Setup ⚙️

1. Deploy to Railway with One Click 🎯  
[![Deploy on Railway](https://railway.com/button.svg)](https://railway.app/template/tRFTHR?referralCode=chIZYq)

2. Configure Your Turborepo 🛠️

After deploying to Railway, you'll need to configure your Turborepo to use the remote cache. Here's how:

1. Go to your Railway project and select the service we just deployed (it has the Turborepo logo)
2. Navigate to the "Variables" tab
3. Find and copy these environment variables: 📋
   - `TURBO_TOKEN`: Your authentication token
   - `TURBO_API_URL`: The URL of your remote cache

Create or modify `.turbo/config.json` in your project root with the values you copied from Railway:
```json
{
  "teamslug": "railway-remote-cache",
  "token": "<TURBO_TOKEN>",
  "experimentalUI": false,
  "apiurl": "<TURBO_API_URL>"
}
```

3. Start Using the Cache 🎉

```bash
turbo build # Remote cache will be automatically utilized
```

## Troubleshooting 🔍

- Ensure your Railway deployment is running and accessible
- Verify that your token and API URL are correctly configured

Still need help? Create a help thread on Railway's [Discord](https://discord.gg/railway) 💬