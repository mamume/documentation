=========================
Manage a financial budget
=========================

Managing budgets is an essential part of running a business. Budgets help people become more
intentional with how money is spent and direct people to organize and prioritize their work to meet
financial goals. They allow the planning of a desired financial outcome and then measure the actual
performance against the plan. Odoo manages budgets using both **general** and **analytic accounts**.

Configuration
=============

Go to :menuselection:`Accounting --> Configuration --> Settings --> Analytics` and enable
:guilabel:`Budget Management`.

Budgetary positions
-------------------

Budgetary positions are lists of accounts for which you want to keep budgets (typically expense or
income accounts).

To define budgetary positions, go to :menuselection:`Accounting --> Configuration --> Management:
Budgetary Positions` and :guilabel:`Create`. Add a :guilabel:`Name` to your budgetary position.
Each budgetary position can have any number of accounts from the chart of accounts, though it must
have at least one.

Use case
========

Let’s illustrate this with an example: we just started a project with *Smith & Co*, and we would
like to budget the income and expenses of that project.

We plan on having a revenue of 1000, and we don’t want to spend more than 700.

First, we need to define what accounts relate to our project’s expenses. Go to
:menuselection:`Accounting --> Configuration --> Budgetary positions`, :guilabel:`Create` a
position, and add the accounts wherein we will book our expenses.

.. image::  budget/smith-and-co-expenses.png
   :align: center
   :alt: display the Smith and Co expenses

Let's repeat the steps to create a budgetary position that reflects the revenue.

.. image::  budget/smith-and-co-revenue.png
   :align: center
   :alt: display the Smith and Co revenue

Analytical accounts
-------------------

Odoo needs to know which costs or expenses are relevant to a specified budget because the above
general accounts may be used for different projects.

Go to :menuselection:`Accounting --> Configuration --> Analytic Accounts` and :guilabel:`Create` a
new **Analytic Account** called Smith & Co. You have to refer to this analytic account when creating
a customer invoice and/or vendor bill.

Each budgetary position can have any number of accounts from the general ledger (the main chart of
accounts) assigned to it, though it must have at least one.

Define the budget
-----------------

Let’s set our targets. We specified that we expect to gain 1000 with this project, and we would like
not to spend more than 700. Go to :menuselection:`Accounting --> Accounting --> Budgets` and
:guilabel:`Create` a new budget.

First, fill in your :guilabel:`Budget Name`. Then, select the :guilabel:`Period` wherein the budget
is applicable. Next, add the :guilabel:`Budgetary Position` you want to track, define the related
:guilabel:`Analytic Account`, and add the :guilabel:`Planned Amount`.

.. image:: budget/define-the-budget.png
   :align: center
   :alt: budget lines display

.. Note::
   When recording a planned amount related to expenses, the amount must be negative.

Check your budget
-----------------

Go to :menuselection:`Accounting --> Accounting --> Budgets` and find the Smith & Co Project to see
ow it evolves.

.. note::
   - The :guilabel:`Theoretical Amount` represents the amount of money you theoretically could have
     spent or should have received based on the date. For example, if your budget is 1200 for 12
     months (January to December), and today is 31 of January, the theoretical amount will be 100,
     since this is the actual amount that could have been made.
   - The :guilabel:`Practical Amount` evolves when a new journal entry related to an accounts from
     your budgetary position and your analytic account.
