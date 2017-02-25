# AngularJs Builder

Build your standard and stick to it.

This repo contains a set of simple linux command-line scripts to set up working directories 
and base files to AngularJs standards. You can customize these scripts to build your own working
directory standard, or use as is.

## How it Works

The /.build directory contains all of the default scripts to setup your working directory, and 
also generate common angularjs files on demand. 

### _setup.sh

This script uses simple bash commands to setup the working directory, generate default js files
and downloads common angularjs and bootstrap src js to the ./assets/lib/ directory.

### Libs Downloaded to ./assets/lib/

 angular.js                                     
 angular.min.js                                  
 angular-resource.js    
 angular-resource.min.js     
 angular-route.js              
 angular-route.min.js             
 angular-sanitize.js             
 angular-sanitize.min.js               

### generatejs.sh

This script will automatically generate default angular js files to a prespecified directory. 

## Standards Used

Templated classes and working directories are built using standards 
outlined in [The Angular 1 Style Guide](https://github.com/johnpapa/angular-styleguide/tree/master/a1/README.md). 

# How To

## Building Base Working Directories
 
### To build in same working directory
 
 ``` sh
 .build/_setup.sh ./
```
### To build in alternate directory

 ``` sh
 .build/_setup.sh ~/{PATH_TO_DIR}
```

## Generating Default AngularJs files

### To generate controller

 ``` sh
 .build/generatejs.sh -c ./defaultController
```

### To generate directive

 ``` sh
 .build/generatejs.sh -d ./defaultDirective
```

### To generate service

 ``` sh
 .build/generatejs.sh -s ./defaultService
```

