# Auth0 X (Twitter) Login Setup Guide

## Prerequisites

1. An Auth0 account (sign up at https://auth0.com)
2. A Twitter Developer account and app (https://developer.twitter.com)

## Step 1: Configure Auth0

### 1.1 Create Auth0 Application

1. Go to your Auth0 Dashboard
2. Navigate to Applications > Applications
3. Click "Create Application"
4. Choose "Single Page Application"
5. Select "JavaScript" as the technology

### 1.2 Configure Application Settings

In your Auth0 application settings, set:

- **Allowed Callback URLs**: `http://localhost:8080, http://localhost:3000, https://yourdomain.com`
- **Allowed Logout URLs**: `http://localhost:8080, http://localhost:3000, https://yourdomain.com`
- **Allowed Web Origins**: `http://localhost:8080, http://localhost:3000, https://yourdomain.com`

### 1.3 Get Your Credentials

Note down these values from your Auth0 application settings:

- **Domain**: `your-app.auth0.com`
- **Client ID**: `your_client_id_here`

## Step 2: Configure Twitter Connection

### 2.1 Create Twitter App

1. Go to https://developer.twitter.com/en/portal/dashboard
2. Create a new project/app
3. Get your Twitter API credentials:
   - API Key
   - API Secret Key

### 2.2 Configure Auth0 Twitter Connection

1. In Auth0 Dashboard, go to Authentication > Social
2. Click on Twitter
3. Enter your Twitter API credentials
4. In the "Attributes" section, make sure these are selected:
   - Email address
   - Profile
5. Save the configuration

## Step 3: Update Your HTML File

Replace the placeholder values in `Pikachu.html`:

```javascript
// Replace these values with your actual Auth0 credentials
domain: 'YOUR_AUTH0_DOMAIN', // e.g., 'your-app.auth0.com'
clientId: 'YOUR_AUTH0_CLIENT_ID', // e.g., 'abc123def456...'
```

## Step 4: Test the Integration

1. Open `Pikachu.html` in a web browser
2. Click the "Login with X" button in the left sidebar
3. You should be redirected to Twitter for authentication
4. After successful login, you'll be redirected back to your game
5. The button should show your Twitter profile picture and name

## Troubleshooting

### Common Issues:

1. **CORS errors**: Make sure your domain is added to "Allowed Web Origins" in Auth0
2. **Redirect errors**: Check that your callback URLs are correctly configured
3. **Twitter connection fails**: Verify your Twitter API credentials in Auth0

### Development Tips:

- Use a local server (like Live Server in VS Code) instead of opening the file directly
- Check the browser console for any error messages
- Use Auth0's Real-time Webtask Logs to debug authentication issues

## Security Notes

- Never commit your Auth0 credentials to version control
- Use environment variables or a separate config file for production
- Consider implementing additional security measures like PKCE for production apps

## Additional Features You Can Add

Once basic login is working, you can enhance the integration:

1. **User Profile Display**: Show user info in the game UI
2. **Leaderboards**: Save high scores associated with user accounts
3. **Game Progress**: Save and sync game progress across devices
4. **Social Features**: Share scores on Twitter
5. **NFT Integration**: Connect user's wallet after authentication

## Support

If you encounter issues:

1. Check Auth0 documentation: https://auth0.com/docs
2. Review Twitter API documentation: https://developer.twitter.com/en/docs
3. Check browser console for error messages
