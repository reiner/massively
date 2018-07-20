+++
title = 'Give your address a position. Give your position an address.'
slug = 'opengeocoder'
image = 'images/geocoder.jpg'
date = "2018-07-20T00:00:00"
description = 'Participate at the TWIST-Hackdays and contribute to develop an open geocoder'
+++

#### Geocoding and reverse geocoding

Addresses represent an important reference dataset for data analyses. In the GIS domain addresses are the essential basis for customer- and business analyses.
Addresses are also pervasive on the web. When we search for directions on google maps we use addresses: behind the scene, these addresses are converted to geographic coordinates, which are then used for the routing analysis. 
Now the other way around. When we click on a street in google maps we get a tooltip showing the address information of that location: behind the scene, geographic coordinates are converted to addresses. The process of converting addresses to geographic coordinates is called **geocoding**, while the inverse process (converting geographic coordinates to addresses) is called reverse geocoding.
We call **geocoder** the tool implementing these functionalities: a geocoder has two main components: a reference dataset and a geocoding algorithm.

#### The Federal Registry of Building and Housing

Since July 2017 the Federal Office of Statistics is publishing the Federal Registry of Buildings and Housing with a CC-BY like license. This is an interim solution, before swisstopo will publish the official registries of streets and building addresses starting from July 2021.
The dataset is published via the Federal Geoportal and is accessible as raw data or via the GeoAdmin API.

#### Let’s implement an open geocoder!

We encourage participants at TWIST to implement, with language of their choice (R, Python, etc.), an open geocoder on top of the mentioned dataset.

## Data source

[Raw data](https://data.geo.admin.ch/ch.bfs.gebaeude_wohnungs_register/)   
[GeoAdmin API](http://api3.geo.admin.ch/services/sdiservices.html#search)
