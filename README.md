#Description

This tools enables you to detect visual regressions in your website.
You define a list of urls in **test-config.json**.

For the first time, you can defined your pre-production website as the reference.

Once you made some change in your source code, you run the UI test to see the changes.

If UI modifications detected by the tool are OK, you can set up a new UI reference.


#Installation

``
npm install
``

#Set up a reference

``
gulp backstop_reference
``

#Run UI test

``
gulp backstop_test
``

#Maven integration

After you have defined a reference with **gulp backstop_reference**, you can integrate in your **pom.xml** file, the plugin **exec-maven-plugin** as it is described in the pom.xml here.