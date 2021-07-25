# Navigo3 workflow

## Introduction
Navigo3 is based on ist's own API library developed by [Jaroslav Kuboš](https://kubos.cz) called [dry-api](https://github.com/NavigoSolutions/dry-api), [Jooq](https://www.jooq.org/")(Java library for building access classes to the database), [Immutables]("https://immutables.github.io/)(Java library for automated creating immutable objects), [Jackson](https://github.com/FasterXML/jackson)(Java library for JSON (de)serialization),... on the backend side.
On the frontend side is Navigo3 based on [React.js](https://reactjs.org/) with [Webpack](https://webpack.js.org/) as bundling tool.


## Backend
  ### Tools
    - IDE - Eclipse
    - Server - Tomcat
    - Resource bundle editor - Eclipse plugin for editing translations
    - Gradle - tool for handling dependencies
    - GIT
    - Database - Postgres
    - Jenkins - Automated buils from git repository
  ### API method structure
    Each java api method is constructed from two java classes.
    One from the Endpoint including the the data input type,\data output type, description and it's name (used for calling).
    The secondone is the Implementation class containing  
    methods for filling some metadata, security(privileges in Navigo3), validation and execution.
    These methods are automaticly implemented by interface.\Both classes has generic arguments for input and output type
    Implementation has onemore for the endpoint class.
 ### Creating item in Navigo3
   #### Listed items with form
        Each of this part of Navigo3 is based on classes:
         - ItemName - Immutable Interface defining properties of the Item
         - GetDefaultItemName(Endpoint,Impl) - returns a default data of ItemName
         - GetItemName(Endpoint, Impl) - returns data of the existing Item
         - UpsertItemName(Endpoint, Impl) - validates form input and upserts data of the Item
         - ListItemName(Endpoint, Impl) - returns the list of existing Items
   #### Filtered items
         - ItemNameFilterMethods - class for filtering items, mostly called from ListItemName
         - ItemNameFilter - Immutable Interface definig the filter properties
         - ItemNameSearchResult -  defines the result of the filtering
