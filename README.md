# ClientJS [![Sauce Test Status](https://saucelabs.com/buildstatus/clientjs)](https://saucelabs.com/u/clientjs) [![Build Status](http://beta.drone.io/api/badges/jackspirou/clientjs/status.svg)](http://beta.drone.io/jackspirou/clientjs) [![Aircover Coverage](https://aircover.co/badges/jackspirou/clientjs/coverage.svg)](https://aircover.co/jackspirou/clientjs) [![Join the chat at https://gitter.im/jackspirou/clientjs](https://badges.gitter.im/jackspirou/clientjs.svg)](https://gitter.im/jackspirou/clientjs?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

**Device information and digital fingerprinting written in _pure JavaScript_.**

[![Sauce Test Status](https://saucelabs.com/browser-matrix/clientjs.svg)](https://saucelabs.com/u/clientjs)


ClientJS is a JavaScript library that makes digital fingerprinting easy, while also exposing all the browser data-points used in generating fingerprints.

If you want to fingerprint browsers, you are **_probably_** also interested in other client-based information, such as screen resolution, operating system, browser type, device type, and much more.

Below are some features that make ClientJS different from other fingerprinting libraries:
- It's pure native JavaScript
- It's decently lightweight at 43 KB
- All user data points are available by design, not just the 32bit integer fingerprint

## Docs/Demo
You can find more documentation on ClientJS at [clientjs.org](https://clientjs.org/). Also there is an example/demo.

## Installation
To use ClientJS, simply include the `client.min.js` file found in the `dist` directory, so `dist/client.min.js` when your in the project root directory.

ClientJS is avalaible via [bower](http://bower.io/search/?q=clientjs) and [npm](https://www.npmjs.com/package/clientjs).

### npm
ClientJS is available via npm.

```shell
npm install clientjs
```

### Bower
ClientJS is also available as a bower package.

```shell
bower install clientjs
```

## Fingerprinting
Digital fingerprints are based on device/browser settings. They allow you to make an "educated guess" about the identify of a new or returning visitor. By taking multiple data points, combining them, and representing them as a number, you can be surprisingly accurate at recognizing not only browsers and devices, but also individual users.

This is useful for identifying users/devices without cookies or sessions. It is not a full proof technique, but it has been shown to be statistically significant at accurately identifying devices.

Simply create a new ClientJS object. Then call the `getFingerprint()` method which will return the browser/device fingerprint as a 32bit integer hash ID.

Below is an example of how to generate and display a fingerprint:

```javascript
// Create a new ClientJS object
var client = new ClientJS();

// Get the client's fingerprint id
var fingerprint = client.getFingerprint();

// Print the 32bit hash id to the console
console.log(fingerprint);
```

The current data-points that used to generate fingerprint 32bit integer hash ID is listed below:
- user agent
- screen print
- color depth
- current resolution
- available resolution
- device XDPI
- device YDPI
- plugin list
- font list
- local storage
- session storage
- timezone
- language
- system language
- cookies
- canvas print

## Available Methods
Below is the current list of available methods to find information on a users browser/device.

You can find documentation on each method at [clientjs.org](https://clientjs.org/).

```
  var client = new ClientJS();

  client.getBrowserData();
  client.getFingerprint();
  client.getCustomFingerprint(...);

  client.getUserAgent();
  client.getUserAgentLowerCase();

  client.getBrowser();
  client.getBrowserVersion();
  client.getBrowserMajorVersion();
  client.isIE();
  client.isChrome();
  client.isFirefox();
  client.isSafari();
  client.isOpera();

  client.getEngine();
  client.getEngineVersion();

  client.getOS();
  client.getOSVersion();
  client.isWindows();
  client.isMac();
  client.isLinux();
  client.isUbuntu();
  client.isSolaris();

  client.getDevice();
  client.getDeviceType();
  client.getDeviceVendor();

  client.getCPU();

  client.isMobile();
  client.isMobileMajor();
  client.isMobileAndroid();
  client.isMobileOpera();
  client.isMobileWindows();
  client.isMobileBlackBerry();

  client.isMobileIOS();
  client.isIphone();
  client.isIpad();
  client.isIpod();

  client.getScreenPrint();
  client.getColorDepth();
  client.getCurrentResolution();
  client.getAvailableResolution();
  client.getDeviceXDPI();
  client.getDeviceYDPI();

  client.getPlugins();
  client.isJava();
  client.getJavaVersion();
  client.isFlash();
  client.getFlashVersion();
  client.isSilverlight();
  client.getSilverlightVersion();

  client.getMimeTypes();
  client.isMimeTypes();

  client.isFont();
  client.getFonts();

  client.isLocalStorage();
  client.isSessionStorage();
  client.isCookie();

  client.getTimeZone();

  client.getLanguage();
  client.getSystemLanguage();

  client.isCanvas();
  client.getCanvasPrint();
```

## Shoulders of Giants
It is important to note that this project owes much to many other pieces of work. I had the advantage of searching through how many others have approached this problem before me.

Built Upon:
- https:github.com/Valve/fingerprintjs
- http:darkwavetech.com/device_fingerprint.html
- detectmobilebrowsers.com

## Vendor Code
All dependencies are automatically included into `client.min.js` when the `build.sh` file compiles this project. They do not need to be included separately.

Dependencies Include:
- ua-parser.js
- fontdetect.js
- swfobject.js
- murmurhash3.js

## Contributing
Begin to colaborate by [forking](https://help.github.com/articles/fork-a-repo/) this repository.

Once you have cloned the project, install all node dependencies. ClientJS uses [Karma](https://karma-runner.github.io/0.13/index.html) as its testing environment.

```shell
# Install dependencies
$ npm install

# If you want tu run karma from the command line
$ npm install -g karma-cli
```

Run Karma and enjoy coding!

```shell
$ karma start
```

Thanks for contribute to ClientJS! Please report any bug [here](https://github.com/jackspirou/clientjs/issues).

## LICENSE
This project is using the GNU GENERAL PUBLIC LICENSE. It is included in the project source code.
