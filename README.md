# AngularJs Builder

A simple linux command-line script to set up working directories and base files to 
AngularJs standards.

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

