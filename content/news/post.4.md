+++
title = 'Crowdsourced open data from «Züri wie neu»'
slug = 'zueri_wie_neu'
image = 'images/openspending.jpg'
date = "2018-05-05T00:00:00"
description = 'Get your hands on crowdsourced "Züri wie neu"-data at the TWIST-Hackdays!'
+++

While we strive to publish as many interesting new open data for TWIST as possible, it is worth taking a look at already existing open data. In this post we would like to give you a brief outlook over the crowdsourced open data from the application [«Züri wie neu»](https://www.zueriwieneu.ch/). We think that there are still some hidden, so far undiscovered, truths to be found in it.

#### The application and derived open data  ##
[«Züri wie neu»](https://www.zueriwieneu.ch/) is an online platform of the Zurich city administration in order to facilitate the reporting of damaged infrastructure by citizens. It went online in 2013. Since then it is moderated by the city administration and managed transparently with all – anonymized - reports available as open data. 

<img src="http://statistik.stadt-zuerich.ch/Modules/ogd_bspe/twist/zwn/zwn.png" alt="Züri wie neu Application" width="90%"/><br>

The [open dataset derived from «Züri wie neu»](https://data.stadt-zuerich.ch/dataset/zueriwieneu-meldungen) currently contains around 14’000 reports (!). It includes the exact georeferenced location of the infrastructure damage, the time of recording, the exact description, the categorisation, the processing status and the time when the report was completed. For approximately 1’700 messages, even transmitted photos can be referred to it. All data is available in open geo formats and can also be queried via the [open interface Open311](https://de.wikipedia.org/wiki/Open311). Open311 is an open standard ([GeoReport v2](http://wiki.open311.org/GeoReport_v2/)), which is used internationally by numerous other cities, such as e.g. Bonn, Toronto or Lisbon. This makes the data comparable with [other cities]( http://wiki.open311.org/GeoReport_v2/Servers/).

#### Use cases 
It is obvious that the spatial and temporal components of these data usually invite for geo analysis and cartographic visualisations, such as heatmaps or animated maps. Here is an example of an animation which shows all new entries by citizens in 2017.

<img src="http://statistik.stadt-zuerich.ch/modules/ogd_bspe/twist/zwn/ezgif_zwn_2017Plus.gif" alt="animation zwn reports in 2017" width="90%"/><br>

But there might be further interesting facts hidden in the data. The precise descriptions of the damage written by the users seem especially interesting. Since it is unstructured text, an analysis for interesting patterns might be a non-trivial challenge to master at the TWIST-Hackdays.

In the media, «Züri wie neu» was often described as a [«sourpuss-app»](http://www.20min.ch/schweiz/zuerich/story/Die--Noergler-App--ist-ein-Erfolg-14633442). But is this really the case or can this claim be refuted?

It would also be interesting to know how different factors, such as for example the weather, seasons, holidays, rein dates, major events or the ascent and descent of the O-bikes impact the reports. 

Furthermore, it could be helpful for the administration, if the category of the detail description could be automatically derived from the text and/or a picture in order to be assigned to the responsible office. The dataset is thus well suited for machine-learning based classification techniques.

Or would it even be possible to predict certain damages by meshing the data up with different other open data (e.g. population structure, infrastructure or social media)?

The data certainly invites to play around and come up with novel insights or unconventional ideas. For example in 2017 all report titles have been stored and colored according to its category and been put into one big poster for the exhibition [«Urban Data Patterns»](http://hahn-zimmermann.ch/projekte/urban-data-patterns).

<img src="http://statistik.stadt-zuerich.ch/modules/ogd_bspe/twist/zwn/urbanPatterns_long_HZ_1_4_01.jpg" alt="full extent of the printout"/>

<img src="http://statistik.stadt-zuerich.ch/modules/ogd_bspe/twist/zwn/urbanPatterns_detail_HZ_1_4_01.jpg" alt="detail of the printout"/>

<img src="http://statistik.stadt-zuerich.ch/modules/ogd_bspe/twist/zwn/urbanPatterns_piles_HZ_1_4_01.jpg" alt="piled after categories"/><br>


#### Further Links: 
- Detailed study results carried out at the UNI Bern: https://zueriwieneu.fdn.iwi.unibe.ch/ 
- Art project «urban data patterns»: http://hahn-zimmermann.ch/projekte/urban-data-patterns 
