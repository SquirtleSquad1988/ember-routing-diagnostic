# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    In the Ember Application Router we define all of our routes for our templates.
    This makes sure that when a user goes to a particular URL the correct template
    is loaded onto the page. Actions performed inside the Ember Route include
    the definition of actions that we want to perform within our templates.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    this.route('campus', function() {
      this.route('boston');
    });
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to 'campus.boston'}}Link Here{{/link-to}}
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
    The top route has a nested route containing a dynamic route while the bottom
    route has no nested route but also defines a dynamic route. On the top route
    it defines a products route along with a nexted route that allows for dynamic
    routes so the user can go to both /products and product/:product_id while
    the bottom URL if a user goes to /product it redirects them to /products/:product_id
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    movies.movie_id
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    {{movies.movie_id}}
    ```
