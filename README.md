#oui <a target="_blank" href="https://npmjs.org/package/oui"><img src="https://badge.fury.io/js/oui.svg" alt="NPM version" height="18"></a> <a target="_blank" href="https://david-dm.org/silverwind/oui"><img src="https://david-dm.org/silverwind/oui.svg" alt="Dependency Status" height="18"></a>
Lookup MAC adresses or their prefixes in the IEEE database. The input string can be pretty much any format as long as 6 charactes containing hexadecimal are provided. If you require stricter input parsing, there's the `strict` option.

##Installation
````bash
npm install oui
````
##Usage
````js
oui(oui, [options], callback);
````
To update the local database from the official IEEE source:
````js
oui.update(callback);
````

##Example
````js
var oui = require("oui");
oui("20-37-06", function(err, result) {
    if (err) {
        console.log(err);
    } else {
        console.log(result);
    }
});
````
will print:
````
CISCO SYSTEMS, INC.
170 W. TASMAN DRIVE
M/S SJA-2
SAN JOSE CA 95134-1706
UNITED STATES
````

##Options
`options` is an object containing below (optional) options:

###strict
````js
oui(oui, {strict: true}, callback);
````
In strict mode, only these formats of MACs are accepted:
 - 00:00:00
 - 00-00-00
 - 00:00:00:00:00:00
 - 00-00-00-00-00-00
 - 0000.0000.0000

##CLI
When installed through `npm install -g oui`, this is available:

````bash
$ oui 20-37-06
````
