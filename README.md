# setup-project-with-webpack
Build a simple yet powerful webpack boilerplate, which I can later use as a starting point in your projects


Instructions:

Initialize a new project and install webpack
* First set up a new GitHub repository for this exercise.
* Follow the instructions from the getting started guide (https://webpack.js.org/guides/getting-started/#basic-setup) to set up the basics. Implement all the steps from Basic Setup to NPM Scripts.

Add HTML
* You already know that all the distribution files will be placed in /dist directory. You also know that you should not create files manually in the /dist folder, as there's a risk they will be overwritten. Therefore, install the HtmlWebpackPlugin to automatically create the index.html file in the /dist directory.
* Follow the instructions from the setting up HtmlWebpackPlugin guide (https://webpack.js.org/guides/output-management/#setting-up-htmlwebpackplugin). Be extra careful when updating the module.exports object in your webpack.config.js file, to not to make any nesting mistakes.
* Now delete all the files from the /dist directory and run:
npm run build
* Check your /dist folder. If it contains a new index.html file, it means you were successful.

HTML template
* If you plan to write some HTML in your project, it's easiest to do it with a template. Create a /src/index.html in which you can write your markup. Add some basic page markup, like:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wbpack Exercise</title>
</head>
<body>
    <h1>Hello webpack!</h1>
</body>
</html>
* Then modify webpack.config.js to point HtmlWebpackPlugin towards your template file:
plugins: [
  new HtmlWebpackPlugin({
-   title: 'Output Management',
+   template: './src/index.html',
  }),
],
* You could remove the title property as well (as shown above), because you have set the page title in your /src/index.html.
* Run npm run build to update the /dist/index.html.
View the /dist/index.html file in a code editor and notice how webpack inserted a <script> tag with correct path and minified the HTML for better performance.

Add CSS
The next step in building your webpack boilerplate is to add some style to it. Follow the steps in loading CSS guide (https://webpack.js.org/guides/asset-management/#loading-css).

* In your style.css file add a generic rule, like:
body {
    background-color: bisque;
}
* Next, execute npm run build and check if the HTML body style has changed.

Setup local dev server
Finally, it's time to improve your developer experience. When working on the project you will not want to run the build command from the terminal every time you make a change in the code. Therefore go ahead and install a webpack dev server, which will watch your source files, generate compiled distribution files and even refresh the browser every time you save changes in the source code.

* Follow the using webpack-dev-server guide (https://webpack.js.org/guides/development/#using-webpack-dev-server) and set it up on your local machine. Again, be cautious with updating the module.exports object in your webpack.config.js.
* Once these steps are complete, you should see your application working at: http://localhost:8080/. Every change you make in js or css files now should be reflected in a browser a few seconds later.
