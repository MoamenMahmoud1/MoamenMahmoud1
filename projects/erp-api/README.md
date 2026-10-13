# ERP API & Sales ERP

An ERP system built around a Django backend, a React web client, and a separate Flutter app for field sales and warehouse work.

**This is a public project overview, not the source repository.** The application repositories are private.

## What it covers

- Sales, invoices, returns, purchasing, customers and suppliers
- Inventory, warehouse transfers and sales-vehicle stock
- Payments, refunds, accounting journals and financial reports
- Role-based access with company, branch and site scopes
- Employee shifts and customer assignment rules

## Backend work

The backend is a modular Django application. Business operations such as invoice confirmation, inventory changes and payment allocation are handled in database transactions. The project uses PostgreSQL row locking where concurrent requests could otherwise cause duplicate settlement or stock inconsistencies.

Other implementation details include:

- Idempotency for retried write requests
- Authentication and permission checks enforced by the backend
- Celery jobs for scheduled and background processing
- Redis for caching and supporting application services
- Reporting based on transactional data rather than separate financial copies

## Stack

| Area | Technology |
| --- | --- |
| Backend | Python, Django 6, Django-Bolt |
| Database | PostgreSQL |
| Background work | Celery, Redis |
| Web | React, TypeScript |
| Mobile | Flutter, Dart |
| Local environment | Docker Compose |

## Clients

**Web:** administration, branch operations and reporting through a React client.

**Mobile:** Flutter client for sales representatives and warehouse staff, with local persistence, queued offline writes and background synchronization.

## Current status

This overview describes implementation work in the private repositories. It is not a public demo, a production uptime claim, or a replacement for an end-to-end deployment check.

For more information, contact me through my [GitHub profile](https://github.com/MoamenMahmoud1).
