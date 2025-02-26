# arrive.js
[![CDNJS version](https://img.shields.io/cdnjs/v/arrive.svg)](https://cdnjs.com/libraries/arrive)

arrive.js provides events to watch for DOM elements creation and removal. It makes use of [Mutation Observers](https://developer.mozilla.org/en/docs/Web/API/MutationObserver) internally.

Download [arrive.min.js](https://raw.githubusercontent.com/uzairfarooq/arrive/master/minified/arrive.min.js) (latest)

or use [Bower](http://bower.io/) to install:

```bash
# install arrive.js and add it to bower.json dependencies
$ bower install arrive --save
```

##### Node.js / NPM
Node.js users can install using npm:

```bash
$ npm install arrive --save
```

## Usage
**The library does not depend on jQuery, you can replace jQuery elements in the examples below with pure javascript elements and it would work fine.**
### Watch for elements creation
In pure javascript you can call the function on `document`, `window`, any `HTMLElement` or `NodeList`, like this:
```javascript
// watch for element creation in the whole HTML document
document.arrive(".test-elem", function() {
    // 'this' refers to the newly created element
});

// this will attach arrive event to all elements in the NodeList
document.getElementsByClassName(".container-1").arrive(".test-elem", function() {
    // 'this' refers to the newly created element
});
```

#### Options
As of v2.0 `arrive` event accepts an optional `options` object as 2nd argument. Options object consists of following:
```javascript
var options = {
    fireOnAttributesModification: boolean, // Defaults to false. Setting it to true would make arrive event fire on existing elements which start to satisfy selector after some modification in DOM attributes (an arrive event won't fire twice for a single element even if the option is true). If false, it'd only fire for newly created elements.
    existing: boolean                      // Defaults to false. Setting it to true would ensure that the registered callback is fired for the elements that already exist in the DOM and match the selector.
};
```


## Browser Support
arrive.js is built over [Mutation Observers](https://developer.mozilla.org/en/docs/Web/API/MutationObserver) which is introduced in DOM4. It's supported in latest versions of all popular browsers.

| Browser           | Supported Versions
| ------------------|:-----------------:|
| Google Chrome     | 27.0+             |
| Firefox           | 14.0+             |
| Safari            | 6.1+              |
| Internet Explorer | 11.0+             |
| Opera             | 14.0+             |

## Contributing
#### Report a bug / Request a feature
If you want to report a bug or request a feature, use the [Issues](https://github.com/uzairfarooq/arrive/issues) section. Before creating a new issue, search the existing ones to make sure that you're not creating a duplicate. When reporting a bug, be sure to include OS/browser version and steps/code to reproduce the bug, a [JSFiddle](http://jsfiddle.net/) would be great.

#### Development
If you want to contribute to arrive, here is the workflow you should use:

1. Fork the repository.
2. Clone the forked repository locally.
3. From the `dev` branch, create and checkout a new feature branch to work upon. (If you want to work on some minor bug fix, you can skip this step and continue to work in `dev` branch)
4. Make your changes in that branch (the actual source file is `/src/arrive.js`).
5. If sensible, add some jasmine tests in `/tests/spec/arriveSpec.js` file.
6. Make sure there are no regressions by executing the unit tests by opening the file `/tests/SpecRunner.html` in a browser. There is a button 'Run tests without jQuery' at the top left of th page, click that button to make sure that the tests passes without jQuery. Run the test cases in all major browsers.
7. Push the changes to your github repository.
8. Submit a pull request from your repo back to the original repository.
9. Once it is accepted, remember to pull those changes back into your develop branch!

#### Some features/bugs you can send pull requests for
- [#70](https://github.com/uzairfarooq/arrive/issues/70): Add Typescript types to the project
- [#69](https://github.com/uzairfarooq/arrive/issues/69): Option to watch for text change
- [#64](https://github.com/uzairfarooq/arrive/issues/64): Function firing twice in Firefox 56 on 2.4.1 (regression from bug 54)
- [#60](https://github.com/uzairfarooq/arrive/issues/60): Issue when expose arrive API to window

**Keywords**

javascript, js, jquery, node.js, watch, listen, creation, dynamically, removal, new, elements, DOM, dynamic, detect, insertions, event, bind, live, livequery
