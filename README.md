# Receiptify: Split the Bill

Receiptify: Split the Bill is inspired by the original Receiptify, a web application that generates receipts that lists out a user's top tracks in the past, month, 6 months, and all time. Our version of receiptify generates receipts based on a group of users in a session. Our application generates a combined music receipt that displays a compiled list of all users' top tracks in the past, month, 6 months, and all time.

Web application inspired by https://www.instagram.com/albumreceipts/. Generates receipts that list out a user's top tracks in the past month, 6 months, and all time.

The application inspired by https://receiptify.herokuapp.com/. Generates receipts on a website for a single user's spotify data.

## Hosting the App Locally

This app runs on Node.js. On [its website](http://www.nodejs.org/download/) you can find instructions on how to install it. You can also follow [this gist](https://gist.github.com/isaacs/579814) for a quick and easy way to install Node.js and npm.

Once installed, clone the repository and install its dependencies running:

    $ npm install

### Using your own credentials

You will need to register your app and get your own credentials from the Spotify for Developers Dashboard.

To do so, go to [your Spotify for Developers Dashboard](https://beta.developer.spotify.com/dashboard) and create your application. In my own development process, I registered these Redirect URIs:

- http://localhost:3000 (needed for the implicit grant flow)
- http://localhost:3000/callback

Once you have created your app, change the `client_id` and `client_secret` values in the a `app.js` file to your own Spotify Developer credentials.

In order to run the app, open the folder, and run its `app.js` file:

    $ node app.js

Then, open `http://localhost:3000` in a browser.

To allow users to access your app, you need to add their names and emails under user managment from the Spotify for Developers Dashboard.

When hosting, set the Redirect URI as:
- http://[serverIP]:3000 (needed for implicit grant flow)
- http://[serverIP]:3000/callback

Setting Redirect URI as http://localhost:3000/callback when trying to host the application for local clients to connect to will fail because the redirect URI points to the client's IP address (localhost).

## Joining the App Locally

A user on the same network the app is hosted on can put the host's IP and port number into their browser (ex. 10.188.203.159:3000).

The first person will click the "Create Session" button and log into their Spotify account. A Session ID will appear on the top of their receipt.

Other users can then click "Join Session" and after entering the shared Session ID, they can log into their Spotify accounts and view the receipt.


