What are the different types of dependencies in Node.js ?
Read
Discuss
Courses
NPM (Node Package Manager) is a package manager for the Node JavaScript platform. It consists of an npm registry that enables Open-Source developers to publish and share their code. You might need to install a few packages to streamline your project. Packages contain code written by other developers. Our root project has a package.json file that keeps track of all the packages we’ve installed. This file contains information about the project and defines the attributes that npm uses for installing dependencies, running scripts, and identifying the entry point for the package.

The different types of dependencies are:  
Production Dependencies
Development Dependencies
Peer Dependencies
Optional Dependencies
Bundled Dependencies
Create Package json file: Run the following command from the root directory of the project to create the package.json file.

npm init 
Note: Npm init prompts you for information about your project such as package name, version, test command, git repository, keywords, author and license.


Creating a package.json file 

Adding Package: Following is the syntax to install the package:

npm install <package_name>
Example: Run the following command to install express package:

npm install express

Installing Express (Express is a node.js framework)

Output: After installing the package, our package.json file will look like this.


package.json file 

Besides the details you entered about the project, you’ll notice the dependencies section. Dependencies are libraries on which the project relies to function effectively. 

1. PRODUCTION DEPENDENCIES: 

Production dependencies are fundamental dependencies that are required to complete the project. Package.json specifies these dependencies under the key “dependencies”. These are the packages used in the project code. If a package doesn’t already exist in the node_modules directory, then it is automatically added. These are the libraries you need when you run your code. For example, To run a react project, you need react-dom. In our production dependencies, you will find the express package we just installed. 

2. DEVELOPMENT DEPENDENCIES: 

As a developer, you may want to install dependencies to build and test your website. The packages required by a developer during development are called devDependencies. Dependencies that you might need at some point in the development process, but not during execution. They are not included in the production version and will not be downloaded to end user’s browser caches. For example, Nodemon, lodash, Babel etc.

Note: Nodemon helps developers create node.js applications by automatically restarting the node application when a file change is detected in the directory.

Adding dev dependency: By using the following command, let’s add nodemon as a dev dependency:

Syntax: npm install <package_name> --save-dev
Example: npm install nodemon --save-dev

Installing Nodemon 

Output: Let’s look at our package.json file. The package.json file now includes the nodemon package under dev dependencies.


package.json file after installing nodemon 

As you install a package, npm will automatically install the package’s dependencies and dev dependencies. In addition to these dependencies, we also have peer dependencies.

3. PEER DEPENDENCIES:

The only time you would encounter peer dependencies is if you were publishing your own package ie, when you develop a code that will be used by other programs. Libraries use peerDependencies to tell developers which other libraries with the exact version they will need to install in their own websites to use your library. Therefore, peer dependencies also express compatibility. The peerDependencies ensure that the code is compatible with the version of the package installed. peerDependencies are not automatically installed. You need to manually modify your package.json file in order to add a Peer Dependency.

For packages like react, this will ensure that there is a single copy of react-dom which is also used by the person installing the package. Even though the package relies on React, it has no direct dependency. Things such as React and React-dom are required, but not installed.

4. OPTIONAL DEPENDENCIES:

As the name implies, optional dependencies are those that won’t cause a failure during the installation of the dependencies for an application or project because npm will ignore them if they fail. Regardless of whether these dependencies are present or not, the application will still run just fine. Adding a dependency as optional can speed up the installation process for Node projects. However, not all dependencies can really be optional.  

Adding dependency as optional: We can use the following command to make a dependency optional:

npm i package_name --save-optional
Example: For instance, we will install the chalk package as an optional dependency. Using the chalk library, we can easily enforce colors and styles on our terminal output.

npm i chalk --save-optional 

Installing chalk 

You will find your package under the “optionalDependencies” key in package.json.


Chalk package under optionalDependencies 

5. BUNDLED DEPENDENCIES:

When publishing the package, these dependencies are bundled with it. NPM packages are preserved locally or can be downloaded from a single file. For example, express, request packages can be bundled. 

BundledDependencies are listed as an array, without versions. Bundled Dependencies have the same functionality as normal dependencies. When normal dependencies are insufficient, bundled dependencies can be useful. They are rarely used. 

