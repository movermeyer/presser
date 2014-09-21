============
Presser v0.1
============

.. image:: https://coveralls.io/repos/ladyrassilon/presser/badge.png?branch=master 
    :target: https://coveralls.io/r/ladyrassilon/presser?branch=master
.. image:: https://travis-ci.org/ladyrassilon/presser.svg?branch=master
    :target: https://travis-ci.org/ladyrassilon/presser
.. image:: https://pypip.in/version/Presser/badge.svg
    :target: https://pypi.python.org/pypi/Presser/
    :alt: Latest Version
.. image:: https://pypip.in/implementation/Presser/badge.svg
    :target: https://pypi.python.org/pypi/Presser/
    :alt: Supported Python implementations
.. image:: https://pypip.in/status/Presser/badge.svg
    :target: https://pypi.python.org/pypi/Presser/
    :alt: Development Status


| This is a simple library that attempts to extract the data for a vine from a given vine.co URL. Its a little rough and ready, and given that Vine can change their page design at any time, cannot be guaranteed to work.

| You'll want to keep an eye out for PresserJavaScriptParseError because this will probably indicate that this is the case.

| You will need Node installed, it does the evaluation of the javascript for more stable javascript data extraction. I am looking to find a viable alternative so the package will not be node dependent, but as yet, I've not found a viable alternative.

However, here is the example usage::

    from presser.presser import Presser
    press = Presser()
    
    #For a vine id
    vine = press.get_data_for_vine_id("OBiwWuBm0Eg")
    
    #For a vine url
    vine = press.get_data_for_vine_from_url("https://vine.co/v/OBiwWuBm0Eg")
    
    vine.keys()
    vine["avatarUrl"]
    
Warning
^^^^^^^
Vine does not permit scraping, so please do not use this in an automated fashion, but it should be okay if your workflow simplifies and speeds up the workflow of a user going to an url and extracting the data manually. 

| If you try to do large batches of vine urls for extraction in a short period of time, then you will probably annoy Vine. Don't do this please.