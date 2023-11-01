# Create a Remix app with Tailwind

By Jared Hettinger

## Prerequisites

1. [VSCode](https://code.visualstudio.com) is installed
1. [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) is installed
1. [Node.js and npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) are installed
1. A [GitHub](https://github.com) account

## Setting Up the Project with Create React App

1. In the terminal, navigate to the directory where you want the project
1. Run `npx create-remix@latest project-name`
1. Run `cd project-name` to move into the newly created folder

## Install Tailwind

1. Run `npm install -D tailwindcss`
1. Run `npx tailwindcss init --ts`
1. Open the project folder in VS Code
1. Open `tailwind.config.ts` and add `'./app/**/*.{js,jsx,ts,tsx}'` onto the content array
1. Create an `/app/tailwind.css` file
1. Add to the new `tailwind.css` file:

        @tailwind base;
        @tailwind components;
        @tailwind utilities;

1. Open `/app/root.tsx`
1. Import the CSS file `import stylesheet from "~/tailwind.css";`
1. Set it in the page links by including `{ rel: "stylesheet", href: stylesheet },` in the links function variable
