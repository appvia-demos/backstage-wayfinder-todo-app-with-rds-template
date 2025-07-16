# Development Guide

## Quick Start

```bash
docker compose up --build --detach
```

## Testing

```bash
cd app
npm test
```

## Environment Variables

The application connects to AWS RDS using environment variables provided by Wayfinder:

- `MYSQL_HOST` - RDS endpoint
- `MYSQL_USER` - Database username  
- `MYSQL_PASSWORD` - Database password
- `MYSQL_DB` - Database name

## GitHub Secrets

When projects are created from this template, configure these GitHub repository secrets:

- `ARTIFACTORY_URL`: `https://trialm6kl97.jfrog.io`
- `ARTIFACTORY_ACCESS_TOKEN`: Your JFrog Artifactory access token

These secrets are used to push Docker images to JFrog Artifactory and enable the JFrog Artifactory plugin integration in Backstage.

## Local Development

For local development, the application uses Docker Compose with a local MySQL container while production uses AWS RDS.