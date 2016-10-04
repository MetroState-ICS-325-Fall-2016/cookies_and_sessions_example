Cookies and Sessions Lab
=========================

Purpose
-------
* Learn how cookies and PHP sessions work.
* Use PHP sessions as part of a simple PHP program.
* Review the basics of using HTML forms and PHP together
* Review how to embed PHP in HTML

Resources and Examples
----------------------
* Chapter 10 in the text.
* The official PHP.net [documentation](http://php.net/manual/en/features.cookies.php) for cookies in PHP.
* The official PHP.net [documentation](http://php.net/manual/en/features.sessions.php) for sessions in PHP.
* w3schools.com has a good basic overview of HTML forms [here](http://www.w3schools.com/html/html_forms.asp).

Prerequisites
-------------
Use git to clone the public cookies and session lab to your computer.  Then in PhpStorm, use `File->Open Directory` and select your local repo.

Instructions
------------
### Instructions to set up the code to run
First you need to clone your git repository to your computer.  Open GitKraken and make sure you are logged into your github.com account.  Next go to `File->Clone Repo`.  Select the `GitHub.com` icon.  A list of your repositories in github.com should pop up.  Select the one for cookies and sessions lab.  If you want, change `Where to clone to` by clicking browser and selecting a folder for your git repo to be cloned into.  Finally, hit the `Clone the repo!` button.  The repo should now clone to your computer.

Next you need to set up PhpStorm.  We will be using the built-in PHP CGI server for this assignment.  To do so, first make sure you have the git repo open in PhpStorm by using the Open Directory menu item under File in PhpStorm (`File->Open Directory`).  Next go to `Run->Edit Configurations...` Click the green `+` to create a new configuration.  Select `PHP Built-in Web Server`.  Change the name to `Cookies and Sessions Lab`.  Leave host as `localhost`.  Set the port to `8080`.  Set the `Document root` to your git repo directory by clicking the `...` button next to the field and using the file chooser to select it.  If there is a red ! icon near the bottom right of the window, click the `Fix` button and specify your PHP interpreter.  Once done, click `Ok` to exit the Edit Configurations window.  Next hit the green run button to start the PHP CGI web server.  Then go to your web browser and enter this url [http://localhost:8080/cookies_sessions_example.php](http://localhost:8080/cookies_sessions_example.php).  

The output from  `cookies_sessions_example.php` is broken down into 4 sections:
* Test Cookies and Sessions: Allows you to control the actions taken on cookies and sessions.
* Messages: Reports the action the PHP script took.
* Cookies Sent by Browser: The cookies the browser sent to the PHP script.
* PHP Session Data: The session data the PHP script had access to when it rendered the page.

In addition, there is a link on that page you can use to change the form submission type from POST to GET.

### Things to try
Open the developer tools built into your web browser and go to the network section.  You will need to look at the request and response headers.  Here are links on how to do that for [Firefox](https://developer.mozilla.org/en-US/docs/Tools/Network_Monitor) and [Chrome](http://stackoverflow.com/questions/4423061/view-http-headers-in-google-chrome).

Then go through the following steps:
1.  With the developer network tools open, fill in:
  * First Name
  * Last Name
  * Age
  * Gender
  * Select Set Cookie.
2. Hit submit.
3. Look at the response headers.  You should see Set-Cookie= followed by the data you entered.  This is the server telling your web browser to set a cookie.
4. Make sure that Do Nothing is selected for Cookie Action.  Then hit submit.
5. Look at the request headers.  You should see Cookie= followed by the data you entered.  That is your web browser sending the cookie back to the server.

Investigate the following questions by experimenting with the form and/or looking at the source code:
1. Which is available to the PHP script immediately after it is set (within the same running script): cookies or sessions?
2. When the web browser sends a cookie to the PHP script, and the PHP script deletes the cookie, is the original cookie available to the PHP script still?
3. What is the difference between Delete Session and Clear & Delete Session?

The source code is commented to explain how it works.  Review the source code to see how it differs from the program in Chapter 7 (assignment 4).  This PHP script uses HTML forms that are static and not dynamically generated by PHP.  In addition, the form can accept both GET and POST requests because it uses the `$_REQUEST` global variable.  You can experiment with the form using GET instead of POST by clicking on the link on that page that switches the form to using GET (only for the current request, you have to click it every time before you submit the form).  While reviewing the code, pay particular attention to the differences between how cookies are used in the code versus sessions.

Grading
-------
There is no work to be turned in for this lab.  It is not graded.
