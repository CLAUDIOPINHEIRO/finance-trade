# Finance Trade
FitTrade is a Node.js application that uses many IBM Financial services and Watson services.  

The application is a modern portfolio manager that provides real-time insight into how news all around the world can impact the investment to any given portfolio. 

# Overview

This repo is UNDER DEVELOPMENT...

## Running the app on Bluemix

1. If you do not already have a Bluemix account, [sign up here][bluemix_reg_url]

1. Download and install the [Cloud Foundry CLI][cloud_foundry_url] tool

1. Clone the app to your local environment from your terminal using the following command:

  ```
  git clone https://github.com/IBM-Bluemix/finance-trade.git
  ```

1. `cd` into this newly created directory

1. Open the `manifest.yml` file and change the `host` value to something unique.

  The host you choose will determinate the subdomain of your application's URL:  `<host>.mybluemix.net`

1. Connect to Bluemix in the command line tool and follow the prompts to log in

  ```
  cf login -a https://api.ng.bluemix.net
  ```

1. Create a Cloudant service in Bluemix

  ```
  cf create-service cloudantNoSQLDB Lite fintrade-db
  ```

1. Push the app to Bluemix

  ```
  cf push 
  ```
  
And voila! You now have your very own finance application running on Bluemix.

## Run the app locally

1. If you do not already have a Bluemix account, [sign up here][bluemix_reg_url]

1. If you have not already, [download Node.js][download_node_url] and install it on your local machine.

1. Create a Cloudant service in Bluemix

  ```
  cf create-service cloudantNoSQLDB Lite fintrade-db
  ```

1. In the checkout directory, copy the file ```vcap-local.template.json``` to ```vcap-local.json```. Edit ```vcap-local.json``` and update the credentials for the Cloudant. You can retrieve the service credentials from the Bluemix console.

1. Run

  ```
  npm install
  ```

1. Run

  ```
  npm start
  ```

## Contribute

If you find a bug, please report it via the [Issues section][issues_url] or even better, fork the project and submit a pull request with your fix! We are more than happy to accept external contributions to this project if they address something noted in an existing issue.  In order to be considered, pull requests must pass the initial [Travis CI][travis_url] build and/or add substantial value to the sample application.

## Troubleshooting

The primary source of debugging information for your Bluemix app is the logs. To see them, run the following command using the Cloud Foundry CLI:

  ```
  $ cf logs fintrade --recent
  ```

For more detailed information on troubleshooting your application, see the [Troubleshooting section](https://www.ng.bluemix.net/docs/troubleshoot/tr.html) in the Bluemix documentation.

## License

See [License.txt](License.txt) for license information.

# Privacy Notice

This application is configured to track deployments to [IBM Bluemix](http://www.ibm.com/cloud-computing/bluemix/) and other Cloud Foundry platforms. The following information is sent to a [Deployment Tracker](https://github.com/IBM-Bluemix/cf-deployment-tracker-service) service on each deployment:

* Node.js package version
* Node.js repository URL
* Application Name (`application_name`)
* Space ID (`space_id`)
* Application Version (`application_version`)
* Application URIs (`application_uris`)
* Labels of bound services
* Number of instances for each bound service and associated plan information

This data is collected from the `package.json` file in the application and the `VCAP_APPLICATION` and `VCAP_SERVICES` environment variables in IBM Bluemix and other Cloud Foundry platforms. This data is used by IBM to track metrics around deployments of sample applications to IBM Bluemix to measure the usefulness of our examples, so that we can continuously improve the content we offer to you. Only deployments of sample applications that include code to ping the Deployment Tracker service will be tracked.

## Disabling Deployment Tracking

Deployment tracking can be disabled by removing `require("cf-deployment-tracker-client").track();` from the beginning of the `app.js` file.

[cloud_foundry_url]: https://github.com/cloudfoundry/cli
[download_node_url]: https://nodejs.org/download/
[travis_url]: https://travis-ci.org/
