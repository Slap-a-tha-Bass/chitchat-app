# Chitchat-App

&nbsp;

## 📁 Table of Contents

- [🧠 Purpose](#-purpose)
- [👟 Running the Project](#-running-the-project)
- [💬 Server](#-server)
- [💻 Client](#-client)
- [🙌 Styling the App](#-styling-the-app)
- [🔐 Closing Remarks](#-closing-remarks)

&nbsp;

## 🧠 Purpose

This project is my first attempt at creating a functional live-chat room using socket.io!

There will be custom styling involved to make it a fun experience for the user. Could be applicable for a chess chat, or for a help IT desk. Whichever I end up doing will still be a good experience learning this technology.

&nbsp;

## 👟 Running the Project

If you already know the process of cloning a repository then follow the normal process and use the script `npm run dev` to get up and going!

If you're new or are interested in the steps and their purpose, then let's dive on in!

&nbsp;

1st:

```bash
git clone https://github.com/Slap-a-tha-Bass/chitchat-app YOUR_PROJECT_NAME
```

This command will "clone" this project's code to _our_ computers! It will default to the name of the GitHub repository, but you can rename it by providing an additional argument, like `YOUR_PROJECT_NAME` in the above example. It will create a folder by that name, and copy all the juicy code into it for you!

&nbsp;

2nd:

```bash
cd YOUR_PROJECT_NAME
```

Hopefully, this one is fairly straightforward by this point.

&nbsp;

3rd:

```bash
npm install
```

This will make `package.json` and `package-lock.json` files to install the needed dependencies for this project to do its job. It will create your `node_modules` folder for you which is what lets the project run.

- Note that sometimes you'll see security vulnerabilities. These will come and go and thankfully are easy to fix. `npm audit fix` can do so by updating an out-of-date package to a new version. However, alot of these free packages are written in the spare time of other developers and you're at the mercy of waiting for them to fix the vulnerability.

&nbsp;

4th:

```bash
npm run dev
```

This command will start the project for us!

- This script will utilize `nodemon` to auto-restart your Express server, meaning any server side code you write and save will trigger a recompile, rebundle, and re-run of the server! No need to stop and restart it over and over again.
- Notice in the `package.json` that `dev` runs `"npm-run-all --parallel watch:*"` as the actual command. It's what fires up 1) `webpack` to compile and bundle our code and 2) run `nodemon` when the server finishes building!
  - The `npm-run-all` lets us run run multiple npm-scripts in parallel or sequentialy.
  - `--parallel` means we run two npm-scripts at the same time.
  - `watch:*` references any other script starting with `watch:`, check out the two in our `package.json`! They are `watch:build` and `watch:server`.
    - Another indent level? 😤 Sheesh. But let's break down the purpose of those watch scripts!
    - `watch:build` will tell webpack to compile and bundle our `src/client` folder as all of our React app and output it to `public/js/app.js`. It will also follow the same process for `src/server` and output it to `dist/server.js`
    - `watch:server` watches the `dist/server.js` for changes and that's how it auto-restarts the server! Unfortunately you'll have to refresh your browser to see any React app changes.

&nbsp;

**The server will start on port 3000 (http://localhost:3000).**

&nbsp;

Optionally:

```bash
npm run start
```

We will use this script in production. We don't need all the auto-restart stuff from the `watch:*` scripts we discussed up above. Just start the server and be done with it.

- This assumes you have a `dist/server.js` and `public/js/app.js` already built.

&nbsp;

## 💬 Server

The server build process compiles the TypeScript files found in `src/server` into a single bundled JavaScript file (`server.js`) located in the `dist` directory, which is created for us during the process.

This will be where we code all things relating to our database, whether SQL or NoSQL. It's where we'll include all of our REST API routes.

&nbsp;

## 💻 Client

The client build process compiles the TypeScript files found in `src/client` into a single bundled JavaScript file (`app.js`) located in the `public/js/` directory, which is created for us during the process.

This will be where we code all things related to our React app and what a user will see and interact with in the browser. That's it. If it needs to ask for any information on the back-end, you will 99% of the time do so via a `fetch` request that hits one of your REST API endpoints.

&nbsp;

#### 🙌 Styling the App

I will be using styled-components for this app.

&nbsp;

## 🔐 Closing Remarks

I'm always trying to learn something new by building projects with newly integrated technologies. 

In this case it is socket.io, which I have never used before, so I'm bound to screw it up!

If you like what I make, simply follow me on Github or just clone what I have and make it even better.
