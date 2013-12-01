
### Arguable is a simple argument parser for [Haxe](http://haxe.org/)
---

I got tired of repeatedly parsing arguments, so here is a simple argument parsing library for Haxe.

Arguable parsers arguments in the form of :   

`--argument value`   
`--argument`   

If arguments are passed incorrectly, for example `--argument value value` the results will include the valid and invalid results for simpler parsing.

---

### Example usage

    var results = ArgParser.parse( Sys.args() );

    	// Handle any invalid arguments
    if(results.invalid.length > 0) {

    	trace("\tUnknown option/s " + results.invalid );
    	trace("\tValid option/s " + results.valid );

    } else {

    		// Handle valid arguments, 
    		// each one is a name and value property.
    	trace("Args : ");
		for(arg in results.valid) {
            trace( '\t> ' + arg.name + ' : ' + arg.value );
		}

    }

### How to run the test file
	
- Have haxe installed (obviously)
- run `haxe build.hxml`
- run `neko argparser.n`

### That's it

- Uses `Stack` from [structural](http://github.com/underscorediscovery/structural)
- Suggestions, issues, bugs welcome.

