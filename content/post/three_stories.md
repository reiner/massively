+++
title = 'Three stories about a child'
slug = 'three_stories'
image = 'images/threestories.jpg'
date = "2018-08-09T00:00:00"
description = 'Three stories about a child moving to Basel as inspiration for TWIST-projects'
+++

Imagine you are a 6 year old child. And you plan to live in a cozy neighborhood in the wonderful city of Basel. Your first day of school will be on Monday – how exciting! But first you have to find a place to live... Imagine further, that you have a decent flair for open statistical data (under open use license) and quite a talent for programming. So you are probably the first ever kid on this world that is able to code before even being able to write in his mother tongue – how weird… But hey, it’s all about imagination! So you start to listen to some music…

#### 1. It’s (not) all about the money – but spatial data

<img src="/images/chapter1.jpg" width="100%"/><br>

So, imagine: your parents plan to move from Zurich to Basel soon – the best decision ever, you think. You are keen to meet all the cool people in this charming city at the Rhine. Usually, the rent is an important criterion when moving to a new apartment. But hey, you are 6 years old and don’t care about money! So you are primarily concerned about the best place to easily get in contact with your future friends. Which area has the highest share in children and young people? Which the greatest social diversity? Where are the green areas? And – you really hate them – where is the probability lowest to meet dogs in your neighborhood? After all, your mum says she would like to live in a place where one doesn’t need a car. And your dad always wanted to test his self-made burglar alarm –don’t ask why. So let’s look for a place that meets all your family’s needs: Many burglaries, not many registered private cars, almost no registered dogs – and some cool friends for yourself.

