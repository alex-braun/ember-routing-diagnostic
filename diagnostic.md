# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    The router's job is to map the URLs to the correct route.  The Ember routes are used to load a template and a model for each URL.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember generate route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{link-to 'campus.boston'}}Boston{{/link-to}}
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    The first function has the products route go straight to a single product URL to be open from the main products URL.  This means that it will not be possible to view the index of all products.

    The second function will have a selectable path for individual products
    from the main products page.  This path will cause the single product URL to
    appear when it is selected from the main products URL.  The main URL will then
    disappear until a user selects a back button.

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    model (params) {
    return this.get('store').findRecord('movie', '123');
    },

    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    {{model.movie movie=movie}}
    ```
