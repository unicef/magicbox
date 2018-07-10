##############################
GitHub workflow best practices
##############################

The UNICEF Innovation development team uses GitHub to host open source projects.
This document explains the GitHub workflow maintainers and developers use.
It also offers suggestions for best practices on using available tools and integrations.

This document explains…

- How to make a new GitHub repository

- How to maintain a GitHub repository

- How to communicate effectively


***********************************
How to make a new GitHub repository
***********************************

This section explains steps to follow when creating a new GitHub repository.
These makes projects more organized, easier to follow from an outsider's perspective, and boosts visibility of development.

Repository creation
===================

These steps focus on the initial repository creation, from `github.com/new <https://github.com/new>`_.

#. **Set a meaningful name**:

    - Try to make purpose obvious in title

    - Use hyphens (``-``) instead of underscores (``_``)

#. **Write a description**: Write one or two sentences to quickly describe the project

#. **Initialize with README**: Check to add a ``README.md`` file

    - If one is not yet written, initialize one

#. **Add .gitignore for project type**: Find project's programming language and choose its ``.gitignore`` file, if available

#. **Add BSD-3 Clause license**: Standard license used for UNICEF Innovation projects

.. figure:: /_static/github-workflow-create-new-repo.png
   :alt: Example of creating a new repository

   Example of creating a new repository

Configure repository
====================

Now, the repository is created.
Make sure these settings are updated:

Disable unneeded tools
----------------------

Disable any unneeded features or repository tools.
If they are needed, they can be turned on again later.
Turning off unneeded features makes it easier for someone to find the useful places in the project.
It can also indicate if the thing they are looking for (e.g. documentation) is somewhere else.

These features are found under the *Settings* menu for every repository.

.. figure:: /_static/github-workflow-disable-features.png
   :alt: Disable unneeded tools, like a wiki or project boards

   Disable unneeded tools, like a wiki or project boards.
   There may be documentation or project boards set up elsewhere.
   This does not disable organization-level project boards.

Set description, URL, topic tags
--------------------------------

Make sure every repository has a description and topic tags set.
If there is a URL to view a demo of the project or read more about it, include it too.

At the top of every GitHub repository, there are fields of metadata for a description, a URL, and topic tags.
A description and URL helps someone understand tge project in one or two sentences or see a live demo.
Topic tags raise visibility in the GitHub ecosystem and help other people discover new projects.

.. figure:: /_static/github-workflow-description-tags-empty.png
   :alt: Example of no description, URL, or topic tags

   Example of no description, URL, or topic tags

Do not leave a repository empty like this.
Use the *Edit* button on the right to change the description and URL.
Two text boxes will appear.

For topic tags, click *Add topics* towards the left.
Choose tags related to your project to help identify it.
Consider programming languages, frameworks, or other software used.
Tags like ``humanitarian`` or ``united-nations`` are also examples of tags for types of software.

.. figure:: /_static/github-workflow-description-tags-filled.png
   :alt: magicbox-latlon-admin-server with description and topic tags

   magicbox-latlon-admin-server with description and topic tags

Set up useful labels
====================

Labels are visual organization tools for your GitHub project.
They make issues easier to sort and prioritize tasks.
Additionally, they also help new contributors identify areas of interest for your project.
They can help improve awareness of different types of contribution methods in your project (e.g. design and documentation tasks).

Configure each repository's labels in a way that makes sense for your project.
The labels should mean something to *you* so they are easily applied for sorting later.
Every repository's issue and pull request labels are found under the *Issues* tab with the *Labels* button.

.. figure:: /_static/github-workflow-labels-menu.png
   :alt: Click the Labels button towards the right of the search bar

   Click the *Labels* button towards the right of the search bar

A good example of labels is `here <https://github.com/unicef/magicbox/labels>`_ on the `unicef/magicbox`_ repository. (To view the color code for a given label, click the "Edit" on its row.)

Not all of these labels will be helpful for a new project.
Take ones that make sense, and make new labels specific to the project, if needed.

Set up continuous integration (CI)
==================================

.. note:: To be written.

Set up code health checks with CodeClimate
==========================================

.. note:: To be written.


