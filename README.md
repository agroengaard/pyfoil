

<div align="center">
 <img src="./doc/pyfoil.png" width="200">

 <h1 align="center">  PyFoil </h1>
 
  <a href="https://github.com/AndersGroengaard/pyfoil/issues/new?assignees=&labels=bug&template=01_BUG_REPORT.md&title=bug%3A+">Report a Bug</a>
  ·
  <a href="https://github.com/AndersGroengaard/pyfoil/issues/new?assignees=&labels=enhancement&template=02_FEATURE_REQUEST.md&title=feat%3A+">Request a Feature</a>
  .
  <a href="https://github.com/AndersGroengaard/pyfoil/discussions">Ask a Question</a>
</div>

<br/>


<div align="center">

[![Generic badge](https://img.shields.io/badge/Python-3.9-blue)]()
[![Generic badge](https://img.shields.io/badge/version-0.1.0_a-green)]()
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
![Size](https://img.shields.io/github/repo-size/AndersGroengaard/pyfoil)
 
</div>

<br /><br />
_Repository containing python scripts for generating or fetching various airfoils_

 

<!-- TABLE OF CONTENTS -->
<h2 id="table-of-contents"> :book: Table of Contents</h2>

<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about"> ➤ About </a></li>
    <li><a href="#features"> ➤ Features</a></li>
    <li><a href="#planned-features"> ➤ Planned Features</a></li>
    <li><a href="#limitations"> ➤ Limitations</a></li>
    <li><a href="#license"> ➤ License</a></li>
  </ol>
</details>
 
<!-- ABOUT THE PROJECT -->
<h2 id="about"> :clipboard: About</h2>
 
<p align="justify"> 
   The intended purpose of this package is to serve as a tool to find the best airfoil shape for your engineering application.
 
   I hope you make some efficient wind (or water!) turbines for some renewable energy, and/or energy-efficient vehicles :airplane: so we can save the planet :earth_africa: 
</p>





<br/><br/>


<!-- Features -->
<h2 id="features"> :dart: FEATURES </h2>

* <b> Generate one, more or all NACA Airfoils: </b>

 Foils are generated in according to the definition stated on the  <a href="https://m-selig.ae.illinois.edu/ads/coord_database.html" > UIUC Airfoil Coordinates Database </a, in which they stated:

> "The coordinates order starts from upper surface trailing edge, then wraps around the leading edge to the lower surface trailing edge"

<!-- Features -->
<h2 id="planned-features"> :goal_net: PLANNED FEATURES </h2>

* Fetch historical airfoils
* Create multi-element airfoils.
* Load a datasheet with a timeseries of wind speeds and angles of attacks, and find the best performing airfoil in terms of lift-to-drag ratio.

<!-- Limitations -->
<h2 id="limitations"> :warning:  Limitations  :warning: </h2>
 
<p align="justify"> 
   WORK IN PROGRESS -> Trying to salvage this project from some old local storage at the moment, but will have the full GUI up at some point, hopefully with some improvements :-)
I would like to turn this into a full Python package at some point
</p>



Locally, I had made a prototype for generating multi-element airfoils, which in its GUI form looked like this:

<img src="./doc/gui.png" width="700">

Which gives a rough direction of what I would like to achieve


<br/><br/>

## :man_technologist: How to use :woman_technologist: 





To create 4 and 5 digit NACA airfoil points by code, and also plot and save them, you could write (See also the example.py file):

```python

from naca import NACA

# NACA 4-Digit airfoil:
airfoil = NACA("2310")

# Retrieve the individual points:
pts = airfoil.pts 

# Plot the airfoil:
airfoil.plot()

# Save the points to a .txt file 
airfoil.save()  
```
Likewise for a 5-digit NACA airfoil:

```python
# NACA 5-Digit airfoil:
airfoil = NACA("23116")
airfoil.plot()
airfoil.save()
 
```

If you want to generate and plot multiple airfoils from a list you could go:

```python
from naca import NACAs, PlotFoil

my_foils = ['2312', '23123', '5212']

foils = NACAs.generate_NACA_foils(my_foils)
PlotFoil.all_from_list(foils)
```

## Authors

Written by Anders Grøngaard [@AndersGroengaard](https://github.com/AndersGroengaard)

 

<h2 id="license"> :book: License</h2>

This project is licensed under a GNU GENERAL PUBLIC LICENSE - see the LICENSE.md file for details


