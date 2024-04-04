# AlchemyLanguage Demo
[![Build Status](https://travis-ci.org/watson-developer-cloud/alchemylanguage-nodejs.svg?branch=master)](http://travis-ci.org/watson-developer-cloud/alchemylanguage-nodejs)
[![codecov.io](https://codecov.io/github/watson-developer-cloud/alchemylanguage-nodejs/coverage.svg?branch=master)](https://codecov.io/github/watson-developer-cloud/alchemylanguage-nodejs?branch=master)

[AlchemyLanguage][service_url] is a collection of APIs that offer text analysis through natural language processing. The AlchemyLanguage APIs can analyze text and help you to understand its sentiment, keywords, entities, high-level concepts and more.


Give it a try! Click the button below to fork into IBM DevOps Services and deploy your own copy of this application on Bluemix.

[![Deploy to Bluemix](https://bluemix.net/deploy/button.png)](https://bluemix.net/deploy?repository=https://github.com/watson-developer-cloud/alchemylanguage-nodejs)

## Getting Started

1. Create a Bluemix Account

  [Sign up][sign_up] in Bluemix, or use an existing account.

2. Download and install the [Cloud-foundry CLI][cloud_foundry] tool

3. Edit the `manifest.yml` file and change the `<application-name>` to something unique.
  ```none
applications:
- services:
  - alchemy-service
  name: <application-name>
  command: npm start
  path: .
  memory: 256M
  ```
  The name you use will determinate your application url initially, e.g. `<application-name>.mybluemix.net`.

4. Connect to Bluemix in the command line tool
  For US Region
  ```sh
  $ cf api https://api.ng.bluemix.net
  ```

  ```sh
  $ cf login -u <your user ID>
  ```

5. Create the AlchemyLanguage Service in Bluemix

  ```sh
  $ cf create-service alchemy_api standard alchemy-service
  ```

6. Push it live!

  ```sh
  $ cf push
  ```

See the full [Getting Started][getting_started] documentation for more details, including code snippets and references.

## Running locally

  The application uses [Node.js](http://nodejs.org/) and [npm](https://www.npmjs.com/).

1. Copy the `apikey` from your `alchemy-service` service in Bluemix to a  `.env` file in the root directory.
2. Install [Node.js](http://nodejs.org/)
3. Go to the project folder in a terminal and run:
    ```
    npm install
    ```
4. Start the application
    ```
    npm start
    ```
6. Go to http://localhost:3000

## Troubleshooting

To troubleshoot your Bluemix application, use the logs. To see the logs, run:

  ```sh
  $ cf logs <application-name> --recent
  ```

## License

  This sample code is licensed under Apache 2.0. Full license text is available in [LICENSE](LICENSE).

## Contributing

  See [CONTRIBUTING](.github/CONTRIBUTING.md).

## Open Source @ IBM

  Find more open source projects on the [IBM Github Page](http://ibm.github.io/)

### Privacy Notice

This node sample web application includes code to track deployments to Bluemix and other Cloud Foundry platforms. The following information is sent to a [Deployment Tracker][deploy_track_url] service on each deployment:

* Application Name (`application_name`)
* Space ID (`space_id`)
* Application Version (`application_version`)
* Application URIs (`application_uris`)

This data is collected from the `VCAP_APPLICATION` environment variable in IBM Bluemix and other Cloud Foundry platforms. This data is used by IBM to track metrics around deployments of sample applications to IBM Bluemix. Only deployments of sample applications that include code to ping the Deployment Tracker service will be tracked.

### Disabling Deployment Tracking

Deployment tracking can be disabled by removing `require('cf-deployment-tracker-client').track();` from the beginning of the `server.js` file at the root of this repo.

[deploy_track_url]: https://github.com/cloudant-labs/deployment-tracker
[service_url]: http://www.ibm.com/smarterplanet/us/en/ibmwatson/developercloud/alchemy-language.html
[cloud_foundry]: https://github.com/cloudfoundry/cli
[getting_started]: http://www.ibm.com/smarterplanet/us/en/ibmwatson/developercloud/doc/getting_started/
[sign_up]: https://console.ng.bluemix.net/registration/
