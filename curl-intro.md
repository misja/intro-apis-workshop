# Start using cURL in the command line

In the [previous section](https://github.com/LearningNerd/intro-apis-workshop/blob/master/network-tab.md), we learned how to use the Network panel in Chrome's built in developer tools to see *all* of the request and response data being sent and received every time you access a web page. Next, let's use an even *more powerful* tool for making HTTP requests: [**cURL**](https://en.wikipedia.org/wiki/CURL)!

**cURL** is a command line tool for accessing and transferring data over the internet. It basically does what your web browser does, but without the graphical user interface, and with a LOT more control over how you send your requests!

![cURL logo](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Curl-logo.svg/320px-Curl-logo.svg.png)

  > **Fun fact:** The name cURL originally was pronounced "C - URL", as in "See URL", to see the data from any URL. But now we just pronounce it "curl" (like the weight lifting term, as in [bicep curls](https://en.wikipedia.org/wiki/Biceps_curl)).

<br/>

## Get your command line tool set up

It should only take a couple minutes to get things set up. :) Follow the instructions below:

<br/>

### Mac users:

If you're on a **Mac**: open the **Terminal** app to access your computer's command line. Easy!

  - You can search for "Terminal" in Finder or in Spotlight, wherever you normally search for things on your computer.

<br/>

### Windows users:

Windows also has a **Terminal** app, although it's installed by default only since Windows 11 (specifically since Windows 11 Release 22H2 ...).

  - Search for "Terminal" in your installed Apps, or wherever you normally search for things on your computer.
  - If you can't find the Terminal app, open Microsoft Store, search for Terminal and install it.

## Make your first cURL request

**Important** When using Windows you'll always need to type `curl.exe` instead of just `curl`. Microsoft is aware of this issue but they haven't created a solution for this yet ...

Copy-paste the code below into your command line, and then press Enter to request `example.com` using cURL:

```bash
curl http://example.com/
```

Compare the response body to the response you saw in the Network tab. ***Are they the same?***

<hr/>

:point_right: **Next up:** [**let's tackle a fun series of practice challenges using cURL to access some fun APIs!**](https://github.com/LearningNerd/intro-apis-workshop/blob/master/api-challenges-1.md)
