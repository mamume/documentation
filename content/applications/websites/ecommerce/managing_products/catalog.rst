=======
Catalog
=======

The eCommerce catalog is the equivalent of your physical store shelves: it allows customers to see
what you have to offer. Clear categories, available options, sorting, and navigation threads help
you structure it efficiently.

Categorize the product catalog
==============================

In Odoo, there is a **specific category model** for your eCommerce. Using eCommerce categories for
your products allows you to add a navigation menu on your eCommerce page. Visitors can then use it
to view all products under the category they select. To do so, go to :menuselection:`Website app
--> eCommerce --> Products`, select the product you wish to modify, click on the :guilabel:`Sales`
tab. and select the :guilabel:`Categories` you want under :guilabel:`eCommerce Shop`.

.. note::
   A single product can appear under multiple eCommerce categories.

When your product's categories are configured, go to :menuselection:`Website dashboard --> Shop` and
click on :menuselection:`Edit --> Customize tab`. In the :guilabel:`Categories` option, you can
either enable a menu on the :guilabel:`Left`, on the :guilabel:`Top`, or both. If you select the
:guilabel:`Left` category, the option :guilabel:`Collapsable Category Recursive` appears and allows
to render the :guilabel:`Left` category menu collapsable.

.. image:: catalog/catalog-panel-categories.png
   :align: center
   :alt: Categories options for your eCommerce website

Browsing
--------

The eCommerce category is the first tool to organize and split your products. However, if you need
an extra level of categorization in your catalog, you can activate various **filters** such as
attributes or sort-by search.

Attributes
~~~~~~~~~~

Attributes refer to **characteristics** of a product such as **color** or **material**, whereas
variants are the different combinations of attributes. :guilabel:`Attributes and Variants` can be
found under :menuselection:`Website app --> eCommerce --> Products`, select your product, and
:guilabel:`Attributes & Variants` tab.

.. seealso::
   - :doc:`../../../sales/sales/products_prices/products/variants`

.. image:: catalog/catalog-attributes.png
   :align: center
   :alt: Attributes and variants of your product

To enable **attributess** filtering, go to :menuselection:`Website dashboard --> Shop`, click on
:menuselection:`Edit --> Customize tab` and select either :guilabel:`Left`, :guilabel:`Top`, or
both. Additionally, you can also enable :guilabel:`Price Filtering` to enable price filters.

.. note::
   :guilabel:`Price Filter` works independently from **attributes** and therefore can be enabled on
   its own if desired.

.. tip::
   You can use **attribute filters** even if you do not work with product variants. When adding
   attributes to your products, make sure only to specify *one* value per attribute. Odoo will not
   create variants if no combination is possible.

Sort-by search
~~~~~~~~~~~~~~

It is possible to allow the user to manually **sort the catalog** using the search bar. From
:menuselection:`Website dashboard --> Shop`, click on :menuselection:`Edit --> Customize tab`, you
can enable or disable the :guilabel:`Sort-By` option as well as the :guilabel:`Layout` button. You
can also select the :guilabel:`Default Sort` of the :guilabel:`Sort-By` button. The default sort
applies to *all* categories.

The **sorting** options are:

- Featured
- Newest Arrivals
- Name (A-Z)
- Price - Low to High
- Price - High to Low

In addition, you can **manually edit** the catalog's order of a products by going to
:menuselection:`Website dashboard --> Shop page --> Edit` and clicking on the product. Under the
:guilabel:`Product` section of the :guilabel:`Customize` section, you can rearrange the order by
clicking on the arrows. `<<` `>>` move the product to **extreme** right or left, and `<` `>` move
the product by **one** row to the right or left. It is also possible to change the catalog's order
of products in :menuselection:`Website app --> eCommerce --> Products` and dragging-and-dropping the
products within the list.

.. image:: catalog/catalog-reorder.png
   :align: center
   :alt: Product rearrangement in the catalog

Page design
===========

Category page
-------------

You can customize the layout of the category page using the website builder. Note that editing the
layout of the category page is global; editing one category layout will affect *all* category pages.

To do so, go on of your :menuselection:`Category page --> Edit --> Customize`. Here, you can choose
the layout, the number of columns to display the products, etc. The :guilabel:`Product Description`
button makes the product description visible from the category page, underneath the product picture.

.. image:: catalog/catalog-category-layout.png
   :align: center
   :alt: Layout options of the category pages.

.. tip::
   You can choose the size of the grid, but be aware that displaying too many products may affect
   performances and page loading speed.

Product highlight
-----------------

You can highlight products to make them more visible on the category or product page. On the page of
your choice, go to :menuselection:`Edit --> Customize` and click on the product to highlight. In the
:guilabel:`Product` section, you can choose the size of the product image by clicking on the grid,
and you can also add a **ribbon** or :guilabel:`Badge`. This displays a banner across the product's
image, such as:

- Sale;
- Sold out;
- Out of stock;
- New.

Alternatively, you can enable the :doc:`Debug mode <../../../general/developer_mode>` on the
**product's template**, and under the :guilabel:`Sales` tab, change or create the ribbon from the
:guilabel:`Ribbon` field.

.. note::
   The :doc:`Debug mode <../../../general/developer_mode>` is only intended for experienced users
   who wish to have access to advanced tools. Using the **Debug mode** is *not* recommended for
   regular users.

.. image:: catalog/catalog-product-highlight.png
   :align: center
   :alt: Ribbon highlight

Additional features
===================

You can access and enable additional feature buttons such as **add to cart**, **comparison list**,
or a **wishlist**. To do so, go to :menuselection:`Website dashboard --> Shop --> Edit -->
Customize`, and at the end of the :guilabel:`Products Page` category, click on the feature buttons
you wish to use. All three buttons appear when hoovering the mouse over a product's image.

- :guilabel:`Add to Cart`: adds a button to **add to cart** the product;
- :guilabel:`Comparison List`: adds a button to **compare** products based on their price, variant,
  etc;
- :guilabel:`Wishlist Button`: adds a button to **wishlist** the product.

.. image:: catalog/catalog-buttons.png
   :align: center
   :alt: Feature buttons for add to cart, comparison list, and wishlist

.. image:: catalog/catalog-features.png
   :align: center
   :alt: Appearance of buttons when hoovering over the mouse

Add content
===========

You can use **building blocks** to add content on the category page, with a variety of blocks
ranging from :guilabel:`Structure` to :guilabel:`Dynamic Content`. Specific areas are defined to use
blocks are defined and highlighted on the page when **dragging-and-dropping** a block.

.. image:: catalog/catalog-content.png
   :align: center
   :alt: Building blocks areas

- If you drop a building block **on top** of the product list, it will create a new category header
  specific to *that* category.
- If you drop a building **on the top** or **bottom** of the page, it will be visible on *all*
  category pages.

.. tip::
   Adding content to an eCommerce category page is beneficial in terms of **SEO** strategy. Using
   **keywords** linked to the products or the eCommerce categories improves the organic traffic.
   Additionally, each category has its own specific URL that can be pointed to and is indexed by
   search engines.
