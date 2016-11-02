# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    Within the Ember Application Router, our routes are mapped and paths are specified.      
    In a client-only app, an Ember Route stores our model and its data.  It also delivers params whenever the model is called.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember generate route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to "campus.boston"}}
        Boston Campus
    {{/link-to}}
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
The first definition creates a nested route 'product' under the route 'products,' and you can only access the 'product' route by going down the 'products' route/path.
The second definition creates a route 'product' at the same level (depth?) as the 'products' route, but it directly sets the path to be nested under the products path.
In our backless client, the second option would force us to duplicate our model data about individual products from the products model.  
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    movie_id or params.movie_id.
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    model.attributeOfModel
    ```
