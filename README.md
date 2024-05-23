# Build & Deploy

This repository contains a Node.js project with a Vite web application located in the `sample-web` directory. The project is configured to automatically build and deploy the application to AWS CloudFront when changes are pushed to the `dev` branch.

## Project Structure

```
├── sample-web
│   ├── dist
│   ├── src
│   ├── package.json
│   └── ...
├── .github
│   ├── workflows
│   │   └── deploy.yml
└── README.md
```

## Prerequisites

- Node.js (version 20.x or higher)
- AWS CLI configured with appropriate permissions
- AWS S3 bucket for storing the built application
- AWS CloudFront distribution for serving the application

## GitHub Actions Workflow

The workflow file `.github/workflows/deploy.yml` is configured to:

1. Check out the code.
2. Configure AWS credentials.
3. Set up Node.js.
4. Install dependencies.
5. Build the Vite application.
6. Deploy the built application to an S3 bucket.
7. Invalidate the CloudFront cache to ensure the latest version is served.

## Secrets

Ensure the following secrets are set in your GitHub repository settings:

- `AWS_REGION`: The AWS region where your resources are located.
- `AWS_ACCOUNT_ID`: Your AWS account ID.
- `AWS_S3_BUCKET_NAME`: The name of the S3 bucket where the built application will be deployed.
- `AWS_CLOUDFRONT_DISTRIBUTION_ID`: The ID of the CloudFront distribution to invalidate the cache.

## Installation and Deployment

### Local Development

1. Clone the repository:

```sh
git clone https://github.com/DFanso/s3-static-web-deploy.git
cd s3-static-web-deploy/sample-web
```

2. Install dependencies:

```sh
npm install
```

3. Run the development server:

```sh
npm run dev
```

### Deployment

To manually trigger the deployment process, push changes to the `dev` branch or use the "Run workflow" feature in GitHub Actions.

## License

This project is licensed under the MIT License.
