## Installing Node.js (via nvm)

Node.js is a javascript runtime that, in addition to being one of the most widely adopted and versatile runtimes, is also a requirement for .. say, a working [Aurelia](http://aurelia.io/) application! Read more about [Node.js](https://nodejs.org/)

To install node (on Mac) it's considered a good practice to use **nvm** _(**n**ode **v**ersion **m**anager)_ - and it's easy!

### Remove old versions of Node

If you had an existing version of Node.js you might want to remove them in favor of the version manager we'll install in the next step.

This isn't too tricky to do, but as of this writing there's no official uninstall tool to do it for you. (steps credit of [tancredi on SO](http://stackoverflow.com/a/11178106))

1. go to `/usr/local/lib` and delete any `node` and `node_modules` directories
1. go to `/usr/local/include` and delete any `node` and `node_modules` directories
1. if you installed with `brew install node`, then run `brew uninstall node` in your terminal
1. check your Home directory for any `local` or `lib` or `include` folders, and delete any `node` or `node_modules` from there
1. go to `/usr/local/bin` and delete any `node` executable

Once node is gone we're ready for the nvm.

### Install the Node Version Manager (nvm)
***WHY?*** It lets you easily swap between versions of node, and, for me, it was the only install I could get to properly work without having to `sudo` the heck out of everything.

If you're on **mac/linux** this can be done right from the commandline by running the install script from github

```
curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | sh
```
Part of the install will inject the `NVM_PATH` variable into your `bash_profile` so if running `nvm` doesn't immediately work, just log out and then back in to pick up the profile changes.

If you're on **windows** you'll have to hit Google for answers as there's no official version of nvm for windows (unless it says otherwise [here](https://github.com/creationix/nvm#installation))

Now try running `nvm` from the commandline. You should get something like the following.

```
Node Version Manager

Note: <version> refers to any version-like string nvm understands. This includes:
  - full or partial version numbers, starting with an optional "v" (0.10, v0.1.2, v1)
  - default (built-in) aliases: node, stable, unstable, iojs, system
  - custom aliases you define with `nvm alias foo`

Usage:
  nvm help                              Show this message
  nvm --version                         Print latest released version of nvm
  nvm install [-s] <version>            Download and install a <version>, 
  nvm uninstall <version>               Uninstall a version
  ...
```

If `nvm` does nothing, look for errors from the install, and don't forget to log out/in of your computer to pick up the path changes (i.e. from `/Users/YourName/.bash_profile`)

### Install the latest version of Node.js

At this point you should have the `nvm` installed and working. Now it's time to install Node.js itself.

Check the [official Node.js site](https://nodejs.org/) for the latest version number - it should be pretty obvious (albiet small) - as we'll use it when telling the **nvm** what to install.

At the time of this writing it was `Current Version: v0.12.7`

Now, back in terminal, run `nvm install <version>` and give it the version number

```
nvm install v0.12.7
```
You should see something like this...

```
CWB-MBP:test DeepThought$ nvm install v0.12.7
######################################################################## 100.0%
Now using node v0.12.7 (npm v2.11.3)
```

Test it out by running `node` - you should get the node runtime - (`ctrl+c` twice to quit)

```
CWB-MBP:test DeepThought$ node
> 
(^C again to quit)
> 
CWB-MBP:test DeepThought$ 
```

## Done
That's it! You should have a working, `sudo`-free version of NodeJs and the used-for-dang-near-everything `npm` _(**n**ode **p**ackage **m**anager)_
