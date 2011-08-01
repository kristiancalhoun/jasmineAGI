<a name="README">[Jasmine](http://pivotal.github.com/jasmine/)</a>
=======
**A JavaScript Testing Framework**

Jasmine is a Behavior Driven Development testing framework for JavaScript. It does not rely on browsers, DOM, or any JavaScript framework. Thus it's suited for websites, [Node.js](http://nodejs.org) projects, or anywhere that JavaScript can run.

Documentation & guides live here: [http://pivotal.github.com/jasmine/](http://pivotal.github.com/jasmine/)

## What's New In This Fork?

* Individual specs or suites can be marked as the only test(s) to run by calling <code>odescribe()</code> or <code>oit()</code> instead of <code>describe()</code> or <code>it()</code>.  
* If there are multiple oits, then they will each run and all other non-oit specs will be skipped. 
* When using odescribe, all specs within that suite will be tested, including those in any nested suites. However, if there is an oit
within an odescribe, then the oit gets priority and no other specs within the suite will run (except for other oits).
*Moreover, if the oit is nested in another suite within the odescribe, then that oit is the only spec that will run within that inner suite. The rest of the specs outside of that suite, but still within the scope of
the original odescribe, also run. 

	// Example 1. Only the second test will run.
	
	describe("Jasmine", function() {
		
		it("makes testing JavaScript awesome!", function() {
			
			expect(yourCode).toBeLotsBetter();
		
		});
		
		oit("now has added oit functionality!", function() {
			
			expect(yourCode).toBeEvenBetter();
		
		});
	});	
		

	// Example 2. Only the first suite will run.
	
	odescribe("Suite 1", function() {
		
		it("test 1", function() {
			
			expect(thisWillRun).toBeTruthy();
		
		});
		
		it("test 2", function() {
			
			expect(thisWillRun).toBeTruthy();
		
		});
	
	});
	
	describe("Suite 2", function() {
		
		it("test 3", function() {
			
			expect(thisWillRun).toBeFalsey();
		
		});
	
	});


## Support

* Search past discussions: [http://groups.google.com/group/jasmine-js](http://groups.google.com/group/jasmine-js)
* Send an email to the list: [jasmine-js@googlegroups.com](jasmine-js@googlegroups.com)
* Check the current build status: [ci.pivotallabs.com](http://ci.pivotallabs.com)
* View the project backlog at Pivotal Tracker: [http://www.pivotaltracker.com/projects/10606](http://www.pivotaltracker.com/projects/10606)
* Follow us on Twitter: [@JasmineBDD](http://twitter.com/JasmineBDD)


## Maintainers

* [Davis W. Frank](mailto:dwfrank@pivotallabs.com), Pivotal Labs
* [Rajan Agaskar](mailto:rajan@pivotallabs.com), Pivotal Labs
* [Christian Williams](mailto:antixian666@gmail.com), Square

Copyright (c) 2008-2011 Pivotal Labs. This software is licensed under the MIT License.
