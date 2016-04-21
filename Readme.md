# Aurelia-view-pipeline

This repository is a feature plugin for loading any Markdown into custom element on Aurelia.

Now we want to create custom component from HTML and turn into any Markdown file into custom element.
Let’s start by adding a this feature into main.js:

``` javascript
export function configure(aurelia) {
    aurelia.use
        .standardConfiguration()
        .developmentLogging()
        .feature('view-pipeline/resources');

    aurelia.start().then(a => a.setRoot('view-pipeline/app'));
}
```

Now you can use it into View
``` html
<template>
    <require from="./hello.md"></require>

    <input type="text" value.bind="firstName" />
    <input type="text" value.bind="lastName" />
    
    <hello>${firstName} ${lastName}</hello>
</template>
```

For .md file we can have a file like this:
``` markdown
# Hello !!!

My name is **<content></content>**

```



