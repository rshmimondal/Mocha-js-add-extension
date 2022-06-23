# How to add extension for automation test in Mocha-js for [LambdaTest](https://www.lambdatest.com/?utm_source=github&utm_medium=repo&utm_campaign=Mocha-js-add-extension)

If your webapp requires an extension for automation test in Mocha-js on Lambdatest, you can use the following steps to upload extension and run your test. You can refer to sample test repo [here](https://github.com/LambdaTest/mocha-selenium-sample).

# Steps:
## Step 1: Get the zip file (Skip this if you already have the zip file with you)

Note: You will need the Chrome Extensions's ID for this. I am referring it to as $ID$. You can get the $ID$ from the URL of the Chrome Extension page.
1. Install your desired chrome extension on chrome.
2. Go to Chrome's Extensions page (chrome://extensions/), Enable the developer mode (check the developer mode box) and take note of the ID for your desired extension.
3. Your extension will be located at:

For Unix, ~/.config/google-chrome/Default/Extensions/$ID$

For Windows, C:\Users\<Your_User_Name>\AppData\Local\Google\Chrome\User Data\Default\Extensions\$ID$

For OSX, ~/Library/Application Support/Google/Chrome/Default/Extensions/$ID$

## Step 2: Upload the zip file to LamdbaTest using API

1. * [Use the LambdaTest extension upload API to upload the zip file to the backend.](https://www.lambdatest.com/support/api-doc/#/extensions/UploadExtensions)

2. Copy the link to your extension which will look something like - https://automation-prod-user-files.s3.amazonaws.com/extensions/orgId-XXXX/2.1.0_0.zip

## Step 3: Pass extension in capabilities

In `conf/single.conf.js` file, you need to update your capabilities. The capabilities object in the for the adding extension  are defined as:
```js
exports.capabilities = {
        'build': 'Mocha-Selenium-Sample', //Build name
        'name': 'Your Test Name', // Test name
        'platform':'Windows 10', // OS name
        'browserName': 'chrome', // Browser name
        'version': 'latest', // Browser version
        'visual': false,  // To take step by step screenshot
        'network':false,  // To capture network Logs
        'console':false, // To capture console logs.
        'tunnel': false, // If you want to run the localhost than change it to true
        "lambda:loadExtension": "https://automation-prod-user-files.s3.amazonaws.com/extensions/orgId-XXXX/2.1.0_0.zip"
};
```

## Run your test

```bash
npm run single
```

## Additional Links

* [Advanced Configuration for Capabilities](https://www.lambdatest.com/support/docs/selenium-automation-capabilities/)
* [How to test locally hosted apps](https://www.lambdatest.com/support/docs/testing-locally-hosted-pages/)
* [How to integrate LambdaTest with CI/CD](https://www.lambdatest.com/support/docs/integrations-with-ci-cd-tools/)

## Tutorials 📙

Check out our latest tutorials on JavaScript automation testing 👇

* [How To Generate Mocha Reports With Mochawesome?](https://www.lambdatest.com/blog/how-to-generate-mocha-reports-with-mochawesome/)
* [Mocha JavaScript Tutorial With Examples For Selenium Testing](https://www.lambdatest.com/blog/mocha-javascript-tutorial-with-examples-for-selenium-testing/)

## Documentation & Resources :books:
      
Visit the following links to learn more about LambdaTest's features, setup and tutorials around test automation, mobile app testing, responsive testing, and manual testing.

* [LambdaTest Documentation](https://www.lambdatest.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=mocha-js-add-extension)
* [LambdaTest Blog](https://www.lambdatest.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=mocha-js-add-extension)
* [LambdaTest Learning Hub](https://www.lambdatest.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=mocha-js-add-extension)    

## LambdaTest Community :busts_in_silhouette:

The [LambdaTest Community](https://community.lambdatest.com/) allows people to interact with tech enthusiasts. Connect, ask questions, and learn from tech-savvy people. Discuss best practises in web development, testing, and DevOps with professionals from across the globe 🌎

## What's New At LambdaTest ❓

To stay updated with the latest features and product add-ons, visit [Changelog](https://changelog.lambdatest.com/) 
      
## About LambdaTest

[LambdaTest](https://www.lambdatest.com/?utm_source=github&utm_medium=repo&utm_campaign=mocha-js-add-extension) is a leading test execution and orchestration platform that is fast, reliable, scalable, and secure. It allows users to run both manual and automated testing of web and mobile apps across 3000+ different browsers, operating systems, and real device combinations. Using LambdaTest, businesses can ensure quicker developer feedback and hence achieve faster go to market. Over 500 enterprises and 1 Million + users across 130+ countries rely on LambdaTest for their testing needs.    

### Features

* Run Selenium, Cypress, Puppeteer, Playwright, and Appium automation tests across 3000+ real desktop and mobile environments.
* Real-time cross browser testing on 3000+ environments.
* Test on Real device cloud
* Blazing fast test automation with HyperExecute
* Accelerate testing, shorten job times and get faster feedback on code changes with Test At Scale.
* Smart Visual Regression Testing on cloud
* 120+ third-party integrations with your favorite tool for CI/CD, Project Management, Codeless Automation, and more.
* Automated Screenshot testing across multiple browsers in a single click.
* Local testing of web and mobile apps.
* Online Accessibility Testing across 3000+ desktop and mobile browsers, browser versions, and operating systems.
* Geolocation testing of web and mobile apps across 53+ countries.
* LT Browser - for responsive testing across 50+ pre-installed mobile, tablets, desktop, and laptop viewports
    
[<img height="58" width="200" src="https://user-images.githubusercontent.com/70570645/171866795-52c11b49-0728-4229-b073-4b704209ddde.png">](https://accounts.lambdatest.com/register)
      
## We are here to help you :headphones:

* Got a query? we are available 24x7 to help. [Contact Us](support@lambdatest.com)
* For more info, visit - [LambdaTest](https://www.lambdatest.com/?utm_source=github&utm_medium=repo&utm_campaign=mocha-js-add-extension)
