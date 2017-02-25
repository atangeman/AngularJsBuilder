# AngularJs Builder

Build your standard and stick to it!

This repo contains a set of simple linux command-line scripts to set up working directories 
and base files to AngularJs standards. You can customize these scripts to build your own working
directory standard, or use as is.

## Standards Used

Templated classes and working directories are built using standards 
outlined in [The Angular 1 Style Guide](https://github.com/johnpapa/angular-styleguide/tree/master/a1/README.md). 

## How it Works

The /.build directory contains all of the default scripts to setup your working directory, and 
also generate common angularjs files on demand. 

### _setup.sh

This script uses simple bash commands to setup the working directory, generate default js files
and downloads common angularjs and bootstrap src js to the ./assets/lib/ directory.

#### Libs Downloaded to ./assets/lib/:

* angular.js                                     
* angular.min.js                                  
* angular-resource.js    
* angular-resource.min.js     
* angular-route.js              
* angular-route.min.js             
* angular-sanitize.js             
* angular-sanitize.min.js               

### generatejs.sh

This script will automatically generate the following default angular js files to a prespecified 
directory:

* Controllers (-c)
* Directives (-d)
* Services (-s)


## Building Base Working Directories

Generating base working directories is performed using the _setup.sh script.
 
### Build in same working directory
 
 ``` sh
 .build/_setup.sh ./
```
### Build in alternate directory

 ``` sh
 .build/_setup.sh ~/{PATH_TO_DIR}
```

## Generating Default AngularJs files

Generating default angularJs files can be performed using the generatejs.sh script

### Generating defaultController.js File

 ``` sh
 .build/generatejs.sh -c ./defaultController
```

##### Sample Output

``` js
/**
 * @file
 */
(function () {

    "use strict";

    angular
        .module('app')
        .controller('DefaultCtrl', DefaultCtrl);

    DefaultCtrl.$inject = ['defaultService', 'logger'];

    function DefaultCtrl(defaultService, logger) {
        var vm = this;
        vm.load = load;
        vm.data = [];
        vm.title = 'Default';

        activate();

        function activate() {
            return getData().then(function() {
                logger.info('Activated Default View');
            });
        }

        function getData() {
            return defaultService.getData().then(function(data) {
                vm.data = data;
                return vm.data;
            });
        }
    }
})();
```

### Generating defaultService.js File

 ``` sh
 .build/generatejs.sh -s ./defaultService
```

##### Sample Output

``` js
/**
 * @file
 */
(function () {

    "use strict";

    function defaultService($http, logger) {
        var service = {
            getData: getData
        };

        return service;

        /////////////

        function getData() {
            // implementation details go here
        }
    }
})();
```

### Generating defaultDirective.js File

 ``` sh
 .build/generatejs.sh -d ./defaultDirective
```

##### Sample Output

``` js
/**
 * @file
* @example <div default-function></div>
 */
(function () {

    "use strict";

    angular
        .module('app')
        .directive('defaultFunction', defaultFunction);

    function defaultFunction() {
        /* implementation details */
    }

})();
```


