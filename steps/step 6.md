# Step 6: Setup the Index.html file

1. Load the dependencies (polyfills)

    Add the following to the \<head\> section in index.html

    ```html
    <script src="node_modules/core-js/client/shim.min.js"></script>
    <script src="node_modules/zone.js/dist/zone.js"></script>
    <script src="node_modules/reflect-metadata/Reflect.js"></script>
    ```

2. Load our angular app with systemjs 

    Add the following to the \<head\> section in index.html

    ```html
    <script src="node_modules/systemjs/dist/system.src.js"></script>
    <script src="systemjs.config.js"></script>
    ```

    Now, load our application with systemjs:

    ```html
    <script>
        System.import('app').catch(function(err){console.error(err); });
    </script>
    ```