***********************************
How to maintain a GitHub repository
***********************************

This section focuses on "housekeeping" with GitHub projects, including labels and project boards.

Housekeeping is important to maintain a repository.
This organizes bugs, feature requests, and the project itself.
Organized projects help active contributors stay on track and make realistic deadlines.
It also helps new contributors understand what is going on.

Housekeeping has five parts:

#. Issue metadata

#. Adding labels

#. Updating project boards

#. Making pull requests

#. Reviewing pull requests

Update issue and pull request metadata
======================================

Every GitHub issue and pull request has four metadata properties:

#. **Assignees**: Who is currently working on this and who is the best point-of-contact for updates

#. **Labels**: Visual cues on task status and importance (see below)

#. **Projects**: Advanced business process management (see below)

#. **Milestone**: Relevant feature or version milestone for an issue or pull request

Assignees and labels should always be used at a minimum.
Use projects and milestones when they are available.

.. figure:: /_static/github-workflow-set-issue-metadata.png
   :alt: Set assignees, labels, project boards, and milestones from the side column in every GitHub issue or pull request

   Set assignees, labels, project boards, and milestones from the side column in every GitHub issue or pull request

Adding labels to issues
=======================

Above, labels were mentioned as part of issue and pull request metadata.
Maintaining and using labels is a good habit.
An issue or pull request might have two to four labels, depending on how the project was set up.

If labels are not yet configured, read `Set up useful labels`_.

Once a week, check issues and pull requests to see if tags are up-to-date.
Update or change any labels that are stale (such as priority labels).
Add labels from the metadata sub-menu when you open an issue or pull request.

Updating project boards
=======================

`GitHub project boards <https://help.github.com/articles/about-project-boards/>`_ are an organizational tool for the project.
They use a `kanban-style <https://en.wikipedia.org/wiki/Kanban_(development)>`_ approach to organizing GitHub issues and pull requests.
Our workflow is explained `on Opensource.com <https://opensource.com/article/18/4/keep-your-project-organized-git-repo>`_.

To update and maintain the project boards…

#. Make sure any issues or pull requests not shown are added to the board

#. Ensure important issues are organized by *In progress* or *To Do*

#. Issues not yet ready for consideration go on the backlog

#. All items under *In progress* or *To Do* columns should be GitHub issues, **not** note cards (note cards are okay for the backlog column)

Making pull requests
====================

All major changes to the project should **always be made through a pull request** (PR).
Pull requests are like a registry of changes for a project.
It is easy for someone to see what is going in and out of a project.
Outside contributors will always have to make pull requests, so it is good practice for core / trusted developers to use pull requests too.

Follow contributing guidelines
------------------------------

The contributing guidelines for all MagicBox projects live `in the unicef/magicbox repository <https://github.com/unicef/magicbox/blob/master/.github/CONTRIBUTING.md>`_.

Always follow these contributing guidelines when working in the project.
These are the standards and rules we ask the community to follow when contributing.
As project maintainers, it is our responsibility to hold ourselves to the same standards we ask of others.
Thus, always make sure current development practices are in-line with what our guidelines.

Write useful commit messages
----------------------------

Writing useful commit messages is a good practice to follow.
When looking through project commits, it should be somewhat clear what has changed in the project and how.
Short or nondescript commit messages are not helpful to maintainers or new contributors.
Commit messages do not need to be paragraphs, but they should clearly indicate what changed or why something changed.

Read `this blog post <https://nathanleclaire.com/blog/2014/09/14/dont-be-scared-of-git-rebase/>`_ for more information about keeping git history clean and tidy with ``git rebase``.

Reviewing pull requests
=======================

.. note:: To be written.

- triage, triage, triage
- CI
- health checks
- code review comments


*******************************
Communicating about development
*******************************

Communication about development should be kept public as much as possible in `our Gitter chat <https://gitter.im/unicef-innovation-dev/Lobby>`_.
Whenever you make a new pull request, always share the link in the main Gitter chat room.
This lets other developers know you made a change and also gives them an opportunity to review your code.
And if you want a code review, be sure to ask for it too.

.. _`unicef/magicbox`: https://github.com/unicef/magicbox
