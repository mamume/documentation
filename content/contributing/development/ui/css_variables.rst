=============
CSS Variables
=============

In Odoo the use of CSS variables is strictly DOM-related, meaning that are used for **contextually** adapt design and layout rather than to manage the global design-system.


Typical Use
===========

The typical use of CSS variables in Odoo is the definition of components' properties that may adapt in specific context or when some circumstances occur.


We define these properties into the component's main block, providing fallback used as defaults.


.. code-block:: scss
   :caption: :file:`my_component.scss`

   .o_MyComponent {
      color: var(--MyComponent-color, #313131);
   }

.. code-block:: scss
   :caption: :file:`my_dashboard.scss`

   .o_MyDashboard {
      // Adapt the component in this context only
      --MyComponent-color: #017e84;
   }

.. seealso::
   - Odoo `CSS Variables guidelines <scss.html#css-variables-aka-custom-properties>`_.
   - CSS variables on `MDN web docs <https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties>`_


CSS and SCSS Variables
======================

Despite being apparently similar, `CSS` and `SCSS` variables behave very differently.
The main difference is that, while `SCSS` variables are **imperative** and compiled away, `CSS` variables are **declarative** and included in the final output.

.. seealso::
   - CSS/SCSS variables difference on `SASS Documentation website <https://sass-lang.com/documentation/variables#:~:text=CSS%20variables%20are%20included%20in,use%20will%20stay%20the%20same>`_


In Odoo we take the best of both worlds, using `SCSS` variables to define the design-system while opting for `CSS` ones when it comes to contextual adaptations.

The implementation of the previous example should be improved by adding SCSS variables in order to gain control at the top-level and ensure consistency with other components.

.. code-block:: scss
   :caption: :file:`primary_variables.scss`

   $o-main-code-color: value;
   $o-brand-primary: value;
   // [...]


.. code-block:: scss
   :caption: :file:`my_component.variables.scss`

   $o_MyComponent_color: $o-main-code-color;
   // [...]

.. code-block:: scss
   :caption: :file:`my_dashboard.variables.scss`

   $o_MyDashboard_card_color: $o-brand-primary;
   // [...]

.. code-block:: text
   :caption: :file:`my_component.scss`

   .o_MyComponent {
      color: var(--MyComponent-color, #{$o_MyComponent_color});
   }

.. code-block:: text
   :caption: :file:`my_dashboard.scss`

   .o_MyDashboard {
      --MyComponent-color: #{$o_MyDashboard_card_color};
   }


The `:root` pseudo-class
========================

Define CSS variables on the `:root` pseudo-class is a technique we normally **don't use** in Odoo's UI.
The practice is commonly used to access and modify CSS variables globally, operations that we perform using SCSS instead.

Exceptions to this rule should be fairly apparent, such as templates shared across frontend and backend that require a certain level of contextual awareness in order to be rendered properly.

