# Coolify Self Growth

A self-hosted GrowthBook instance optimized for Coolify deployment with enhanced security, monitoring, and production-ready configurations.

## Key Features

### 🔧 Coolify-Optimized
- Health checks for proper service orchestration
- Environment variable templating for easy configuration
- Proper networking and volume management
- Restart policies for reliability

### 🔒 Security & Configuration
- Configurable MongoDB credentials
- JWT and encryption key support
- Email configuration for notifications
- Cloud storage integration (S3)

### 📊 Production-Ready
- Latest MongoDB 7 image
- Proper dependency management
- Volume persistence for data and uploads
- Network isolation

## Required Environment Variables

Create these in your Coolify environment:

```sh
# Required
MONGO_ROOT_PASSWORD=your_secure_mongo_password
JWT_SECRET=your_jwt_secret_key_here
ENCRYPTION_KEY=your_32_character_encryption_key

# Optional but recommended
APP_ORIGIN=https://your-domain.com
API_HOST=https://your-domain.com:3100
NODE_ENV=production

# Optional - Email Configuration
EMAIL_ENABLED=true
EMAIL_HOST=smtp.your-provider.com
EMAIL_PORT=587
EMAIL_HOST_USER=your-email@domain.com
EMAIL_HOST_PASSWORD=your-email-password
EMAIL_FROM=noreply@your-domain.com

# Optional - AWS S3 for file uploads
UPLOAD_METHOD=s3
S3_BUCKET=your-bucket-name
S3_REGION=us-east-1
AWS_ACCESS_KEY_ID=your-access-key
AWS_SECRET_ACCESS_KEY=your-secret-key
```

## Deployment Notes

- **Ports**: The app runs on port 3000 (frontend) and 3100 (API)
- **Data Persistence**: MongoDB data and file uploads are persisted in Docker volumes
- **Health Checks**: Configured for both MongoDB and GrowthBook for proper startup ordering
- **Networking**: Uses a dedicated bridge network for service isolation

## Security Recommendations

- Generate strong passwords and secrets
- Use environment variables for all sensitive data
- Consider using an external MongoDB service for production
- Set up proper SSL/TLS termination in Coolify
- Configure email for proper user management

---

The configuration follows GrowthBook's official documentation while adding Coolify-specific optimizations for health checks, environment variable management, and production deployment patterns.