# Todo App

This is a simple demo nodejs todo app which depends on AWS RDS cloud resouce (MySQL database). It allows you to create, update, and delete tasks in a user-friendly interface.

## Features

- Add item to list
- Mark item as done
- Delete item from list

## Pre-requisites

Ensure [MySQL RDS cloud resource plan](./mysql-rds-cloud-resource-plan.yaml) is applied in Wayfinder.

## Installation

1. Clone the repository: `git clone https://github.com/appvia/todo-app.git`
2. Run docker compose up --build --detach

## 🔧 Required GitHub Secrets

When projects are created from this template, the following GitHub repository secrets need to be configured for the CI/CD pipeline to work properly:

- `ARTIFACTORY_URL`: `https://trialm6kl97.jfrog.io`
- `ARTIFACTORY_ACCESS_TOKEN`: Your JFrog Artifactory access token

These secrets are used to push Docker images to JFrog Artifactory and enable the JFrog Artifactory plugin integration in Backstage.

**Note**: Docker images can be pulled from JFrog Artifactory without authentication since anonymous access is enabled.

## Usage

1. Open the app in your browser: `http://localhost:3000` (may take a few seconds to start up)
2. Create a new task by entering a description and clicking "Add Item"
3. Update the status of a task by clicking the checkbox next to it
4. Delete a task by clicking the "Delete" button next to it


## Published Images

The images are published on Github Container Registry: https://github.com/appvia/todo-app/pkgs/container/todo-app

## Contributing

Contributions are welcome! If you find a bug or have a feature request, please open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
