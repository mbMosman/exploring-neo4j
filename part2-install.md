---
layout: default
---

## Neo4J Overview: Installation & Getting Started

Neo4j has several install options depending on whether you are interested in the Community Edition or the Enterprise Edition.  The open source Community Edition is free of charge and offers the base database without support.  The Enterprise Edition offers additional features for high availability and clustering, but requires a purchase although a 30-day trial is available. There is also an option to work with a sandbox online to learn without installing anything.

### Getting Started
I will walk through the steps to install and work with the Community Edition.  There is a Mac install of Neo4j packaged as a dmg file for easy install, just download and click to install.  When you first open the application, you will need to acknowledge that you do really want to open the application, since it was downloaded from the web, and then it will prompt you to enter a location for your database.

{% include figure.html
    src = "/images/config-db-location.png"
    alt="Screenshot of initial configuration screen."
%}

Click Options… to alter any defaults such as cache settings, port bindings, Java VM settings, or the location of any Neo4j plug-ins or extensions that should be used.

{% include figure.html
    src = "/images/config-options.png"
    alt="Screenshot of configuration options screen."
%}

To start the database, click the Start button.  When ready, a green message with a link appears.

{% include figure.html
    src = "/images/config-db-started.png"
    alt="Screenshot of initial screen showing database started with connection URL."
%}

### Browser Application
Clicking the link will bring up the database admin tools in your web browser.  You can log in with the default password (shown on the screen), but will then be prompted to change the password.  Once you are logged in and connected, the options along the left side will allow you to:

| <img src="{{ "/images/icon-db.png" | prepend: site.baseurl }}" alt="database icon" width="35px" height="35px" style="max-width:100%;"> | view information about your database
| <img src="{{ "/images/icon-favs.png" | prepend: site.baseurl }}" alt="favorites icon" width="35px" height="35px" style="max-width:100%;"> | bookmark favorite scripts or queries
| <img src="{{ "/images/icon-docs.png" | prepend: site.baseurl }}" alt="docs icon" width="35px" height="35px" style="max-width:100%;"> | view the documentation and reference material
| <img src="{{ "/images/icon-cloud.png" | prepend: site.baseurl }}" alt="cloud icon" width="35px" height="35px" style="max-width:100%;"> | manage your local data and work with the cloud sync feature
| <img src="{{ "/images/icon-settings.png" | prepend: site.baseurl }}" alt="settings icon" width="35px" height="35px" style="max-width:100%;"> | modify the default settings
| <img src="{{ "/images/icon-about.png" | prepend: site.baseurl }}" alt="about icon" width="35px" height="35px" style="max-width:100%;"> | view information about Neo4j and the current version

There are also a series of tutorial demonstrations to help you learn more about neo4j and Cypher the graph query language.

{% include figure.html
    src = "/images/initial-admin-page.png"
    alt="Screenshot of admin screen showing tutorial options."
%}

By selecting the “Jump into code” option shown in the middle, you can begin exploring the sample datasets that are provided with the install:

- Movie Graph – a dataset that allows you to explore a graph and common query patterns
- Northwind Graph – the RDBMS Northwind data example which demonstrates loading data from a CSV file and how to convert RDBMS schemas to a graph structure
- Query Templates – templates to generate Cypher statements and generate nodes and relationships


### Exploring with Movie Graph Data
The Movie Graph is a great place to start if you just want to learn how to get started with new data.  The first part of the tutorial gives you a sample command that will load the data into the current database.  The create queries are over 100 lines, but here is a sample section that illustrates the structure.

{% include figure.html
    src = "/images/movies-create-sample.png"
    alt = "Part of the movie dataset create query."
%}

Once the data is loaded, you can explore the graph nodes and relationships.

{% include figure.html
    src = "/images/movies-graph-sample.png"
    alt = "Part of the movie dataset create query."
%}

Overall, I was very impressed with this tutorial. It is pleasantly interactive and offers a variety of different query types to help you get familiar with both the query language and the set-up of the nodes and relationships in the dataset. One of the more interesting queries allows you to see how many people are related within 4 levels of the graph to Kevin Bacon.

<pre>
MATCH (bacon:Person {name:"Kevin Bacon"})-[\*1..4]-(hollywood)
RETURN DISTINCT hollywood
</pre>

{% include figure.html
    src = "/images/kevin-bacon-query.png"
    alt = "4 degrees of Kevin Bacon query and results."
%}

Wow!  That’s 135 nodes:  27 Movies and 108 People.  

### Wrap-up
Overall the installation and setup was very simple. You really can be up and running in minutes.  While these screenshots are from a Mac install, I also walked through the install process on Windows and it was equally straightforward.  There is also a [video walkthrough](https://youtu.be/0FO81O-nTrc), but really there wasn’t much room to go astray.  There are numerous developer resources, both tutorial videos and web and PDF documentation.  Neo4j is amazingly developer friendly.


### References
- Neo4j. (n.d.). Retrieved September 22, 2016, from Neo4j: Get Started: [https://neo4j.com/developer/get-started/]()
- Neo4j. (2016, 9 2). 4 Minutes on Installing and Getting Started Using. Retrieved from YouTube.com: [https://youtu.be/0FO81O-nTrc]()
