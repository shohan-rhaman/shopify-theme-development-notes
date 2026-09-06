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


==================================================================

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


===========================================================================

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


=====================================================================

Q5. What is a Liquid variable?

A variable stores a value that can be reused.

{% assign product_title = product.title %}

Now we can use:

{{ product_title }}

Another example:

{% assign featured_collection = collections['featured'] %}


======================================================================

Q6. What is an if statement in Liquid?

It allows us to execute code based on a condition.

{% if product.available %}
  <button>Add to Cart</button>
{% else %}
  <button disabled>Sold Out</button>
{% endif %}

This is commonly used in Shopify themes for:

Product availability
Sale badges
Conditional sections
Customer-specific content
Variant states


===================================================================

Q7. What is a Liquid loop?

A loop allows us to repeat code for multiple items.

Example:

{% for product in collection.products %}
  <h2>{{ product.title }}</h2>
{% endfor %}

If a collection contains 10 products, the loop generates the product markup 10 times.

====================================================================

Q8. What is the difference between Liquid and JavaScript?
Liquid

Liquid runs on Shopify's server and is mainly used to retrieve Shopify data and generate HTML.

JavaScript

JavaScript runs in the customer's browser and is used for interactive behavior.

For example:

Liquid:

{{ product.title }}

Gets the product title.

JavaScript:

button.addEventListener("click", function() {
  // interaction
});

Handles browser interaction.

Simple rule
- Liquid      → Shopify data + server-side rendering
- JavaScript  → Browser interaction + dynamic behavior


==========================================================================

Interview Answer

If an interviewer asks:

"What is Liquid?"

A strong answer is:

Liquid is Shopify's server-side templating language. I use it to access Shopify objects such as products, collections, cart and shop data, and generate dynamic HTML. Liquid also provides tags for logic and filters for transforming output.

Practice

Before moving to the next topic, you should be able to:

- Explain Liquid
- Explain Objects
- Explain Tags
- Explain Filters
- Explain {{ }}
- Explain {% %}
- Create variables with assign
- Create if/else conditions
- Create for loops
- Explain Liquid vs JavaScript