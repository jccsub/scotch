# Step 8: Create the App Module

## About App modules

From documentation:

>Angular Modules help organize an application into cohesive blocks of functionality.
>
>An Angular Module is a class adorned with the @NgModule decorator function. @NgModule takes a metadata object that tells Angular how to compile and run module code. It identifies the module's own components, directives and pipes, making some of them public so external components can use them


## The AppModule

Every angular application has at least one angular module, the root module.
It is the module in which you bootstrap to launch the application.

The convential name of the root module is AppModule.

## Creating the AppModule

1. Create the app.module.ts in the app folder

1. Import NgModule:

    ```javascript
    import {NgModule} from '@angular/core';
    ```
1. Import the BrowserModule - The BrowserModule contains lots of services and directives needed
in the angular app like ngIf:

    ```javascript
    import {BrowserModule} from '@angular/platform-browser';
    ```
1. Import the AppComponent that was craeted earlier (Since we had exported it fromthe 
app.component.ts file, we can import it here)

    ```javascript
    import {AppComponent} from './app.component';
    ```
1. Create the NgModule
    
    The @NgModule decorator defines the metadata for the module.

    * Here we will import a single helper module, BrowserModule.
    
        * the BrowserModule is the module that every browser app must import.
        * the BrowserModule registers critical application service providers. 
        * the BrowserModule includes common directives like NgIf and NgFor which become immediately visible and usable in any of this modules component templates.
        ```javascript
        @NgModule({
            imports: [BrowserModule]
        })
        ```
    * Next, we will identify the application's components using the declarations
    list

        ```javascript
        @NgModule({
            imports: [BrowserModule],
            declarations: [AppComponent]
        })
        ```

    * Finally, we will use the @NgModule.bootstrap property to identify the 
    AppComponent as the bootstrap component. 
    
        That means that when Angular launches 
    the app, it places the HTML rendering of AppComponent in the DOM, inside the <my-app> element tags of the index.html
        ```javascript
        @NgModule({
            imports: [BrowserModule],
            declarations: [AppComponent],
            bootstrap: [AppComponent]

        })
        ```
1. Export the class, AppModule

    ```javascript
    @NgModule({
        imports: [BrowserModule],
        declarations: [AppComponent],
        bootstrap: [AppComponent]
    })
    export class AppModule {}
    ```


The app.module.ts file should now look like this:

```javascript
import {NgModule} from '@angular/core';
import {BrowserModule} from '@angular/platform-browser';
import {AppComponent} from './app.component';


@NgModule({
    imports: [BrowserModule],
    declarations: [AppComponent],
    bootstrap: [AppComponent]
})
export class AppModule {}
```