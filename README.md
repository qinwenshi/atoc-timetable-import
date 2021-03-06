atoc-timetable-import
=====================

Import the ATOC Timetable Feed into MongoDB using PHP.

This is a really simple script that sacrifices optimization for clarity of understanding.

Currently the source is provided for anyone interested in how a rail data import and API might fit together, but at best should be considered "Alpha" release. That said, I welcome feedback on the project even as it stands.


Data Sources
============
Date is provided at http://data.atoc.org/data-download - You'll need to sign up to get access.

Data Format Documentation
=========================
The data format documentation is lifted directly from the ATOC CIF documentation.
In many fields the data is padded with whitespace so it's important to trim() the values before inserting them into MongoDB.


REST Based API
==============
Under the public directory is the foundation of a REST API, using the PHP Micro Framework Flight. 
Some of the code requires PHP 5.4, mostly because I used the new [] format for defining Arrays.

Compatability Note
==================
Currently the API and datastructure are unversioned, and could change drastically in between commits. 


Casting of Data
===============
Because we plan to put the data into MongoDB where strings and numbers query differently, we cast strings as such when we need to make sure PHP doesn't miss identify a value as a number.

Licence
=======
This code is provided as is, without warranty.

FAQ
===
How Long Does The Import Take?
------------------------------
On a virtual machine running on Windows 8, with SSD the import takes around 10 mins. On a Bytemark BigV VM, using SATA disks it takes around 20 mins.

Is There A Slide Show About Why You Made This and How It Works?
---------------------------------------------------------------
Funny you should ask, there's a copy of the slides from my Liverpool Geek Up Talk at: https://docs.google.com/presentation/d/1IlP-BNhZckibUC8D6k79npmsMsi-x3IkfjfJ_Z-16Vs/edit?usp=sharing
