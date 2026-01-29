# Hello CI/CD 🚀

A simple Node.js application demonstrating a complete CI/CD pipeline using GitHub Actions and Docker.

## Project Overview

This project is a basic HTTP server that responds with "Hello CI/CD 🚀". It includes:
- A simple Node.js HTTP server running on port 3000
- Automated testing with GitHub Actions
- Docker containerization
- CI/CD pipeline that automatically builds and tests on every push to the main branch

## Project Structure

```
hello-ci-cd/
├── app.js              # Main Node.js application
├── test.js             # Test file
├── package.json        # Project dependencies and scripts
├── Dockerfile          # Docker configuration for containerization
├── .github/
│   └── workflows/
│       └── ci.yml      # GitHub Actions CI/CD pipeline
└── README.md           # This file
```

## Prerequisites

- Node.js 18+ (for local development)
- Docker (for containerization)
- Git (for version control)

## Installation & Setup

### Local Development

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd hello-ci-cd
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Run the application:
   ```bash
   npm start
   ```
   The server will start on `http://localhost:3000`

4. Run tests:
   ```bash
   npm test
   ```

### Docker

Build and run the application in Docker:

```bash
# Build the Docker image
docker build -t hello-ci-cd .

# Run the container
docker run -p 3000:3000 hello-ci-cd
```

The application will be available at `http://localhost:3000`

## CI/CD Pipeline

The project uses GitHub Actions for automated testing and Docker image building. The pipeline is defined in `.github/workflows/ci.yml` and includes:

1. **Checkout** - Pulls the latest code from the repository
2. **Setup Node.js** - Installs Node.js 18
3. **Install Dependencies** - Runs `npm install`
4. **Run Tests** - Executes test suite with `npm test`
5. **Build Docker Image** - Creates a Docker image for deployment

The pipeline is triggered automatically on every push to the `main` branch.

## Available Scripts

- `npm start` - Start the HTTP server
- `npm test` - Run the test suite

## Application Details

### app.js
A simple HTTP server that listens on port 3000 and responds to all requests with "Hello CI/CD 🚀"

### test.js
Basic unit test that verifies 1 + 1 = 2, ensuring the test infrastructure is working correctly.

## Docker Configuration

The Dockerfile uses:
- **Base Image**: `node:18-alpine` (lightweight Node.js image)
- **Working Directory**: `/app`
- **Port**: 3000 (exposed for HTTP traffic)
- **Start Command**: `npm start`

## Development Workflow

1. Make changes to the code
2. Test locally: `npm test`
3. Commit and push to the `main` branch
4. GitHub Actions automatically runs the CI/CD pipeline
5. Check the Actions tab in GitHub to see pipeline results

## Troubleshooting

- **Port 3000 in use**: Change the port in `app.js` or kill the process using port 3000
- **Dependencies not installed**: Run `npm install`
- **Docker build fails**: Ensure Docker is installed and running

## Future Enhancements

- Add more comprehensive tests
- Add deployment step to CI/CD pipeline
- Add linting and code formatting
- Add coverage reports
- Deploy to a cloud service (AWS, Heroku, etc.)

## License

MIT (or specify your license)
