# CodeGingerAI - GitHub PR Review Bot 🤖

CodeGingerAI is an intelligent GitHub bot that automatically reviews pull requests and responds to mentions using the Shapes API. It helps maintain code quality and provides instant feedback on code changes.

## Features ✨

- 🤖 **Automatic PR Reviews**: Automatically reviews new pull requests using Shapes API
- 💬 **Smart Responses**: Responds to mentions in PR comments
- 📝 **Detailed Reviews**: Provides comprehensive code reviews with suggestions
- 🔄 **Real-time Updates**: Instantly responds to PR events and mentions

## Installation 🚀

### From GitHub Marketplace

1. Visit the [CodeGingerAI GitHub App](https://github.com/marketplace/codegingerai) in the GitHub Marketplace
2. Click "Install it for free"
3. Choose the repositories where you want to install the bot
4. Click "Install"

### Manual Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/codegingerai.git
   cd codegingerai
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory with the following variables:
   ```env
   SHAPES_API_KEY=your_shapes_api_key_here
   SHAPES_BASE_URL=https://api.shapes.inc/v1
   SHAPES_MODEL=shapesinc/codegingerai
   ```

4. Set up GitHub App credentials:
   - Create a new GitHub App in your organization
   - Set the webhook URL to your deployment URL
   - Generate an RSA private key:
     ```bash
     # Generate a new RSA private key
     openssl genrsa -out private-key.pem 2048
     ```
   - Save the private key as `private-key.pem` in the root directory
   - Add the following to your `.env` file:
     ```env
     GITHUB_APP_ID=your_app_id
     GITHUB_CLIENT_ID=your_client_id
     GITHUB_CLIENT_SECRET=your_client_secret
     GITHUB_WEBHOOK_SECRET=your_webhook_secret
     GITHUB_PRIVATE_KEY_PATH=./private-key.pem  # Path to your RSA private key
     ```

5. Start the bot:
   ```bash
   npm start
   ```

## Usage 📝

### Automatic PR Reviews

The bot automatically reviews new pull requests when they are opened. It will:
1. Fetch the PR diff
2. Analyze the changes using Shapes API
3. Post a review comment with suggestions and feedback

### Responding to Mentions

To interact with the bot:
1. Mention `@codegingerai[bot]` in a PR comment
2. The bot will respond with:
   - PR title and description
   - List of existing comments
   - Context-aware responses

## Configuration ⚙️

The bot can be configured through environment variables:

| Variable | Description | Default |
|----------|-------------|---------|
| `SHAPES_API_KEY` | Your Shapes API key | Required |
| `SHAPES_BASE_URL` | Shapes API base URL | https://api.shapes.inc/v1 |
| `SHAPES_MODEL` | Model to use for reviews | shapesinc/codegingerai |
| `GITHUB_PRIVATE_KEY_PATH` | Path to RSA private key | ./private-key.pem |

## Development 🛠️

### Project Structure
```
codegingerai/
├── src/
│   ├── config/
│   │   └── config.js         # Configuration and environment variables
│   ├── services/
│   │   └── shapesService.js  # Shapes API service
│   └── index.js             # Main application file
├── .env                     # Environment variables
├── private-key.pem         # RSA private key for GitHub App
└── package.json            # Project configuration
```

### Running Tests
```bash
npm test
```

## Contributing 🤝

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License 📄

This project is licensed under the ISC License - see the [LICENSE](LICENSE) file for details.

## Support 💬

If you encounter any issues or have questions:
- Open an issue in this repository
- Contact us at support@codegingerai.com
- Visit our [documentation](https://docs.codegingerai.com)

## Acknowledgments 🙏

- [Probot](https://probot.github.io/) for the GitHub App framework
- [Shapes API](https://shapes.inc) for the AI review capabilities 