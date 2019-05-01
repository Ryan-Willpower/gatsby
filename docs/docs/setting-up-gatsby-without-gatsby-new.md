## Setting Up a Gatsby Site Without Gatsby New

There are many Enterprise level companies that maintain an internal clone of the NPM registry for security purposes. If you work for such a company, you may find that you are able to successfully run `npm install -g gatsby-cli` but cannot run the `gatsby new <project-source>` as the `gatsby new` command clones a repo from a public GitHub repository. Many companies block public GitHub, which will cause the `gatsby new` command to fail. Not to worry, though, you can set up a new Gatsby site without the `gatsby new` command with a few quick steps.

First, you'll want to set up a new project folder.
```shell
mkdir my-new-gatsby-site
cd my-new-gatsby-site
```

Next, you'll need to set up NPM within your project.
```shell
npm init
```

Fill out the prompts for the package.json file that is generated. If you'd like to skip that, you can run `npm init -y` and a pre-filled package.json will be generated for you.

Now, you'll need to install the neccessary packages that Gatsby relies on to work its magic.
```shell
npm i gatsby react react-dom
```

Once your packages have installed, you'll likely want to add some of the Gatsby specific files at the root of your project.
```shell
touch gatsby-config.js
touch gatsby-browser.js
```

Next, you'll add a `src` directory and a `pages` directory inside of that. 
```shell
mkdir src
cd src
mkdir pages
```

Inside the pages directory, you'll make an `index.js` file that exports a React component.
```shell
cd pages
touch index.js
```

Now, add some React code to your `index.js` file as a starting point for your project.
```jsx:title=src/pages/index.js
import React from 'react';

export default () => (
  <h1>Hello Gatsby!</h1>
);
```

Finally, go back to the root of your project and run the `gatsby develop` command to start a development server and begin coding.
```shell
cd ../../ 
gatsby develop
```

And that's it! You should now have your initial page running on `localhost:8000` with a GraphiQL IDE running on `localhost:8000/___graphql`. From here, you can follow the rest of the [Gatsby tutorial](https://www.gatsbyjs.org/tutorial/part-zero/#set-up-a-code-editor) starting with setting up a code editor to get the full experience of what Gatsby can offer.  