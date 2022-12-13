=====
Kenya
=====

.. _localization/kenya/configuration:

Configuration
=============

:ref:`Install <general/install>` the following modules to get all the features of the Kenyan
localization:

.. list-table::
   :header-rows: 1

   * - Name
     - Technical name
     - Description
   * - :guilabel:`Kenyan - Accounting`
     - `l10n_ke`
     - Installing this module grants you access to the list of accounts used in the local GAAP and
       the list of common taxes (VAT, etc.).
   * - :guilabel:`Kenyan - Accounting Reports`
     - `l10n_ke_reports`
     - Installing this module grants you access to improved accounting reports for Kenya, such as
       Profit and Loss and Balance Sheets.

You also have to install the **Kenya Tremol Device EDI Integration** package to be able to report
your taxes to the **Kenya Revenue Authority (KRA)** using the Tremol G03 Control Unit:

.. list-table::
   :header-rows: 1

   * - Name
     - Technical name
     - Description
   * - :guilabel:`Kenya Tremol Device EDI Integration`
     - `l10n_ke_edi_tremol`
     - This module integrates with the Kenyan G03 Tremol control unit device to report taxes to KRA
       through TIMS.


.. image:: kenya/modules.png
   :align: center
   :alt: The three modules for the Kenya Fiscal Localization Package on Odoo

Kenyan TIMS integration
=======================

The Kenya Revenue Authority (KRA) has decided to go digital for tax collection through the **Tax
Invoice Management System (TIMS)**. As of December 1st, 2022, all VAT-registered persons should
comply with TIMS. The goal is to reduce VAT fraud, increase tax revenue, and increase VAT compliance
through standardization, validation, and transmission of invoices to KRA on a real-time or near
real-time basis.

All VAT-registered taxpayers should use a **compliant tax register**. Odoo decided to develop the
integration of the **Tremol G03 Control Unit (type C)**, which can be run locally through USB. This
device validates invoices to ensure financial documents meet the new regulations and send the
validated tax invoices directly to KRA.

Installing the Proxy Server on a Windows device
-----------------------------------------------

Go to odoo.com/download, fill out the required information and click :guilabel:`Download`.

.. image:: kenya/download.png
   :align: center
   :alt: Install the Proxy Server on a Windows device

Once it is loaded on your computer, a wizard opens. You have to read and agree with the terms of the
agreement. On the next page, select the **type of install: Odoo IoT**. And then click
:guilabel:`Next` and :guilabel:`Install`. Once completed, click :guilabel:`Next`. An **access token
number** for the Odoo IoT appears. Copy it for later and click :guilabel:`Next`. Check the
:guilabel:`Start Odoo` box to be redirected to Odoo automatically, and then click
:guilabel:`Finish`.

A new page opens, confirming your IoT Box is up and running. Connect your physical device **Tremol
G03 Control Unit (type C)** to your laptop via USB. In the :guilabel:`IoT Device` section, check
that your Tremol G03 Control Unit (type C) appears.

.. image:: kenya/iot-box.png
   :align: center
   :alt: Your IoT box is up and running

.. note::
   If the device is not detected, try to plug it in again or click on the :guilabel:`Restart` button
   in the top right corner.

.. seealso::
   Video flow of installing the Tremol G03 Control Unit on Windows device

Sending the data to KRA using the Tremol G03 Control Unit
---------------------------------------------------------

As a pre-requisite, check out that the :ref:`Kenyan Accounting modules <localization/kenya/configuration>`
are installed on your database. Then, go to the :menuselection:`General Settings --> Kenya TIMS
Integration section` and check that the :guilabel:`control Unit Proxy Address` has been
automatically filled out, confirming the connection is established between the device and your
computer.

Upon confirmation of a new invoice, the :guilabel:`Send Invoice to Device` button appears. Clicking
on it sends the invoice details to the government. Once this is done, the :guilabel:`CU Invoice
Number` field is automatically completed in your invoice, confirming the information has been sent.

.. note::
   On the `Kenya Revenue Authority website <https://itax.kra.go.ke/KRA-Portal>`_, go through the
   :guilabel:`Invoice Number Checker` section to verify the invoice information that has been sent
   to KRA.

The :guilabel:`Tremol G03 Control Unit` tab contains the following fields that are automatically
completed once the invoice data have been sent and that appear on the invoice when you click on
:guilabel:`Send & Print`:

- :guilabel:`CU QR Code`: Url from the KRA portal which reflects a QR code.
- :guilabel:`CU Serial Number`: reflects the serial number of the device.
- :guilabel:`CU Signing Date and Time`: The date and time when the invoice has been sent to KRA.
