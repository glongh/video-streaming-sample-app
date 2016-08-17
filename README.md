# Ricoh Video Streaming Samples

### Two-way video streaming

* [Video Chat Sample](https://github.com/ricohapi/video-streaming-sample-app/tree/master/samples/twoway).

### One-way video streaming

* [Broadcast Sample](https://github.com/ricohapi/video-streaming-sample-app/tree/master/samples/oneway-broadcast).
* [Watch Sample](https://github.com/ricohapi/video-streaming-sample-app/tree/master/samples/oneway-watch).

---

## Additional Information

### RICOH Cloud API Seminar 1

* [Video part 1](https://youtu.be/bih-9dIXG-g)
* [Video part 2](https://youtu.be/ZyW0FUoFYcw)
* [Video part 3](https://youtu.be/Z_2PZ4PWe6g)
* [Slides](http://www.slideshare.net/contest-theta360/ricoh-theta-x-iot-developers-contest-cloud-api-seminar)

### RICOH Cloud API Seminar 2
* [Video](https://youtu.be/jEecgbMzjds)
* [Slides](http://www.slideshare.net/contest-theta360/ricoh-theta-x-iot-developers-contest-cloud-api-seminar-2nd-installation)

---

You can  live stream 360 video between two computers using a browser. The video stream has  full 360 degree navigation, enabling 360 video conferencing between two people.

<img src="http://lists.theta360.guide/uploads/default/optimized/1X/828b771767ac761f79e9a162dd23fe093d8f1a0e_1_605x500.png" width="605" height="500">

The magic happens with WebRTC. A functional sample application is available with source code. WebRTC requires an external server for signaling. In this guide, we use the RICOH Cloud API server for signaling. [Free accounts](http://theta360.guide/contest/signup_cloudapi.html) are available. The video data is sent between the two browsers and does not travel to the signaling server. In addition to a login to the signaling server, you will need API keys. These are also freely available. Refer to the link above for more information.

## Download [live streaming code from GitHub](https://github.com/ricohapi/video-streaming-sample-app).

Note that if you don't have git installed and don't know how to install it from the command line, you can download the [GitHub Desktop](https://desktop.github.com/).

Follow the steps and get going.

    $ git clone https://github.com/ricohapi/video-streaming-sample-app.git
    $ cd video-streaming-sample-app/samples

Remain in the directory `samples`

    $ cp config_template.js config.js

Put your credentials into `config.js`  The sample application uses the RICOH Cloud as the [signaling server](http://www.tutorialspoint.com/webrtc/webrtc_signaling.htm). You may be able to modify the source code of the sample application and build your own signaling server. For simplicity, this example focuses on using the free RICOH Cloud as the signaling server.

The credentials you get from the RICOH Cloud API server look like this.

<img src="http://lists.theta360.guide/uploads/default/original/1X/2e0c96df53044b1d0e90cbc2c3c4ec704d677572.png" width="530" height="51">

If you don't have your free API key credentials for signaling, read this [RICOH Cloud API signup guide](http://theta360.guide/contest/signup_cloudapi.html).

    $ npm install

When you run `npm install`, there will be warnings. Ignore them. I've tested Mac and Windows 10 with nodejs downloaded from the main nodejs.org site and the sample application ran with no problem. I've also tested it on Ubuntu 16.04 with both the node installed with `apt install nodejs` as well as the more recent version of node installed from the nodejs.org site.

    $ npm run build

Go into the directory `twoway`

    $ pwd
    .../video-streaming-sample-app/samples/twoway

If you try running

    $ npm start

and you see the error message about `gulp: not found`, then adjust your `PATH` for `gulp`

### gulp error message

        $ npm start

        > @ start /home/craig/Documents/Accounts/ricoh/cloudApi/video-streaming-sample-app/samples/twoway
        > gulp server

        sh: 1: gulp: not found

        npm ERR! Linux 4.4.0-28-generic
        npm ERR! argv "/usr/bin/nodejs" "/usr/bin/npm" "start"
        npm ERR! node v4.2.6
        npm ERR! npm  v3.5.2
        npm ERR! file sh
        npm ERR! code ELIFECYCLE
        npm ERR! errno ENOENT
        npm ERR! syscall spawn
        npm ERR! @ start: `gulp server`
        npm ERR! spawn ENOENT
        npm ERR!
        npm ERR! Failed at the @ start script 'gulp server'.
        npm ERR! Make sure you have the latest version of node.js and npm installed.
        npm ERR! If you do, this is most likely a problem with the  package,
        npm ERR! not with npm itself.
        npm ERR! Tell the author that this fails on your system:
        npm ERR!     gulp server
        npm ERR! You can get information on how to open an issue for this project with:
        npm ERR!     npm bugs
        npm ERR! Or if that isn't available, you can get their info via:
        npm ERR!     npm owner ls
        npm ERR! There is likely additional logging output above.


### adjusting path to find gulp

If your system can't find `gulp`, then do this:

    $ npm bin

It will return your path, probably something like this:

    /home/ricoh/Development/livestream/video-streaming-sample-app/samples/node_modules/.bin

Add the PATH for  [gulp](https://www.npmjs.com/package/gulp).

On Linux systems, this will look similar to this:

     export PATH=$PATH: /home/ricoh/Development/livestream/video-streaming-sample-app/samples/node_modules/.bin

I've tested this on Windows 10, Linux Ubuntu 16.04, and Mac. In all cases, I needed to specify the PATH.

After the PATH environmental variable is set, then run `npm start` again.

    $ npm start

    > @ start /home/craig/Documents/Accounts/ricoh/cloudApi/video-streaming-sample-app/samples/twoway
    > gulp server

    (node:24274) fs: re-evaluating native module sources is not supported. If you are using the graceful-fs module, please update it to a more recent version.
    [15:51:30] Using gulpfile ~/Documents/Accounts/ricoh/cloudApi/video-streaming-sample-app/samples/twoway/gulpfile.js
    [15:51:30] Starting 'server'...
    [15:51:30] Webserver started at http://localhost:8034
    [15:51:30] Finished 'server' after 9.61 ms



It will automatically open up a browser. RICOH recommends Google Chrome 51 or
newer. I also used Mozilla Firefox 47, which is the recommended version.

Select RICOH THETA S as the device.

![](http://lists.theta360.guide/uploads/default/original/1X/9035458e84ec20c90405b99abd2a0f2ca23d5860.png)

Log in with your modified RICOH username and password.

<img src="http://lists.theta360.guide/uploads/default/optimized/1X/6dadebae7bc7b7f02761f5f3be0efc725fca0a1b_1_677x500.png" width="677" height="500">


If you don't have a RICOH User account, refer to this [guide](http://theta360.guide/contest/signup_cloudapi.html).

<img src='http://lists.theta360.guide/uploads/default/optimized/1X/24a8084bfaf198ee32f794c315752a55c1b65940_1_690x354.png'>

To set up a peer-to-peer connection, use a Ricoh user ID with a plus sign and
string after it. For example, `craig@oppkey.com+01` or `craig@oppkey.com+theta`.

![](http://lists.theta360.guide/uploads/default/optimized/1X/375b97622500b289b8321dcd1b0b03a14bc73270_1_690x492.png)

In this example, I am using Chrome in two different tabs on the same computer. In the screenshot at the top of this section, the THETA is connected to one USB port of my Windows computer and another webcam (not a THETA) is
connected to another USB port on the same computer. The only reason I am only using one THETA is because I only have one THETA at my house.

I am using the THETA S driver, not UVC Blender. The preview window in the right of the browser is in dual fisheye.

![](http://lists.theta360.guide/uploads/default/original/1X/a2bda74eccf5b60ba142a2928b25233302c0d215.png)

Press the _THETA View Mode_ green button to convert the incoming dual-fisheye video stream into a equirectangular view with the JavaScript in your browser.

![](http://lists.theta360.guide/uploads/default/original/1X/d4258a742b70a7d44b361f6f2591e2f5d27b084b.png)

So cool! The view has full navigation.

![](http://lists.theta360.guide/uploads/default/optimized/1X/b60106c6d650da624a1704a5b49dcbeb4e3eeab4_1_554x500.png)


## Streaming 360 Video Directly Between Two computers

To stream 360 between two computers on the same network, run the samples code on each computer. Open up a Chrome browser (Firefox didn't work in my tests) on each computer. The sample application will look for a webcam
on each computer. If you only have one THETA, use your standard webcam, such as the one built into your laptop.

In my test network, I have the THETA connected to my Linux computer with a USB cable. My Linux computer is connected to my home router with WiFi on a private IP address in subnet 192.168.1.0. The router is connected to the Internet. Remember, Firefox on Linux did not work for me, only Chrome.

![](http://lists.theta360.guide/uploads/default/optimized/1X/48e4f999eec929ac8401c02621c3f2958a6e8468_1_690x365.png)

I have a second Windows 10 computer on the same subnet connected with Ethernet.

![](/uploads/default/original/1X/e64fb4d52f66132fcea47f41d8e25c70c3e568c6.png)

Here's how the network looks.

![](/uploads/default/original/1X/9687f904fa32bf0b1bda665284d7908e9a86e7e9.png)

Here's what your screen may look like.

https://www.youtube.com/watch?v=gnZ9IcqHruA

I've had problems connecting from Linux to Windows with the default firewall settings on Windows. If you have problems, turn off Windows firewall.  You only need to connect from *Computer A* to *Computer B*, this is enough to set up a video streaming connection from each computer. Similar to using Skype, only one person needs to initiate the connection and then two-way video conferencing is set up.

Here's a diagram of the streaming functionality of the application.
![](http://lists.theta360.guide/uploads/default/optimized/1X/c31047aa8a7bc5c85b1498592c96ba5fbbd23319_1_690x475.png)

Here's a diagram with some of the technology used.
![](http://lists.theta360.guide/uploads/default/optimized/1X/a45c78ac30c85ca8c893aae3091c862876838f87_1_690x471.png)



## Using WebRTC Between Two Computers on Separate Networks

To view the two 360 streams between two different computers on two separate networks (example: San Francisco and Palo Alto), you'll need to assign each computer a static IP address on the Internet (not NAT on an internal network) or use NAT traversal.

![](/uploads/default/original/1X/8c771e7dcc07ad4c8253cf7618bec0c8d2588601.png)

I have not tried NAT Traversal yet.

You can check out two untested services for STUN / TURN for NAT traversal here:

- Untested [Eyeball](http://www.eyeball.com/standards/stun-turn-ice/)
- Untested [Twilio](https://www.twilio.com/stun-turn/pricing)

Article on [WebRTC](http://www.html5rocks.com/en/tutorials/webrtc/infrastructure/)

We have a [full slide deck about the RICOH Cloud API](http://lists.theta360.guide/t/cloud-api-seminar-presentation-useful/22) available.

# [THETA Developer Ecosystem Registration](http://theta360.guide/ecosystem/)


![Analytics](https://ga-beacon.appspot.com/UA-73311422-5/ricoh-webrtc-sample)
