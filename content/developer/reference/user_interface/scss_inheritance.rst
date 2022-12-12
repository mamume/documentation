
.. _contributing/scss_inheritance:

================
SCSS Inheritance
================



Overview
========

Managing SCSS assets in Odoo is not as straightforward as it is in some other environment, but it's highly efficient.

Modularity is key, the inheritance scheme described further allows Odoo to:

- customise Bootstrap CSS framework;
- handle two different webclient designs (Community and Enterprise);
- handle backend and frontend bundles separately (including the user's website design);
- contextually load necessary assets only;
- handle multiple color-schemes (eg. dark-mode);

SCSS `!default` directive
=========================

"Direct variables’ overrides" are technically possible in SCSS but may lead to inconsistent results in complex environments like Odoo.

.. code-block:: scss
   :caption: :file:`library.scss`

   $foo: red;

.. code-block:: scss
   :caption: :file:`customization_layer.scss`

   $foo: blue; // -> Don't!

Indeed, since the compilation process proceed across different interdependent bundles, re-assign a variable in the "wrong spot" may lead to unexpected cascade results.

SCSS provide several techniques to overcome these issues (eg. `shadowing <https://sass-lang.com/documentation/variables#shadowing>`_ ), but the most critical procedure in Odoo is the use of the `!default` flag.

When using  the `!default` flag, the compiler assigns a value **only** if that variable isn’t defined yet.

As a result of this technique, the priority of how variables are assigned matches the assets loading order.

.. code-block:: scss
   :caption: :file:`customization_layer.scss`

   $foo: red !default;

.. code-block:: scss
   :caption: :file:`library.scss`

   $foo: blue !default; // -> Already defined, line ignored.
   $bar: black !default; // -> Not defined yet, value assigned.

.. code-block::
   :caption: :file:`component.scss`

   .component {
      color: $foo; // -> 'color: red;'
      background: $bar; // -> 'background: black;'
   }

.. seealso::
   - `!default` flag on `SASS Documentation website <https://sass-lang.com/documentation/variables#default-values>`_

Odoo SCSS inheritance scheme
============================

The following scheme conceptually illustrates CSS and SCSS variables definition in relation to the compilation order.

.. code-block:: text

    ↓ [Compilation starts]
    ⏐
    ↓ web.dark_mode_variables
    ⏐   ├─ Primary variables
    ⏐   └─ Components Variables
    ⏐
    ↓ web._assets_primary_variables
    ⏐   ├─ Primary Variables (enterprise)
    ⏐   ├─ Components Variables (enterprise)
    ⏐   ├─ Primary Variables (community)
    ⏐   └─ Components Variables (community)
    ⏐
    ↓ web._assets_bootstrap
    ⏐
    ↓ web.assets_backend
    ⏐   ├─ ...
    ⏐   ├─ CSS variables definition
    ⏐   └─ CSS variables contextual adaptations
    ⏐
    ● [Visual result on screen]

.. important::
   | This scheme is incomplete and doesn't match the actual bundles organization.
   | Read more on :ref:`asset bundles<reference/assets_bundle>`.



