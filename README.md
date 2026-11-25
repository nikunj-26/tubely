# Tubely

Tubely is a video management application for creating video drafts, uploading videos and thumbnails, and serving video files through Amazon S3 and CloudFront.

## Requirements

- Go 1.27.2 or newer
- FFmpeg (`ffmpeg` and `ffprobe`) available on your `PATH`
- An AWS account with an S3 bucket and CloudFront distribution
- AWS credentials available to the AWS SDK, for example through the AWS CLI configuration

## Setup

Install dependencies and configure the application:

```bash
go mod download
cp .env.example .env
```

Update `.env` with your local database path, JWT secret, S3 bucket, AWS region, CloudFront distribution URL, and desired port. Configure AWS credentials separately using your preferred AWS credential provider.

To download sample images and videos, provide URLs for a landscape image, portrait image, landscape video, and portrait video:

```bash
./samplesdownload.sh \
  https://example.com/landscape.png \
  https://example.com/portrait.png \
  https://example.com/landscape.mp4 \
  https://example.com/portrait.mp4
```

## Run

Start the server from the repository root:

```bash
go run .
```

Open the URL printed in the terminal (by default, `http://localhost:8091/app/`).
