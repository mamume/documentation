=====
Italy
=====

Configuration
=============
The first configuration to book accounting transactions on an Italian localization is the
:guilabel:`Italy - Accounting` module. It allows to:

- Generate electronic invoices in **FatturaPA's** format.
- Send and receive electronic invoicing through SDIcoop.

.. warning::
   Once this module is installed, it's no longer possible to send invoices via :ref:`PEC mails
   <italy/pec>`.

Once this module is installed, there are a few more necessary configurations. For all B2B
transactions, Italy requires electronic invoicing with the use of specific formats and the
transmission of invoices on **SDI** platform.

Company information
-------------------

The company information is the also an important configuration to ensure the proper set up of your
Accounting database. To add the information, go to :menuselection:`Configuration --> Settings -->
General Settings --> Update info`. In this menu, make sure to have at least the following:

- the company address
- :guilabel:`GSTIN` code
- :guilabel:`Codice Fiscale`
- :guilabel:`Tax System`
- :guilabel:`PEC address email`

PEC
---
The PEC email is a specific type of certified email providing a legal equivalent to the traditional
registered mail. The PEC email of the main company must be the same as the one registered by the
Agenzia delle Entrate authorities.

E-Invoicing
-----------

**SDI** is the public technical system that allows sending and receiving invoices. It enables the
transmission and receipt of electronic billing in XML as well as validating and sending it from
businesses to third parties.
To receive invoices and notifications from third parties, you need to inform the FatturaPA service
that Odoo is the allowed party to process files for you. To do so, you must set up Odoo's **Codice
Destinatario** on the FatturaPA portal.

#. Go to https://ivaservizi.agenziaentrate.gov.it/portale/ and authenticate.
#. Go to section :menuselection:`Fatture e Corrispettivi`.
#. Set the user as Legal Party for the VAT number you wish to configure the electronic address.
#. In :menuselection:`Servizi Disponibili --> Fatturazione Elettronica --> Registrazione
   dell’indirizzo telematico dove ricevere tutte le fatture elettroniche`, insert Odoo's Codice
   Destinatario (`K95IV18`), then confirm.

Give Odoo permission to process files
-------------------------------------

Since the files are transmitted through Odoo's server before being sent to SDICoop or received by
your database, you need to authorize Odoo to process your files from your database.

To do so, go to :menuselection:`Accounting --> Configuration --> Settings --> Electronic
Document Invoicing`. In the :guilabel:`Electronic Document Invoicing`, you can see three different
modes:
- Demo
- Test (experimental)
- Official (production)

Choosing the right mode
-----------------------

- :guilabel:`Demo` mode in Odoo is a simulation environment where all invoices created are **not**
  automatically sent to the government. In such mode, the invoices need to be manually downloaded
  as xml files and you then have to upload them on the Agenzia dell'Entrate website.
- :guilabel:`Test` mode sends invoices to a non-production service. THerefore a communication is
  established between Odoo and the test server of the Public Administration and only send invoices
  to a selected few `fake` destinations.
- :guilabel:`Official` is a production mode that sends your invoices directly to the Agenzia
  dell'Entrate.

.. warning::
   The choice of the mode is **not reversible**. Once in :guilabel:`Official` mode it is not
   possible to get back to the :guilabel:`Test` and :guilabel:`Demo`. Equally is not possible to go
   from :guilabel:`Test` to :guilabel:`Official`.

After having selected the right mode, you need to accept the terms and conditions right below the
mode selection. Once you have :guilabel:`Saved` the mode you want, you can start recording your
Accounting transactions in Odoo.

Issue invoices
==============

The **FatturaPA** feature is automatically actived, you can check it in
:menuselection:`Configuration --> Journals --> Customer Invoices -->  Advanced Settings`
You can create a new invoice by going to :menuselection:`Accounting dashboard --> New invoice`, once
confirmed the e-invoice will be generated and sent.

.. warning::
   The e-invoice is only sent to the government if you are in :guilabel:`Official` mode.

You can check the current status of your customer invoice under the :guilabel:`Electronic invoicing`
field. The xml file is accessible in the chatter of the invoice.

.. image:: italy/processing.png
   :align: center
   :alt: Electronic invoicing status (waiting for confirmation)

Vendor bills
============

As for invoices, when creating a vendor bill, the :guilabel:`Fattura PA` option is automatically
activated in the Vendor bill Journals' advanced settings.
When inserting taxes in a vendor bill, you have the possibility to choose **reverse charge** taxes,
these are automatically activated in the Italian fiscal position. By going to
:menuselection:`Configuration --> Taxes`, you will see that the 10% & 22% services and goods taxes
are activated and have the correct tax grids; these are set up automatically to ensure the correct
booking of accounting entries and display of the tax report.
Once the bill is confirmed, a banner appears, and the bill can be sent to the EDI service.

Integration documents
=====================

If one of the two parties of the reverse charge is not Italian, it is required to send additional
integration documents to the SDI. Depending on the case, these documents, **Dati Documento** can be
type TD 16, TD 17, TD 18 and others.




