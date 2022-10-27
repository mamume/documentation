
.. _contributing/scss:

===============
SCSS Guidelines
===============



Syntax and Formatting
=====================

.. tabs::

    .. code-tab:: html SCSS

        .o_foo, .o_foo_bar,
        .o_baz {
            height: $o-statusbar-height;

            .o_qux {
                height: $o-statusbar-height * 0.5;
            }
        }

        .o_corge {
            background: $o-list-footer-bg-color;
        }

    .. code-tab:: css CSS

        .o_foo, .o_foo_bar, .o_baz, .o_qux {
            height: 32px;
        }

        .o_foo .o_quux, .o_foo_bar .o_quux, .o_baz .o_quux {
            height: 16px;
        }

        .o_corge {
            background: #EAEAEA;
        }

- four (4) space indents, no tabs;
- 80 characters wide columns;
- related selectors on the **same** line; unrelated selectors on new lines;
- empty space between the last selector and the opening brace (`{`).
- the closing brace (`}`) on its own new line.
- one line for each declaration;
- meaningful use of whitespace.


.. _scss/properties_order:

Properties order
================

Order properties from the "outside", starting from `position` and ending with decorative rules (font,  filters...).

:ref:`Scoped SCSS variables <scss/scoped-scss-var>` and `CSS variables <css_variables>`_ must be placed at the very top, followed by an empty line separating them from other declarations.


.. code-block::

    .o_myComponent {
        $-inner-gap: $border-width + $legend-margin-bottom;

        --myComponent-margin: 1rem;
        --myComponent-size: 3rem;

        @include o-position-absolute(1rem);
        display: block;
        margin: var(--myComponent-margin);
        width: calc(var(--myComponent-size) + #{$-inner-gap});
        border: 0;
        padding: 1rem;
        background: blue;
        font-size: 1rem;
        filter: blur(2px);
    }

Naming Conventions
==================

Naming conventions in CSS are hugely useful in making your code more strict, transparent and informative.


Use the "Grandchild" approach
-----------------------------
Avoid creating hyper-specific classes and variables names. When naming nested elements, opt for the "Grandchild" approach.

Besides being more compact, this approach improves maintenance 'cause avoids the need to rename classes and variables in case of DOM changes.

Don't:

.. code-block:: html

    <div class=“o_MyBox_wrapper”>
        <div class=“o_MyBox_wrapper_entries”>
            <span class=“o_MyBox_wrapper_entries_entry”>
                <a class=“o_MyBox_wrapper_entries_entry_link”>Entry</a>
            </span>
        </div>
    </div>

Do:

.. code-block:: html

    <div class=“o_MyBox_wrapper”>
        <div class=“o_MyBox_entries”>
            <span class=“o_MyBox_entry”>
                <a class=“o_MyBox_link”>Entry</a>
            </span>
        </div>
    </div>


.. ####### NOT COMMON CONSENSUS YET #######
.. Classes
.. -------

.. Our standard convention for classes naming is `o_[root]_[element]_[modifier]`:

.. * `[root]` - either the component **or** the module name (components take priority);
.. * `[element]` - the univocal element targeted by the rules;
.. * `[modifier]` - optional modifier;

.. .. code-block:: scss
..     :caption: :file:`mail/static/src/scss/composer.scss`

..     .o_mail_emoji {
..     }

.. .. code-block:: scss
..     :caption: :file:`mail/static/src/components/chat_window/chat_window.scss`

..     .o_ChatWindow {

..         .o_ChatWindow_newMessageFormInput {
..         }

..         .o_ChatWindow_newMessageFormInput_active {
..         }
..     }


.. Exceptions to these rules are `Bootstrap default classes <https://getbootstrap.com/docs/5.1/getting-started/introduction/>`_ and odoo utility-classes generated using `Bootstrap's API <https://getbootstrap.com/docs/5.1/utilities/api/>`_.


Variables
---------

Global SCSS Variables
~~~~~~~~~~~~~~~~~~~~~~~

Our standard convention is `$o-[root]-[element]-[property]-[modifier]`:

* `[root]` - either the component **or** the module name (components take priority);
* `[element]` - optional identifier for inner elements;
* `[property]` - the property/behavior defined by the variable;
* `[modifier]` - optional modifier;

.. code-block:: scss

    $o-block-color: value;
    $o-block-title-color: value;
    $o-block-title-color-hover: value;

.. note::
   With Odoo, "Global" SCSS variables are actually accessible within the current bundle only.

.. _scss/scoped-scss-var:

Scoped SCSS Variables
~~~~~~~~~~~~~~~~~~~~~

These variables are declared within blocks and are not accessible from the outside.
Our standard convention is `$-[variable name]`.

.. code-block::

    .o_myComponent {
        $-inner-gap: compute-something;

        margin-right: $-inner-gap;

        .o_myComponent_child {
            margin-right: $-inner-gap * 0.5;
        }
    }

.. seealso::
   Variables scope on `SASS Documentation website <https://sass-lang.com/documentation/variables#scope>`_

.. _scss/css-var:

CSS Variables (aka "Custom properties")
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

In Odoo the use of CSS variables is strictly DOM-related. Use them for **contextually** adapt design and layout.

Our standard convention is BEM, so `--[root]__[element]-[property]--[modifier]`.

* `[root]` - either the component **or** the module name (components take priority);
* `[element]` - optional identifier for inner elements;
* `[property]` - the property/behavior defined by the variable;
* `[modifier]` - optional modifier;


.. code-block:: scss

    .o_kanban_record {
        --KanbanRecord-width: value;
        --KanbanRecord__picture-border: value;
        --KanbanRecord__picture-border--active: value;
    }

    // Adapt the component when rendered in another context.
    .o_form_view {
        --KanbanRecord-width: another-value;
        --KanbanRecord__picture-border: another-value;
        --KanbanRecord__picture-border--active: another-value;
    }


.. seealso::
   Read more on :doc:`CSS variables <css_variables>` in Odoo.


SCSS Mixins and Functions
-------------------------

Our standard convention is `$o-[name]`.
Name optional argument as :ref:`scoped variables <scss/scoped-scss-var>`.

.. code-block::

    @mixin o-avatar($-size: 1.5em, $-radius: 100%) {
        width: $-size;
        height: $-size;
        border-radius: $-radius;
    }

    @function o-invert-color($-color, $-amount: 100%) {
        $-inverse: change-color($-color, $-hue: hue($-color) + 180);

        @return mix($-inverse, $-color, $-amount);
    }

.. seealso::
   - Mixins on `SASS Documentation website <https://sass-lang.com/documentation/variables#scope>`_
   - Functions on `SASS Documentation website <https://sass-lang.com/documentation/variables#scope>`_



