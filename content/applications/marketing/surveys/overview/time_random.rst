==============================
Timed and randomized questions
==============================

When creating a survey in Odoo, the user has the options to set a time limit on the survey and
randomize the questions.

Time limit
==========

During a timed survey, participants must finish the survey within a certain period of time. Placing
a time limit on the survey ensures that every participant gets the same amount of time to fill in
answers. It also greatly reduces the chance of participants looking up responses via external
resources (Google, etc.).

The :guilabel:` Survey Time Limit` setting is found in the :guilabel:`Options` tab of the survey
form under the :guilabel:`Questions` section.

.. image:: time_random/time-limit.png
   :align: center
   :alt: Time limit field in the options tab of a survey template form.

When a time limit is configured, a timer is displayed on every page of the survey, letting
participants keep track of the time remaining. Participants that do not submit their survey by the
preconfigured time limit will *not* have their answers saved.

Randomized selection
====================

When a survey is randomized, Odoo shuffles the questions and reveals them in a random order every
time a participant begins the questionnaire.

Randomizing surveys is an effective way to discourage participants from looking at each other's
responses.

To randomize a survey, click the :guilabel:`Options` tab on the survey form. In the
:guilabel:`Questions` section, select :guilabel:`Randomized per section` for the
:guilabel:`Selection` field.

After enabling this feature, navigate to the :guilabel:`Questions` tab. In the :guilabel:`Random
questions count` column, determine how many questions (per section) Odoo should select and display
during the shuffling of questions.

.. image:: time_random/random-questions.png
   :align: center
   :alt: Randomized question count in the questions tab of a survey.

.. seealso::
    - :doc:`scoring`
