# Technology Stack: Create Community App Platform

## Overview

This document describes the technology stack recommended for the Create Community App platform, supporting the pilot implementation and future whole-company rollout.

## Frontend

| Layer | Technology | Purpose |
|---|---|---|
| Mobile App | React Native | Cross-platform iOS/Android app for kamaliʻi and ʻohana |
| Web Admin | React | Admin dashboard for content moderation and user management |
| UI Components | React Native Paper / MUI | Accessible, themeable component library |
| State Management | Redux Toolkit | Predictable state container for complex app state |

## Backend

| Layer | Technology | Purpose |
|---|---|---|
| API Server | Node.js + Express | RESTful API and WebSocket server |
| Real-time | Socket.IO | Live notifications, direct messaging, content feeds |
| Authentication | Auth0 / Firebase Auth | Secure user authentication with role-based access |
| Media Processing | Cloudinary | Image/video upload, transformation, and delivery |

## Database & Storage

| Component | Technology | Purpose |
|---|---|---|
| Primary Database | PostgreSQL | User data, posts, messages, activity records |
| Cache | Redis | Session management, rate limiting, real-time pub/sub |
| Object Storage | AWS S3 | Media files, attachments, exported reports |

## Content Moderation & Safety

| Component | Technology | Purpose |
|---|---|---|
| Keyword Filtering | Custom rule engine + AWS Comprehend | Automated flagging of high-risk content |
| Post Approval Queue | Admin dashboard workflow | Human-in-the-loop approval for all posts |
| Incident Reporting | In-app reporting + email alerts | Routes flagged reports to designated Admins |
| Access Controls | Role-based permissions (Admin, Facilitator, Kamaliʻi, ʻOhana) | Enforces least-privilege access per user type |

## Infrastructure & DevOps

| Component | Technology | Purpose |
|---|---|---|
| Cloud Provider | AWS | Hosting, managed services, compliance |
| Container Orchestration | Docker + ECS | Reproducible deployments, scalability |
| CI/CD | GitHub Actions | Automated testing and deployment pipelines |
| Monitoring | Datadog / CloudWatch | Uptime, error tracking, usage metrics |
| CDN | CloudFront | Fast, globally distributed content delivery |

## Integrations

| System | Integration Type | Purpose |
|---|---|---|
| Constituent Management System | REST API (future phase) | Data alignment and reporting |
| Push Notifications | Firebase Cloud Messaging (FCM) / APNs | Alerts, announcements, reminders |
| Analytics | Mixpanel | User adoption and engagement metrics |
| Surveys & Feedback | Typeform / in-app forms | Pilot feedback collection |

## Security & Compliance

- **Data Encryption:** TLS 1.3 in transit; AES-256 at rest
- **Usage Window Enforcement:** Server-side access controls restrict app availability to 7:00 AM – 8:00 PM
- **Private Instance:** Invite-only onboarding; no public discoverability
- **Minor Data Protection:** Compliant with COPPA and applicable Hawaii state privacy laws for users under 13
- **Audit Logging:** All admin actions and content moderation decisions are logged

## Scalability Path

The pilot begins with a single site (Center, Hawaii) serving approximately 50–65 users. The architecture is designed to scale horizontally to support a whole-company rollout across multiple sites with minimal re-architecture.

## Ticket Reference

Ticket ID: `321ce158-1c97-4406-8341-fb58466afa44`
