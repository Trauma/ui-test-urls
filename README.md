# Description

[Forked from Alexandre-Gadiou/ui-test-urls
](https://github.com/Alexandre-Gadiou/ui-test-urls)

This tool, based on [BackstopJS][62712fdc], enables you to detect visual regressions with screenshots comparision.

  [62712fdc]: https://github.com/garris/BackstopJS "BackstopJS"

# Installation

Pre-requisites: [Chrome][c49f6796] browser must be installed

  [c49f6796]: https://www.google.com/intl/fr-FR/chrome/ "chrome"

If not already, install nodeJS :

``
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
``

Then clone this repository, `cd` into it and run :

``
npm install
``

# Testings

Define the target urls you want to test in the ``urls.json`` file.

Then run ``npm run test`` in your terminal. Once the tests are passed your browser should popup. Review the screenshots, if everthing is ok then you must set them as references.

If not you can tune backstopJS settings in the `backstop-config.js` file look at the `scenariosArray` block. Please also refere to backstopJS documentation. In these setup backstopJS config object is define as a node module inside a .js file in order to iterate through all the target urls.

# Set the references

In order to approve the previous test run, an therefor make it the new reference, run ``npm run approve`` in your terminal. The reference hence is name will be the comparision reference for the next tests.

# Jenkins integration

Use the Jenkinsfile provided in a pipe-line job. The jenkins build agent must have nodeJS and chrome installed.
