# Step 2: TypeScript Setup

1. Install TypeScript

        npm install --save-dev typescript typings

1. Create the configuration files needed

        touch tsconfig.json typings.json

1. Modify the tsconfig.json file:

    ```javascript
    {
        "compilerOptions" : {
            "target" : "es5",
            "module" : "commonjs",
            "moduleResolution" : "node",
            "sourceMap" : true,
            "emitDecoratorMetadata" : true,
            "experimentalDecorators" : true,        
            "removeComments" : false,
            "noImplicitAny" : false
        }
    }
    ```

1. Install typings:

        npm install -g typings

        typings install dt~core-js dt~jasmine dt~node --save --global

    * Observe that the typings.json file now contains entries for the installed typings.
    * Observe that there is now a new folder, typings, that has been added to the project folder

1. Modify the package.json file with typescript scripts:

    * Add the typescript compiler script:

            "tsc" : "tsc",
    * Add the typescript watch script:

            "tsc:w" : "tsc -w" 

    * Add the typings script:

            "typings" : "typings"

    * Add the postinstall script. This script will recreate and repopulate the typings folder if it doesn't exist:

            "postinstall" : "typings install" 

    * The *scripts* section of the package.json file should look like this:

        ```javascript
        "scripts": {
            "lite": "lite-server",
            "tsc" : "tsc",
            "tsc:w" : "tsc -w",
            "typings" : "typings",
            "postinstall" : "typings install"
        }
        ```
1. As we want to run both lite-server and typescript watch at the same time, we need 
package that allows us to do that.

    * Install concurrently 

        npm install concurrently --save-dev

    * Modify the package.json file so that *npm start* will start the lite-server and typescript watch.
    To do that add a *start* script as follows:

            "start" : "tsc && concurrently \"npm run tsc:w\" \"npm run lite\"
    
    * So now, the scripts section of the packages.json should look like this:

        ```javascript
            "scripts": {
            "start" : "tsc && concurrently \"npm run tsc:w\" \"npm run lite\"",
            "lite": "lite-server",
            "tsc": "tsc",
            "tsc:w": "tsc -w",
            "typings": "typings",
            "postinstall": "typings install"
        }
        ```