On [www.basleratlas.ch](https://www.basleratlas.ch) you happen to find all the relevant data and easily visualize it in different maps. Not bad, this gives a good first impression, your longing for Basel already noticeably increases.
 
<a target="_blank" href="https://basleratlas.ch/index.php?indics=11_fahrzeuge.11_motorisierungsgrad&serie=2016&indics2=11_fahrzeuge.personenwagen_anz&serie2=2016&view=map5&lang=de&maponly=1">
<img src="/images/geoclip.jpg" alt="basleratlas" width="100%"/>
</a>

But comparing the different data and running spatial analyses with more than one dataset is not really possible. A pity… Then your mom shouts that you should brush your teeth and go to bed. This is the point when you realize that all the data you were looking at is also accessible as CSV from:

http://www.statistik.bs.ch/karten/basler-atlas.html

And hey, there is also a page which provides you a JSON-File including the data structure and all relevant meta-data:

https://basleratlas.ch/geoclip_data_csv.php

Based on this you can get all CSV-data on all available spatial layers in the Basler Atlas by simply complement the link with the parameters from the JSON-File, iID=iID and ngeo=Ebene. For example, for the number of private cars on the spatial layer Block: 

https://basleratlas.ch/geoclip_data_csv.php?iID=personenwagen_anz&ngeo=wbl

You forget about your toothbrush and mentally dive into the possibilities that would emerge when combining these (and maybe even other) data into an application that would allow enhanced spatial analyses and explorations. And so you start coding…

#### 2. We're safe and sound - on our way to school

<img src="/images/chapter2.jpg" alt="safe way to schools" width="100%"/>

So, imagine: you look forward to meeting your new classmates soon. But you want to meet them safe and sound. Remember, you are a six years old, living in the life-threatening environment of a nowadays city – traffic can be deadly, it’s said (at least according to your caring mom). So let’s quickly check if there is some open data available on how safe your way to school is. And hey, what a surprise, it is! The cantonal [Geoportal BS](http://geo.bs.ch/) provides you with a dataset called “Schulwegsicherheit”:

<iframe src="https://map.geo.bs.ch/?lang=de&baselayer_ref=Grundkarte%20grau&tree_groups=Schulwegsicherheit&tree_group_layers_Schulwegsicherheit=SS_Querung%2CSS_Fussweg&map_x=2612208&map_y=1267258&map_zoom=4" width="100%" height="450"></iframe>

[Link to Geoportal with preselected layer](https://map.geo.bs.ch/?lang=de&baselayer_ref=Grundkarte%20grau&tree_groups=Schulwegsicherheit&tree_group_layers_Schulwegsicherheit=SS_Querung%2CSS_Fussweg&map_x=2612208&map_y=1267258&map_zoom=4)

Street crossings are marked according to their safeness, footpaths are available. This looks useful. But also a bit like a labyrinth. Not easy to find the optimal way through it: safe, but still fast. Looks like a route planner is needed. Maybe [graphhopper](http://graphhopper.com), as described in this [tutorial](http://www.liedman.net/leaflet-routing-machine/tutorials/alternative-routers/) ? Fortunately, all data on the Geoportal BS is made available by the WFS-Server [wfs.geo.bs.ch](http://wfs.geo.bs.ch) (and there’s also a [documentation](http://www.geo.bs.ch/geodaten/geodienste/wfsbs.html)) which offers you his capabilities through:

https://wfs.geo.bs.ch/?SERVICE=WFS&VERSION=2.0.0&REQUEST=GetCapabilities 

And by adding the parameter “&outputFormat=geojson” to the GetFeature requests you get your desired data as GEOJSON – how useful!

https://wfs.geo.bs.ch/?service=wfs&version=1.1.0&request=GetFeature&typeNames=SS_SchulwegSicherheit_Querung&srsName=epsg:2056&outputFormat=geojson

https://wfs.geo.bs.ch/?service=wfs&version=1.1.0&request=GetFeature&typeNames=SS_QuerungSym&srsName=epsg:2056&outputFormat=geojson

https://wfs.geo.bs.ch/?service=wfs&version=1.1.0&request=GetFeature&typeNames=SS_Fussweg&srsName=epsg:2056&outputFormat=geojson

You can even check which school would be closest to you by loading all primary schools in Basel:

https://wfs.geo.bs.ch/?service=wfs&version=1.1.0&request=GetFeature&typeNames=SC_Primarschule&srsName=epsg:2056&outputFormat=geojson 

Hm, the vector-data seems to have some topological imperfections, might need some snapping here and there to make it routable. But otherwise it would have been way too easy to implement, wouldn’t it! ;-) So you start coding…

####  3. In the year 2525 – or maybe 2035

<img src="/images/chapter3.jpg" alt="safe way to schools" width="100%"/><br>

So, imagine: your first day at school was somewhat promising. Really cool kids from many different countries. You already made some new friends by showing them your brand new app “Cool2School” – which was already downloaded by all 8480 kids at the age of 5-9 in Basel. But having met so many beautiful people this day, back home you start wondering: Will we still be friends in 17 years? Where will we all live then? Still in the same area of Basel? Or in Zurich, again? What is supposable? Would be cool to have some Open Data on the future population of Basel and Zurich to see what kind of people will be living in which part of which city. And how probable is it that you and your new friends will still be here?

Good to know that Basel and Zurich (city and canton) just recently published their population scenarios:

https://opendata.swiss/de/dataset/bevolkerungsszenarien

https://opendata.swiss/de/dataset/bevolkerungsszenarien-2017-2030

https://statistik.zh.ch/internet/justiz_inneres/statistik/de/daten/daten_bevoelkerung_soziales/bevprognosen.html

(Comparing them with the [cantonal scenarios](https://www.bfs.admin.ch/bfs/de/home/statistiken/bevoelkerung/zukuenftige-entwicklung/kantonale-szenarien.html) published by the Federal Statistical Office could be interesting. Modelling population is not “exact science”…)

Remember the charts you saw some weeks ago, visualizing future population in an interactive and appealing way ([this](https://service.destatis.de/bevoelkerungspyramide/) and [that](https://service.destatis.de/laenderpyramiden/) one)? Why not trying to visualize the population scenarios with such a d3-application? Or alternatively with the [d3-visualization-library](https://statistikstadtzuerich.github.io/sszvis/#/beginners) of Statistik Stadt Zurich?  


Your classmates will be impressed again tomorrow! So you start coding…

<center><h4>REGISTER NOW FOR THE TWIST-Hackdays!</h4></center>

<center><a target="_blank" href="https://www.eventbrite.de/e/twist-2018-tickets-44099503803" class="button back alt2">Register Now!</a></center>
