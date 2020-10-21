# JavaScript Best Practices
First of all, Node and JavaScript are often confused among each other (and JavaScript is to java, as  *as* manslaughter is to laughter.)


- JavaScript is a language
- Node is a runtime environment
# Coding style

Refer to google’s JavaScript style guide (https://google.github.io/styleguide/javascriptguide.xml).  **Idiomatic.js** complements and further details some of the concepts provided by Google (https://github.com/rwaldron/idiomatic.js)

# Linting

Always use a linting tool before submitting a Pull/Merge request (and do fix the issues that it reports)  one of the most popular linting tools is https://jshint.com/ and several IDE’s provide a jsHint based offline tool. 

Another linting tool is ESLint (https://eslint.org/) which can be automated to check and fix code according to a given set of rules, including those from google. this can be configured to be used as a part of a deployment process or commit hook.

# The often overlooked JS language features that you should definitely we aware of and make use when needed


- OOP (https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects)
- Anonymous functions/closures (https://riptutorial.com/javascript/example/726/anonymous-function, https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
- Functions are first class objects (https://medium.com/@kvsn_1/functions-are-first-class-objects-in-javascript-b8c2c2cc2994)
- Loose typing (http://blog.jeremymartin.name/2008/03/understanding-loose-typing-in.html)
- Scoping and Hoisting (http://blog.jeremymartin.name/2008/03/understanding-loose-typing-in.html)
- Function binding (https://www.smashingmagazine.com/2014/01/understanding-javascript-function-prototype-bind/)
- Strict mode (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)
    - should be required on all JS code written by the org
- Immediately-invokable function expressions “IIFE” (http://benalman.com/news/2010/11/immediately-invoked-function-expression/)
    - for coding patterns like Revealing Module Pattern
# Design/Coding Patterns

Hopefully you are already familiar with “design patterns”, if you are not, please take a look at the following resources:


- https://www.dofactory.com/javascript/design-patterns
- https://addyosmani.com/resources/essentialjsdesignpatterns/book/

From above, there are 3 that are considered “coding patterns” and you should be aware of, specially when creating modules:


- Constructor pattern (https://addyosmani.com/resources/essentialjsdesignpatterns/book/#constructorpatternjavascript)
- Module pattern (https://addyosmani.com/resources/essentialjsdesignpatterns/book/#modulepatternjavascript)
- Revealing module pattern (https://addyosmani.com/resources/essentialjsdesignpatterns/book/#revealingmodulepatternjavascript)
# Unit Testing
- Mocha - Test framework
    - https://mochajs.org/
- Chai - Assertion library
    - https://www.chaijs.com/
- Sinon - Test spies, stubs, and mocks
    - https://sinonjs.org/
## Test anatomy (AAA)
1. Arrange - create stubs, spies, fixtures…
2. Act - execute the method to be tested
3. Assert - output, spies, etc…


## Best practices
- Descriptive testing using product language
    1. What is tested
    2. under what circumstances
    3. expected result


    describe('Products Service', function() {
      describe('Add new product', function() {
        //2. scenario and 3. expectation
        it('When no price is specified, then the product status is pending approval', ()=> {
          const newProduct = new ProductService().add(...);
          expect(newProduct.status).to.equal('pendingApproval');
        });
      });
    });


- Black box testing, test only public methods
- Avoid mocks in favor of stubs and spies (https://martinfowler.com/articles/mocksArentStubs.html)
- Stay within the test, minimize external helpers and abstractions as much as possible
- Avoid global fixtures, add data per test
# General software development principles that are encouraged to apply
## SOLID principles
- Single responsibility
    - A class should only have one job
- Open-closed
    - open for extension, closed for modification
- Liskov substitution
    - every subclass or derived class should be substitutable for their base/parent class without breaking the application
- Interface Segregation
    - A class should never be forced to implement an interface it does not use, or depend on methods they do not use
- Dependency Inversion
    - Entities must depend on abstractions and not on concretions.  High level modules must not depend on low level modules.


https://scotch.io/bar-talk/s-o-l-i-d-the-first-five-principles-of-object-oriented-design


The above will achieve Low coupling, High cohesion, which makes any code base to be easy to maintain (https://medium.com/clarityhub/low-coupling-high-cohesion-3610e35ac4a6).

