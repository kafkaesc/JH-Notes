# Deploy a React App to GithHub Pages

## Prerequisites

1. [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) is installed
1. [Node.js and npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) are installed
1. A [GitHub](https://github.com) account
1. A [React](https://reactjs.org) project (to deploy!)
1. [VS Code](https://code.visualstudio.com), the IDE of your choice, or just use the vim codes in these notes

## Setup

1. Use the terminal to navigate to the folder for your React project
1. Run `npm install gh-pages --save-dev` to install the `gh-pages` npm package
1. Open the `package.json` file in your IDE or run `vim package.json` in the terminal.
1. Add `"homepage": "https://{GitHubUsername}.github.io/{ProjectName}/",` under the name and version key-value pairs, where GitHubUsername is your GitHUb username and ProjectName is the name of your project repository.
1. In the scripts section of the same `package.json` file add the predeploy and deploy scripts:

        "predeploy": "",
				"deploy": "gh-pages -d build",

1. Open your project repository at [github.com](https://github.com)
1. Click the tab labeled "Settings"
1. Click the "Pages" link in the left sidebar
1. In the "Build and deployment" section select "Deploy from a branch" for source, then select `gh-pages` and `./ (root)` for your branch and folder.
1. Click "Save"

Now that the setup is complete, run `npm run deploy`. In about 2 minutes you should be able to see your React project deployed at your GitHub pages URL.

## Routing Complications

If you are using the more common routers from [React Router](https://reactrouter.com) you might get some messy behavior from GitHub pages: getting 404s trying to go directly to most routes or having to visit the base URL to get the app to load. In my experience you will have to use the [hash router](https://reactrouter.com/en/main/router-components/hash-router) to get correct routing behavior. Details for that to come.
