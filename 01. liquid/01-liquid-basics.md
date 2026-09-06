# Shopify Liquid Basics

- Short Answer: 
Liquid is Shopify's templating language. It is used to access Shopify store data and generate dynamic HTML.

- Detailed Answer: 
Liquid runs on Shopify's server and allows a theme to work with dynamic store data such as products, collections, customers, cart information, and shop settings.

For example:
<h1>{{ product.title }}</h1>

Instead of hardcoding a product name, Liquid retrieves the actual product title from Shopify.

Example
<h1>{{ product.title }}</h1>
<p>{{ product.vendor }}</p>
<p>{{ product.price | money }}</p>

If the product is "Classic T-Shirt", Liquid generates HTML containing that product's actual information.


================================================================================================================

Q2. What are the three main parts of Liquid?

Liquid consists mainly of:

1. Objects
2. Tags
3. Filters

Objects

Objects are used to access Shopify data.

{{ product.title }}
{{ product.price }}
{{ shop.name }}

Tags

Tags control the logic or behavior of Liquid.

{% if product.available %}
  Available
{% endif %}

Common tags include:

- if
- unless
- for
- assign
- capture
- render
- case
- Filters

Filters modify the output of an object.

{{ product.title | upcase }}

Another example:

{{ product.price | money }}

==========================================================================

Q3. What is the difference between {{ }} and {% %}?

{{ }} — Output

Used when we want to display a value.

{{ product.title }}
{% %} — Logic

Used when we want to execute Liquid logic.

{% if product.available %}
  Available
{% endif %}

Easy way to remember
{{ }}  → Show something
{% %}  → Do something


=========================================================

Q4. What is a Liquid filter?

A filter modifies the value before it is displayed.

Example:

{{ product.title | upcase }}

If the title is:

Classic T-Shirt

The output becomes:

CLASSIC T-SHIRT

Multiple filters can also be chained:

{{ product.title | downcase | capitalize }}