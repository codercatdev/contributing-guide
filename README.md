# Contributing to Couchbase Starter Kits

Thank you for your interest in contributing to Couchbase starter kits! This guide will help you understand how to contribute new starter kits for various frameworks.

Please review the [Contributing](#contributing) section briefly to understand the process of contributing new starter kits. When you are ready to get started, this README and the accompanying [sample files](samples) will help you create a new starter kit.

## Current Starter Kits

| Framework | Repository Link |
|-----------|-----------------|
| Spring    | [Spring Starter Kit](https://github.com/couchbase-starter-kit/couchbase-spring-starter) |
| Rails     | [Rails Starter Kit](https://github.com/couchbase-starter-kit/couchbase-rails-starter) |

## Required Environment Variables

| Variable Name                      | Description                                                 |      Default value       |
|:-----------------------------------|:------------------------------------------------------------|:------------------------:|
| SPRING_APPLICATION_NAME            | The name of your application, used for OTLP as well         | couchbase-spring-starter |
| SPRING_COUCHBASE_CONNECTION_STRING | A couchbase connection string                               |            -             |
| SPRING_COUCHBASE_USERNAME          | Username for authentication with Couchbase                  |            -             |
| SPRING_COUCHBASE_PASSWORD          | Password for authentication with Couchbase                  |            -             |
| COUCHBASE_USE_CAPELLA              | Use to change the connection profile                        |          false           |
| COUCHBASE_DEFAULT_BUCKET           | The name of the Couchbase Bucket, parent of the scope       |         default          |
| COUCHBASE_DEFAULT_SCOPE            | The name of the Couchbase scope, parent of the collection   |         _default         |
| COUCHBASE_DEFAULT_COLLECTION       | The name of the Couchbase collection to store the Documents |         _default         |
| COUCHBASE_OTLP_ENABLED             | Enable traces and metrics OTLP export                       |          false           |
| COUCHBASE_OTLP_ENDPOINT            | The OTLP server endpoint to send metrics and traces         |            -             |

## Basic Functionality

Each starter kit should include the following basic functionalities:
- Establish a connection to Couchbase, with the option for both Couchbase Server and Capella.
- Include the appropriate Couchbase SDK for the language/framework.

## Necessary Files

Each starter kit should include the following files, and you can find examples of these in the [samples](samples) directory that you can use in your repository:

- `README.md`: A README file that includes instructions on how to run the starter kit.
- `LICENSE`: A license file that includes the license for the starter kit.
- `CODE_OF_CONDUCT.md`: A code of conduct file that includes the code of conduct for the starter kit.
- `.env.sample`: A sample environment file that includes the necessary environment variables for the starter kit.
- `.github/workflows/test-couchbase.yml`: A GitHub Action workflow that tests the connection to Couchbase.
- `.gitpod.yml`: A Gitpod configuration file that deploys the starter kit in Gitpod.
- `.devcontainer/devcontainer.json`: A GitHub Codespaces configuration file that deploys the starter kit in GitHub Codespaces.

## Testing

To ensure your starter kit works correctly, you should include tests that verify the connection to Couchbase. The [sample workflow](samples/.github/workflows/test-connection.yml) can be used to test the connection to Couchbase.

The workflow should be modified to include the necessary environment variables for your starter kit:

* The `COUCHBASE_DEFAULT_BUCKET` variable should be unique, the convention is to prepend the bucket name with the framework name, such as `spring_`, `rails_`, or `python_`.
* The `Set up JDK` and `Setup Gradle` steps should be modified to match the build tools for your specific framework.

The secrets used in the workflow are stored at the `couchbase-starter-kit` GitHub organization level, so there is no need to create them in your repository.

The workflow is added to the `.github/workflows` directory in your repository and can be named `test-connection.yml` or similar.

## Deployment

The starter kit should be ready to deploy in any number of environments. At a minimum, the starter kit should be deployable in Gitpod, and GitHub Codespaces. See the [sample README](samples/README.md) to be included in your repository to view the Gitpod and GitHub Codespaces buttons that are added to the top of the README.

### Gitpod

The sample configuration for Gitpod can be found in the [samples/.gitpod.yml](samples/.gitpod.yml) file. This file should be included in the root of your repository.

### GitHub Codespaces

The sample configuration for GitHub Codespaces can be found in the [samples/.devcontainer/devcontainer.json](samples/.devcontainer/devcontainer.json) file. This file should be included in the `.devcontainer` directory in the root of your repository.

## Contributing

The best way to get started is by looking at the open Issues in this repository. If you see a framework or language that you are familiar with, feel free to contribute a starter kit for that framework.

What about frameworks or languages not mentioned in the open Issues? Feel free to open a new Issue and let us know what you would like to contribute. The team will be happy to review, provide feedback and guidance, and help you get started.