# Step 9: Creating the main.ts

 1. Create the main.ts file in the app folder

 1. Import platformBrowserDynamic

    ```javascript
    import {platformBrowserDynamic} from '@angular/platform-browser-dynamic';
    ```
  1. Import our AppModule

        ```javascript
        import {platformBrowserDynamic} from '@angular/platform-browser-dynamic';
        import {AppModule} from './app.module';

        ```

1. Finally bootstrap our application:

    ```javascript

    platformBrowserDynamic().bootstrapModule(AppModule);

    ```

The **main.ts** file should look like this:

```javascript
import {platformBrowserDynamic} from '@angular/platform-browser-dynamic';
import {AppModule} from './app.module';

platformBrowserDynamic().bootstrapModule(AppModule);
```
