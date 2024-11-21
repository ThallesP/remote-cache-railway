# 🚂 Self-Hosted Turborepo Remote Cache on Railway

Deploy a secure, self-hosted Turborepo remote cache on Railway with just a few clicks. This alternative provides you full control over your build cache infrastructure. 🔒

## Setup Guide 

### 1. Deploy to Railway with One Click 🎯  
[![Deploy on Railway](https://railway.com/button.svg)](https://railway.app/template/tRFTHR?referralCode=chIZYq)

Simply click the Deploy on Railway button above to instantly set up your remote cache.

### 2. Configure Turborepo Project 🛠️

After deploying, you'll need to configure your Turborepo project to use the new remote cache:

1. Open your Railway project we just deployed
2. Select the service with the Turborepo logo
3. Navigate to the "Variables" tab
4. Copy these required environment variables:
  - `TURBO_TOKEN`: Authentication token
  - `TURBO_API_URL`: Remote cache endpoint

### 3. Update Turborepo Configuration 📝

Now it's time to modify our code, but trust me, it's easy.  
Create or modify `.turbo/config.json` in your project root:

```json
{
 "teamSlug": "railway-remote-cache",
 "token": "<TURBO_TOKEN>",
 "experimentalUI": false,
 "apiUrl": "<TURBO_API_URL>"
}
```

> ⚠️ **Security Warning**: Never commit the `config.json` file with your actual `TURBO_TOKEN` to version control. Add `.turbo/config.json` to your `.gitignore` file to prevent accidentally exposing sensitive credentials.

<details>
<summary>💡 <strong>Alternative:</strong> Using Environment Variables</summary>

If you don't want to create the `config.json` file, you can set the following environment variables in your Turborepo project when building:

```properties
TURBO_TOKEN=<TURBO_TOKEN>
TURBO_API_URL=<TURBO_API_URL>
TURBO_TEAM=railway-remote-cache
```

And to load it from a `.env` file, you can use the `dotenv-cli` package:

```bash
dotenv -e .env -- npx turbo build
```

</details>

### 4. Use Remote Cache 🎉

Run your Turborepo commands as normal. The remote cache will be automatically utilized:

```bash
turbo build
```
You can verify the remote cache is working by checking your Turborepo build logs. When successful, you'll see:

```
Remote caching enabled
```

## Troubleshooting 🔍

### Common Issues
- Verify Railway deployment is running and accessible
- Double-check that your token and API URL are correctly configured
- Test the setup using the [example reference project](https://github.com/ThallesP/remote-cache-railway) to validate configuration and rule out any potential template-specific issues

### Need More Help?
Join Railway's [Discord community](https://discord.gg/railway) for additional support and troubleshooting. 