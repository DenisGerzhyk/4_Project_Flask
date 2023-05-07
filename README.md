# 4_Project_Flask

This is a Python code for a Flask web application that includes a database and several routes to handle HTTP requests.

The first line imports the Api and Checkout classes from the cloudipsp module, which is used to create an online payment system.

The Flask class is initialized and assigned to the app variable. The next two lines set the configuration options for the application's SQLite database using the SQLAlchemy package.

The Item class is a model that represents a table in the database with four columns: id, title, price, and isActive. It also has a text column that is not used in this code. The __repr__ method is defined to return the title of the item.

The first route (@app.route('/')) returns the index.html template and retrieves all items from the database and orders them by price.

The second route (@app.route('/about')) returns the about.html template.

The third route (@app.route('/buy/<int:id>')) takes an id parameter and retrieves the corresponding item from the database. It then creates a new instance of the Api class with the merchant ID and secret key, and creates a new instance of the Checkout class with the api parameter. The data dictionary is created with the currency and amount keys, and the amount value is calculated by multiplying the item's price by 100 and converting it to a string. Finally, the url variable is set to the checkout URL returned by the checkout.url() method, and the user is redirected to the checkout URL.

The fourth route (@app.route('/create', methods=['POST', 'GET'])) handles both GET and POST requests. If a POST request is received, the form data is used to create a new Item object and add it to the database. If the operation is successful, the user is redirected to the index page. If an error occurs, an error message is returned. If a GET request is received, the create.html template is returned.

The final block of code starts the application if the file is executed directly, with the debug option enabled.
