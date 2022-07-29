===============
Scoring surveys
===============

To measure a survey participant's performance, knowledge, or overall satisfaction, ascribe points
to survey answers. At the end of the survey, these points are summed up, resulting in the
participant's final score.

To add points to questions, open the :guilabel:`Surveys` application and open the desired survey
form. Then, click on the :guilabel:`Options` tab. Under the :guilabel;`Scoring` section, choose
between :guilabel:`Scoring with answers at the end` or :guilabel:`Scoring without answers at the
end`.

:guilabel:`Scoring with answers at the end` shows the survey participant their answer choices at
the end and which questions they got right or wrong. On the questions they got wrong, it shows
which answer is correct. :guilabel:`Scoring without answers at the end` does not show the survey
participant their answer choices at the end, only their final score.

Then, click on the on the :guilabel:`Questions tab` and click on a question. In the question form,
check the :guilabel:`Is a correct answer` box for the choice that is the correct answer and attach
a score value.

Back on the :guilabel:`Options` tab of the survey, set the :guilabel:`Success %`. The percentage
entered determines what percentage of correct answers is needed to pass the survey.

In the :guilabel:`Options` tab of the survey, the user can also choose to make the survey a
certification. A certification indicates that the survey asks questions to test the participants'
knowledge level on a subject.

If enabling the :guilabel:`Is a certification` option, then choose a :guilabel:`Certification email
template`. The certification will automatically be emailed using this email template to users who
pass the survey with a final score that is greater than or equal to the set :guilabel:`Success %`.

In the :guilabel:`Candidates` section, the user can require participants to log in to take the
survey. If the :guilabel:`Login Required` setting is enabled, two new options appear. The
:guilabel:`Attempts Limit` checkbox appears and can be checked if the user wishes to limit the
number of times a participant can attempt the survey. The option to :guilabel:`Give Badge` appears
beneath the :guilabel:`Certification` options in the :guilabel:`Scoring` section.

.. image:: scoring/required-score-login.png
   :align: center
   :alt: Setting the Required Score (percentage), login required, and certification template.

Badges are related to the eLearning portion of the user's website. Badges are a way to set
milestones and reward the participant for passing surveys and gaining points. Besides the logged-in
user, website visitors who access the :guilabel:`Courses` page will also be able to see the granted
badges.

.. image:: scoring/frontend-badges.png
   :align: center
   :alt: Example of how a badge looks on the eLearning portion of the website.

.. seealso::
   - :doc:`time_random`
