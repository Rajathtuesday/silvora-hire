# Silvora

Silvora is a private engineering project built to explore backend system design,
file storage workflows, and real-world operational trade-offs.

This project focuses on **backend correctness, system boundaries, and ownership**
rather than scale or commercial readiness.

🌐 Project website (overview & architecture):  
https://rajathtuesday.github.io/silvora-hire/

---

## What is Silvora?

Silvora is a self-hosted file storage system designed and implemented to understand:

- Authenticated backend API design
- Chunked and resumable file uploads
- Object storage integration
- Failure handling and cleanup strategies
- Linux-based deployment and operation

The system is intentionally scoped and feature-frozen to prioritize learning,
stability, and clarity over feature growth.

---

## High-level architecture

Silvora is composed of the following components:

### Client
- Handles authentication
- Splits large files into smaller chunks
- Uploads chunks with retry support

### Backend API
- Built using Django and Django REST Framework
- Validates requests and enforces user-scoped access isolation
- Coordinates chunk tracking and upload state

### Storage
- Files are stored using **Cloudflare R2** (S3-compatible object storage)
- Uploaded chunks are assembled server-side once all parts are received
- Metadata is tracked to support retrieval and cleanup

### Deployment & Operations
- Deployed on a Linux server using Nginx and Gunicorn
- Manual monitoring and cleanup to better observe real-world behavior
- No auto-scaling or multi-region setup (by design)

---

## Key engineering focus areas

- Backend API design and correctness
- Handling partial failures and retries
- Storage abstractions and ownership boundaries
- Operational discipline and scope control
- Honest documentation of limitations

---

## Project status

- **Status:** Private / Internal Alpha
- **Usage:** Personal use + very small trusted group
- **Development:** Feature-frozen (maintenance only)

---

## Evaluation build (Android)

An Android APK may be provided for limited evaluation purposes.

> ⚠️ This build is shared strictly for testing and demonstration.  
> Do not upload sensitive or irreplaceable data.

---

## Disclaimer

This project has not undergone a formal security audit and does not provide
production-grade guarantees. It exists purely as an engineering exercise.

---

## Author

Built and maintained by **Rajath**  
GitHub: https://github.com/Rajathtuesday
