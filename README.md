# Unit Testing Node Restful API with Mocha

## What is Unit Testing
The core idea with unit testing is to test a function’s behavior when giving it a certain set of inputs. You call a function with certain parameters, and check you got the correct result.

## What is Mocha?
Mocha is a simple, extensible and fast testing library for Node.js

### Steps

```
npm install mocha --save
npm install chai --save
```
We are using the --save option to automatically save these dependencies in our ```package.json``` file.


Mocha gives us the ability to describe the features that we are implementing by giving us a ```describe``` function that expresses our expectations. 

The first argument is a simple string that describes the feature, which is *Color Code Converter*

```javascript
describe("Color Code Converter", function() {

});
```
If you want to give it a bit more detail, you can also write like this :

```javascript
describe("Color Code Converter", function() {
  describe("RGB to Hex conversion", function() {
  });

  describe("Hex to RGB conversion", function() {
  });
});
```

Now the ```it``` function is very similar to the describe function, except that we can only put expectations in the body of the ```it``` function

```javascript
describe("Color Code Converter", function() {
    describe("RGB to Hex conversion", function() {
        it("converts the basic colors from rgb to hex", function() {

        });
    });

    describe("Hex to RGB conversion", function() {
        it("converts the basic colors from hex to rgb", function() {

        });
    });
});
```

*Note that our implementation code doesn't exist at this point, but this need not bother us, and we can write our tests as if the implementation already exists.*

For every ```it``` that needs to wait for a response value, we will inject a done callback function and call it only when our expectations were executed. This way, Mocha will know it needs to wait for some of the expectations.
