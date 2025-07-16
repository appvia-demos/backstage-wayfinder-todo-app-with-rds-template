# ${{ values.name }}

${{ values.description }}

## Overview

A simple todo application demonstrating Backstage integrations with AWS RDS cloud resource. This template uses AWS RDS for the database instead of a containerized MySQL instance.

## Features

- Add item to list
- Mark item as done
- Delete item from list
- AWS RDS MySQL integration

## Pre-requisites

Ensure [MySQL RDS cloud resource plan](../mysql-rds-cloud-resource-plan.yaml) is applied in Wayfinder.

## Quick Start

```bash
docker compose up --build --detach
```

Visit http://localhost:3000

## Learn More

- [Development Guide](development.md)
- [RDS Integration](rds-integration.md)