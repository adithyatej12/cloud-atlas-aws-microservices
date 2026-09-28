# Security

## IP-Based Access Control

The employee administration service is protected using IP-based filtering at the Application Load Balancer.

The `/admin/*` routes are accessible only from the configured whitelisted IP.

## Public Access

Customer catalog functionality is exposed through the normal application path.

## Administrative Access

Employee functionality uses:

```text
/admin/*
