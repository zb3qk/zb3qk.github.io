---
layout: post
author: Zachary Bilmen
topics: [ 'Angular', 'Ionic', 'Django']
tags: Carrier
---
Carrier is an application I envisioned to be the crossroads of all other work I am doing at UVa. The idea of it is to be a display of various media so that you may showcase, preview, and analyze files on your computer from anywhere. 

The stack for this is a Django server powered by various python libraries installed on your computer (what we shall call a provider) connected to our Global Server (what we shall call a distributor). To view the files, one can download a mobile application designed using Ionic JS and its logic written in Angular. 

## Provider Backend
The provider first scans a folder and all of its children to map the contents to a mySQL database. Whenever a user requests a file, it must go through this database. 

## Distributor Backend
To allow users protection, the distributor uses OAuth. Every user must create an account before using the service. 

## Mobile Frontend
![My helpful screenshot](/assets/images/IMG-4482.JPG =x200)
![My helpful screenshot](/assets/images/IMG-4483.JPG =x200)
![My helpful screenshot](/assets/images/IMG-4484.JPG =x200)
![My helpful screenshot](/assets/images/IMG-4485.JPG =x200)