========================================================================
SARS-CoV-2 Submissions Workshop
========================================================================

Introduction
------------
In this workshop, we will step through the available options to submit SARS-CoV-2 data to the European 
Nucleotide Archive using example data. For a complete submissions guide, please see 
`here <sars-cov-2-submissions>`_.

Metadata Model Guide
====================
Before submitting any data, it is important to understand
the structure of our 
`metadata model <https://ena-docs.readthedocs.io/en/latest/submit/general-guide/metadata.html>`_.
This model is used, not only for SARS-CoV-2 data, but data from across the tree of life. In this 
short video, I will touch on the importance of each element of the model and what data/metadata each
object holds.

.. raw :: html

    <div style="position: relative; overflow: hidden; max-width: 100%; height: 350;">
        <iframe width=100% height=350 src="https://www.youtube.com/embed/p2-mE45Ezyk" title="ENA: an introduction" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </div><br>


Submission Routes
=================

* programmatic: most suitable for high-throughput, frequent submissions and automated systems
* interactive: most suitable for infrequent submission, or those more comfortable with spreadsheets
* drag-and-drop uploader: most suitable for once-off submission

.. note ::
    We will use the test servers for this workshop. These service URLs begin with `wwwdev`
    instead of `www`. Submissions to this service are removed nightly. 


Workshop Setup
==============
Before we begin, please download the example data `here <###TODO####>`_ and unzip it.

For this tutorial, you will need:
- a means to view/edit spreadsheets in Microsoft Excel format and a text editor,
ideally something with syntax highlighting for XML formatted files.
- a command line utility with `cURL <https://curl.se/>`_ installed.
- a Webin account. If you don't already have one, please register `here <https://www.ebi.ac.uk/ena/submit/webin/accountInfo>`_.


Registering a Study
-------------------
Let's start by registering a study. There are 2 ways to do so: interactively through our 
`Webin Submission Portal <https://wwwdev.ebi.ac.uk/ena/submit/webin/login>`_, or programmatically
using cURL.

Interactive
===========

Head over to the `Webin Submission Portal <https://wwwdev.ebi.ac.uk/ena/submit/webin/login>`_
and log in using your Webin credentials to access the landing page.  Here, menus are color-coded
in line with the metadata model. Study-related items are in yellow. Click on the 'Register Study'
button.

.. image :: ../images/wsp_landing.register_study.png

Fill out info here:

.. image :: ../images/wsp.register_study.png

.. image :: ../images/wsp_accessions.register_study.png

You're done!

Programmatic
============

For this, we will use XML files.
