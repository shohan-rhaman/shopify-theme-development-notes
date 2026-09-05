# Shopify Liquid Basics

- Short Answer
Liquid is Shopify's templating language. It is used to access Shopify store data and generate dynamic HTML.

- Detailed Answer
Liquid runs on Shopify's server and allows a theme to work with dynamic store data such as products, collections, customers, cart information, and shop settings.

For example:
<h1>{{ product.title }}</h1>

Instead of hardcoding a product name, Liquid retrieves the actual product title from Shopify.

Example
<h1>{{ product.title }}</h1>
<p>{{ product.vendor }}</p>
<p>{{ product.price | money }}</p>

If the product is "Classic T-Shirt", Liquid generates HTML containing that product's actual information.