# Step 7: Create the App Component

1. Create a new file app.component.ts in the app folder

1. Do an ES6 import to 'Component'

    ```javascript
    import {Component} from 'angular/core';
    ```

1. Create the new AppComponent class with the Component decorator:

    ```javascript
    
    @Component ({

    })
    export class AppComponent { }
    ```
1. Add the selector to the Component decorator:

    ```javascript
    @Component ({
        selector : 'my-app'
    })
    export class AppComponent { }
    ```

1. Create the inline template using the ES6 back-tick (`) character for multi-line
strings

    ```javascript
    @Component ({
        selector : 'my-app',
        template : `
            <div class="jumbotron">
                <h1>Welcome to our App!</h1>
            </div>`
    })
    export class AppComponent { }    
    ```

    **Note: the rule of thumb is that if the template is more than 3 lines, then
    use the templateUrl instead**

1. Add an inline styles if desired

    ```javascript
    @Component ({
        selector : 'my-app',
        template : `
            <div class="jumbotron">
                <h1>Welcome to our App!</h1>
            </div>`,
        styles : [`
            .jumbotron {box-shadow: 0 2px 0 rgba (0,0,0,0.2); }
          `]
    })
    export class AppComponent { }    
    ```
