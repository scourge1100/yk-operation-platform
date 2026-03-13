# System Architecture

## Overview

```mermaid
graph TD
    Operator[Game Operator] --> AdminUI[Admin Web Console]

    AdminUI --> SpringAPI[Spring API Server]

    SpringAPI --> MariaDB[(MariaDB)]
    SpringAPI --> MSSQL[(MSSQL)]

    SpringAPI --> S3[(AWS S3)]

    SpringAPI --> CloudWatch[CloudWatch Monitoring]

    GitLabCI[GitLab CI/CD] --> EC2[(AWS EC2 Deployment)]
