---
layout: post
title: Angular 2 Components
description: "How to build components in Angular 2"
date: 2016-02-29 19:00:00
modified: 2016-02-29
tags:
    Angular2
    Typescript
categories: [Web Development]
---

[Angular Docs](http://angular.io) is a great resource to reference when building an app with the framework.  With Angular 2, it is built upon Typescript, which may be
new to some people.  Typescript is a superset of Javascript, which introduces classes to the mix.  Furthermore, Angular 2 also uses AtScript, which extendes the Typescript
language.  AtScript uses the notation '@', which is clearly the idea behind the name.  Let's look at how Angular 2 components utilize this.

## The Structure of A Component

<pre><code>
import { Component } from 'angular2/angular2';

@Component({
    selector: 'my-app',
    template: '<div>Hello World</div>'
})

class MyClass {
    //Code Goes Here    
}
</code></pre>

### Import the Component

There are 3 basic parts to the component.  First is the import statement, which pulls the 'Component' from the Angular2 directory 'angular2/angular2' into the app file
you are working on.  Just as your index.html page needs to know where to find your stylesheet or script, this is an AtScript call to the file you need.

### @Component

The above code is where the information about the Component are built.  `selector: 'my-app'` is saying, "I would like my Component to be referenced in the HTML as `<my-app></my-app>`.
You can name this whatever you please, but it is always good practice to use a descriptive name to be able to tell it apart.

`template: '<div>Hello World</div>'` is defining what you would like to appear when you reference `<my-app></my-app>` on the page.  Other selectors can be referenced in the template,
but that can be covered at a later time.  For now, lets stick with the basics.  If you feel the template should live outside of the scripting portion, you can also use 
`templateUrl: 'path/file.html'` to reference an external template.

You may also see the template broken away from the `@Component` and placed in a `@View` instead.

### Class

In the last portion is the class, and it is where the magic happens.  This is where you will store variables and functions to use in your Component, utilizing Typescript syntax.

### That's It?

No, not quite.  Save this file in your site's directory as a Typescript file.  Most examples I have seen will place them into a new folder, like `app/myfile.ts`.  Now, we have to
bootstrap the Component so the page will load it.  You can either put this in the file you just created, but I prefer to separate it into a `boot.ts` file in the same directory.
Again, you will need to import your app if you put it in a separate file, along with bootstrap as well. For the example above, we would make our boot file like so:

<pre><code>
import {bootstrap} from 'angular2/platform/browser';
import {MyClass}   from './myfile';
bootstrap(MyClass);
</code></pre>

### One Last Thing

<pre><code>
      System.config({
        transpiler: 'typescript',
        typescriptOptions: { emitDecoratorMetadata: true },
        packages: {'app': {defaultExtension: 'ts'}}
      });
      System.import('app/myfile')
            .then(null, console.error.bind(console));
</code></pre>

The SystemJS will need configured in your `index.html` file, so that it points to your app file you just created.  Notice the import statement toward the bottom, it is pointing to `app/myfile.ts'
The Typescript will compile down to Javascript (using a compiler, its not automatic) and ...

**Now you can enjoy your freshly created app** 