
##Welcome to Project Norman


Project Norman is a free, open-sourced, cloud-based and social platform that enables even non-technical users to easily create useful enterprise-ready applications and deliver them to end-users without writing a line of code.
It contains the following projects:
+ [Log-on] (https://github.wdf.sap.corp/Norman/Logon) 
+ [Data Composer] (https://github.wdf.sap.corp/Norman/DataComposer)
+ [Data Model Editor] (https://github.wdf.sap.corp/Norman/DataModelEditor)
+ [Flow Composer] (https://github.wdf.sap.corp/Norman/FlowComposer)
+ [Sample Data Server] (https://github.wdf.sap.corp/Norman/SampleDataServer)
+ [UX Rule Engine] (https://github.wdf.sap.corp/Norman/UXRuleEngine )
+ [UI Canvas] (https://github.wdf.sap.corp/Norman/UICanvas )
+ [UI Composer] (https://github.wdf.sap.corp/Norman/UIComposer)
+ [Shared Workspace] (https://github.wdf.sap.corp/Norman/SharedWorkspace)
+ [UI Catalog Manager] (https://github.wdf.sap.corp/Norman/UICatalogManager)
+ [Previewer] (https://github.wdf.sap.corp/Norman/Previewer)
+ [User Research] (https://github.wdf.sap.corp/Norman/UserResearch)
+ [Collaboration] (https://github.wdf.sap.corp/Norman/Collaboration)
+ [Shell] (https://github.wdf.sap.corp/Norman/Shell)
+ [Analytics] (https://github.wdf.sap.corp/Norman/Analytics)
+ [Common] (https://github.wdf.sap.corp/Norman/Common)
+ [Projects - aka Project Management] (https://github.wdf.sap.corp/Norman/Projects)


norman-norman
===============
This is a bare-bones norman application. Use this to build norman modules on top of that.


# Prerequisites
- Configure [Sap NPM registry](https://jam4.sapjam.com/wiki/show/kvLVqwLEg5DQorc6zsGIUh) - for installing norman modules with `npm`


# Installation

1. Clone [Norman/Norman](https://github.wdf.sap.corp/Norman/Norman) repo
    ```sh
    git clone git@github.wdf.sap.corp:Norman/Norman.git
    ```

2. Install required node modules (dependencies):
    ```sh
    npm install
    ```

3. Build and run:
    ```sh
    grunt dev       // just build in development mode
    grunt serve     // build dev + start express server + watch js & less for changes
    grunt dist      // build for production
    ```

## Adding Modules

#### To include a Norman module to the client side e.g. the Shell module:

1. `npm install norman-shell-client` 

2. Inside `client/require.js` file add:
    ```sh
    require('norman-shell-client');
    ```

3. Build and Run


#### To include another Norman module on the Server e.g. the Login module:

1. `npm install norman-auth-server` 

2. Inside the `server/require.js` file add:
    ```sh
    require('norman-auth-server')(app);
    ```

3. Build and Run


## Developing modules locally

1. Assuming you have your module in a separate folder

2. Using terminal/console, navigate to the `client` or `server` folder

3. create a link to the module
    ```sh
    npm link
    ```

4. Using terminal/console, navigate to the root of the `norman-norman` project and run:
    ```sh
    npm link module-name	
    ```

5. Inside the `server/require.js` (or `server/require.js`) file add:
    ```sh
    require('norman-login-server');
    ```

6. Build and Run

**<u>NOTE</u>**  When making changes to the module under development it may be necessary to run the `npm link` command again.
