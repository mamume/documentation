==============
United Kingdom
==============

Configuration
=============

:ref:`Install <general/install>` the following modules to get all the features of the UK
localization:

.. list-table::
   :header-rows: 1

   * - Name
     - Technical name
     - Description
   * - :guilabel:`UK - Accounting`
     - `l10n_uk`
     - Installing this module grants you access to:
        - CT600-ready chart of accounts
        - VAT100-ready tax structure
        - InfoLogic UK counties listing
        - a few other adaptations
   * - :guilabel:`UK - Accounting Reports`
     - `l10n_uk_reports`
     - Installing this module grants you access to:
        - Accounting reports for UK
        - Allows sending the tax report via the MTD-VAT API to HMRC.

.. tip::
   Installing the module :guilabel:`UK - Accounting Reports` installs all two modules at
   once.

.. note::
   Your company should be located in the UK to be able to submit HMRC reports.

.. seealso::
   - `HM Revenue & Customs <https://www.gov.uk/government/organisations/hm-revenue-customs/>`_
   - `Overview of Making Tax Digital <https://www.gov.uk/government/publications/making-tax-digital/overview-of-making-tax-digital/>`_

Making Tax Digital (MTD)
========================

Making Tax Digital is a key part of the UK government’s plans to make it easier for individuals and
businesses to get their tax right and keep on top of their affairs. All VAT-registered businesses
are required to follow the MTD rules by keeping digital records and using software to submit their
VAT returns.

The **UK - Accounting Reports** package enables you to comply with the `HM Revenue & Customs <https://www.gov.uk/government/organisations/hm-revenue-customs/>`_
requirements regarding `Making Tax Digital <https://www.gov.uk/government/publications/making-tax-digital/overview-of-making-tax-digital/>`_ in the UK.

.. important::
   If your periodic submission is more than three months late, it is no longer possible to submit
   your report through Odoo. Odoo only retrieves open bonds from the last three months. Your
   submission has to be done manually by contacting HMRC.

Register your company to HMRC before the first submission
---------------------------------------------------------

Import your obligations HMRC, filter on the period you want to submit and send the VAT Return report
by clicking on :guilabel:`Send to HMRC`.

.. note::
   Configure your Tax Return Periodicity by going to :menuselection:`Accounting Settings -->
   Taxes section`. Click :guilabel:`Configure your tax accounts` to update your Tax groups.

Periodic submission to HMRC
---------------------------

Only one company - and one user - can connect to HMRC simultaneously. If several UK companies are on
the same database, the user that submits the HMRC report follows these instructions each time he
wants to proceed to a submission:

#. Log into the company for which the submission has to be done.
#. Go to :guilabel:`Settings app` and in the :guilabel:`Users` section click
   :guilabel:`Manage Users`. Select the user who will submit VAT.
#. Go to :guilabel:`UK HMRC Integration` tab and click :guilabel:`Reset Authentication Credentials`
   or :guilabel:`Remove Authentication Credentials` button. Then click again to create new
   credentials. It is now possible to submit the tax report for this company.
#.  Repeat the steps to proceed to the HMRC submission for another company.

.. note::
   During this process, the :guilabel:`Connect to HMRC` button no longer appears for other UK
   companies.
