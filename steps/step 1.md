# Step 1 : Initial Setup


1. Initialize the packages.json file using all defaults:

			npm init --yes
1. Select a Bootstrap theme by going to https://www.bootstrapcdn.com/bootswatch/ and copy the link to your favorite theme. Here we are using Flatly.
1. Create the index file with the following content:

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>My Angular 2 App</title>
        <!-- css -->
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootswatch/3.3.7/flatly/bootstrap.min.css">
        <style>body {padding: 50px 0; }</style>
        </head>
        <body  class="container">
            I am the app!
        </body>
    </html>	
    ```
1. Setup lite-server
	* Install

			npm install lite-server --save-dev 
    
    * Configure NPM to run lite-server. Your packages.json should look like this now:

        ```javascript
        {
            "name": "scotch",
            "version": "1.0.0",
            "description": "",
            "main": "index.js",
            "scripts": {
                "lite" : "lite-server"
            },
            "keywords": [],
            "author": "",
            "license": "ISC",
            "devDependencies": {
                "lite-server": "^2.2.2"
            }
        }
        ```
1. Do a test run:
    * Execute:

            npm run lite

    * Browse to http://localhost:3000


