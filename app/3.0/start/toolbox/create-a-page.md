---
title: Step 2. Create a new page
subtitle: "Build an app with App Toolbox"
---

<!-- toc -->

The `starter-kit` includes placeholder pages you can use to start building out
the views of your application. But at some point, you'll probably want to add more.

This step takes you through the process of adding a new page or top-level view to your application.

## Create an element for the new page

First, create a new custom element that encapsulates the contents of
your new view.

1.  Create a new file called `src/my-new-view.js` and open it in an editor.

2.  Add some scaffolding for a new custom element definition using Polymer:

    ```js
    
    ```

For now your element is very basic, and just has a `<h1>` that says "New view",
but we can return to it and make it more interesting later.

## Add the element to your app

Your element is defined, but your app isn't actually using it yet. To use it,
you need to add it to your app's HTML.

1.  Open `src/my-app.js` in a text editor.

1.  Find the set of existing pages inside the `<iron-pages>`:

    ```
    <iron-pages
        selected="[[page]]"
        attr-for-selected="name"
        fallback-selection="view404"
        role="main">
      <my-view1 name="view1"></my-view1>
      <my-view2 name="view2"></my-view2>
      <my-view3 name="view3"></my-view3>
      <my-view404 name="view404"></my-view404>
    </iron-pages>
    ```

    The `<iron-pages>` is bound to the `page` variable that changes with the
    route, and selects the active page while hiding the others.

1.  Add your new page inside the iron-pages:

    ```
    <my-new-view name="new-view"></my-new-view>
    ```

    Your `<iron-pages>` should now look like this:

    ```
    <iron-pages
        selected="[[page]]"
        attr-for-selected="name"
        fallback-selection="view404"
        role="main">
      <my-view1 name="view1"></my-view1>
      <my-view2 name="view2"></my-view2>
      <my-view3 name="view3"></my-view3>
      <my-new-view name="new-view"></my-new-view>
      <my-view404 name="view404"></my-view404>
    </iron-pages>
    ```

    `%TODO: Find out how lazy loading will be done in p3 version of this template`

    Note: Normally when adding a new custom element for the first time, you'd
    want to import the module to ensure the component definition has been
    loaded. However, this app template is already set up to lazy-load top
    level views on-demand based on the route, so in this case you don't need
    to add an import for your new `<my-new-view>` element.
        
    The following code that came with the app template will ensure the
    definition for each page has been loaded when the route changes.  As
    you can see, the app follows a simple convention (`'my-' + page + '.js'`)
    when importing the definition for each route. You can adapt this code as you
    like to handle more complex routing and lazy loading.

    Existing template code—you do not need to add this { .caption }

    ```
    ... 
    ```

## Create a navigation menu item

You've defined your new element and declared it in your app. Now you
just need to add a menu item in the left-hand drawer so that users can navigate to the new page.

1.  Keep `src/my-app.js` open in your editor.

1.  Find the navigation menu inside the `<app-drawer>` element.

    ```
      <!-- Drawer content -->
      <app-drawer id="drawer" slot="drawer">
        <app-toolbar>Menu</app-toolbar>
        <iron-selector selected="[[page]]" attr-for-selected="name" class="drawer-list" role="navigation">
          <a name="view1" href="/view1">View One</a>
          <a name="view2" href="/view2">View Two</a>
          <a name="view3" href="/view3">View Three</a>
        </iron-selector>
      </app-drawer>
    ```

    Each navigation menu item consists of an anchor element (`<a>`) styled with CSS.

1.  Add the following new navigation item to the bottom of the menu.

    ```
    <a name="new-view" href="/new-view">New View</a>
    ```

    Your menu should now look like the following:

    ```
    ...
      <!-- Drawer content -->
      <app-drawer id="drawer" slot="drawer">
        <app-toolbar>Menu</app-toolbar>
        <iron-selector selected="[[page]]" attr-for-selected="name" class="drawer-list" role="navigation">
          <a name="view1" href="/view1">View One</a>
          <a name="view2" href="/view2">View Two</a>
          <a name="view3" href="/view3">View Three</a>
          <a name="new-view" href="/new-view">New View</a>
        </iron-selector>
      </app-drawer>
    ...
    ```

Your new page is now ready! Serve your app with `polymer serve --open --npm`.

![Example new page](/images/3.0/toolbox/new-view.png)

## Register the page for the build

When you deploy your application to the web, you'll use the Polymer CLI
to prepare your files for deployment.  Polymer CLI will need to know about any
demand-loaded fragments like the lazy-loaded view you just added.

1.  Open `polymer.json` in a text editor.

1.  Add `src/my-new-view.js` to the list of `fragments`.

    The new list should look like this:

    ```
    "fragments": [
      "src/my-view1.js",
      "src/my-view2.js",
      "src/my-view3.js",
      "src/my-new-view.js",
      "src/my-view404.js"
    ]
    ```

`TODO: next para is probably all wrong`

Note: You only need to add files you will lazy load or import using the `async`
attribute to the `fragments` list.  Any files that are imported using synchronous
`<link rel="import">` tags should *not* be added to `fragments`.

## Next steps

You've added a new page to your application. Next, learn how to install and add an off-the-shelf custom element to your app.

<a class="blue-button"
    href="add-elements">Next step: Add an element</a>
