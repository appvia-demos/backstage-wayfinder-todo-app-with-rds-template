# AWS RDS Integration

This application uses AWS RDS MySQL database as its data store, provisioned through Wayfinder cloud resource plans.

## RDS Cloud Resource Plan

The MySQL RDS instance is defined in `mysql-rds-cloud-resource-plan.yaml` and must be applied in Wayfinder before deploying the application.

## Database Configuration

The application connects to the RDS instance using environment variables sourced from Wayfinder cloud resource outputs:

- `MYSQL_HOST` - RDS endpoint
- `MYSQL_USER` - Database username
- `MYSQL_PASSWORD` - Database password
- `MYSQL_DB` - Database name

## Wayfinder Integration

The RDS resource is managed through Wayfinder's cloud resource management system, providing:

- Automated provisioning
- Security management
- Backup and monitoring
- Cost optimization

## Component Definition

The database is defined as a `CloudResource` type in `wayfinder/components.yml`:

```yaml
spec:
  application: ${{ values.name }}
  cloudResource:
    plan: appvia-rds-mysql
    planVersion: 1.0.0
    variables:
      db_name: todos
      allocated_storage: ${{ values.database_allocated_storage }}
      instance_class: ${{ values.database_instance_class }}
```

## Environment Variables

The application component receives database connection details through cloud resource outputs:

```yaml
- name: MYSQL_HOST
  fromCloudResourceOutput:
    componentName: mysql-${{ values.name }}
    output: DATABASE_HOST
```