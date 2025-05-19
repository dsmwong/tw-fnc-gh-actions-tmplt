# Deploying Functions via GitHub Actions

This application works as a sample to show how Twilio Functions
can be tracked together in one repository and deployed automatically via a
Continuous Delivery mechanism such as GitHub Actions.

## Project Structure

```
tw-fnc-gh-actions-tmplt
├── README.md
├── assets
├── functions
├── node_modules
├── package-lock.json
├── package.json

```

### Twilio Functions & Assets

The `functions` and `assets` folders contain any [Twilio Functions & Assets](https://www.twilio.com/functions) you might want to deploy. They'll be deployed using `twilio serverless:deploy`  that is part of the Twilio Serverless Toolkit](https://www.twilio.com/docs/labs/serverless-toolkit).

### GitHub Actions

You can find the GitHub Actions workflow that is being triggered on each push
to `main` inside `.github/workflows/deploy-functions.yml`. The logic can be ported to any
other CI/CD platform that can:

1. Can store secrets and set them as environment variables
1. Install Node.js
1. Install twilio cli and serverless plugin from npm
1. Deploy funcions using `twilio serverless:deploy`

## How to use this project

This project is not intended to immediately work by forking the project.
Instead it is intended to work as a blueprint for your own projects copy the Github Actions Workflow into your working Twilio Functions project

Please set your Twilio Account SID and Auth Token as `TWILIO_ACCOUNT_SID` and `TWILIO_AUTH_TOKEN` secrets inside GitHub Actions' Secrets Store

## Code of Conduct

This template is open source and welcomes contributions. All contributions are subject to our [Code of Conduct](https://github.com/twilio-labs/.github/blob/master/CODE_OF_CONDUCT.md).

## License

MIT