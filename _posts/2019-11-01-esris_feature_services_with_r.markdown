---
layout: post
title:      "ESRI's Feature Services with R"
date:       2019-11-01 20:20:30 +0000
permalink:  esris_feature_services_with_r
---


I've been doing a lot of R coding the last month or so for work and I've been doing some really fun stuff with GIS datasets hosted on ESRI SDE servers. I've read a lot about their RESTful API's for map and feature services and thought I would write up a quick reference for using those. 

ESRI's geodatabases are really just like any other database, although maybe less easy to work with from the backend perspective. But in essence you have a database on a server that holds data. Easy! In these databases though we hold tables of spatial data as well as tables of other data and images. If you host this data you can publish it to a map or a feature service using ESRI's enterprise software package. 

Map services and feature services really do about the same thing but allow different access to the data to the end users. The map services don't allow you to play around with data for individual features like points, lines, or polygons. They are really just meant to be a way to server up maps. Using feature services is really where we start to see the restful way of life come to the forefront. Just like in our ruby on rails projects we start to hit api's at things like <your url>/feature/1. This obviously will serve up data on Feature 1 of the feature layer. 

Having worked with the ESRI api for these services for a few weeks there are a few things I've learned that might make someone else looking into these stuff ease into things a bit better:

* In order to construct the query for the api you need to add a ? at the end of your url. That will allow you to add options to the request like which feilds are returned, or if you get the geometry data returned as well as the property data.
* If you want to query a feature layer for features that fit some kind of criteria, you need to add a query="" parameter like this:   https://my.awesome.esri.server/FeatureService/2/query?f=json&ATTRIBUTE=5
* If you hit an api for a single feature, you'll only get a json of certain attributes about the layer, not necessarily the data pertaining to the feature in question. If you use the parameter outFields=" * " you will get all the fields associated with the feature like you would in the attribute table of ArcMap or ArcGIS Pro.
* Related data is harder to work with. You need to have set up a relationship class in the geodatabase between the geometry and whatever table you want to relate to that geometry. Once that relationship class is established, you can use the ?queryRelatedFeatures parameter just like the query parameter above.
* I personally use the f=json parameter in almost all my api hits so the data comes out in a nice easy to use format. But you can also have the data come out as HTML, raw, or even GeoJSONs if the server is setup to handle those kinds of requests.

Hope that's helpful! Using R with ESRI products has been a fun rabbit hole and I'm really excited to see where it takes me next.
