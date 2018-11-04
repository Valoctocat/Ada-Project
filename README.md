# Think Global Buy Local!  

# Abstract

- **What**: A lot of food is being imported throughout the year to have constant stock independently of food season products. In Switzerland, 48% of consumed food is imported. The possibility to promote local agriculture was an issue at stake during the  [last votations in Switzerland](https://www.bfs.admin.ch/bfs/fr/home/statistiques/politique/votations/annee-2018/2018-09-23/souverainete-alimentaire.html#-1194286177).
- **Why**: Local food keeps local land in production and local money in the community. It often costs less than classic produced food and builds community relations. Decentralized production also reduces food safety risks, as long-distance food can potentially be contaminated at many points on its journey to our plates. Reducing the distance in food transportation would also reduce greenhouse gas emission.
- **How**: [Open Food Facts](https://world.openfoodfacts.org/) dataset gives some good insights towards foods origins...It gathers information about food products around the world as the ingredients, origin of ingredients, nutrition factors, manufacturing places, countries where they are sold.


# Research questions
- From which countries does food mainly come from ? 
- What are the main categories of food product being imported ? Is this justified?
( Maybe :- What is the share of those product that are bio? What are their carbon print ? Is there any correlation between packaging and distance travelled ?  )
- Is it possible to infer on the food origins based on the product features (ingredients, brand if available, Country, etc.) using machine learning implementations(Neural Network, Random Forest)? Can we cluster some products based on the origin of their ingredients ?

# Dataset

[Open Food Facts](https://world.openfoodfacts.org/) will be the main dataset used for our analysis. It is a collaborative, free and open database of food products from around the world, completed by volunteers. It is available on the EPFL IC cluster or publicly [here](https://world.openfoodfacts.org/data). Origins of ingredients are labelled under the *origins* feature, which will be our starting point for this subject.

OFF gathers data of more than 600k products, but only 40k have labelled ingredient origins, which accounts for roughly 6% of the dataset. However, this should still be enough for a first analysis of the product importations. Other ways to enrich the dataset could be interesting, but have not been found yet as this unique project started recently (in 2012) and is still growing. Therefore, any statistical conclusion from the analysis will need to be studied carefully due to the small size of the population sample.

As the OFF project started in France, the dataset gathers mostly food products sold in French stores. Therefore, imformation about the situation in other countries may be less representative. 

Data cleaning will be a big part of this analysis as the project is open-sourced : anyone can contribute and add their favorite (or not!) products. This leads to inconsistencies and unnormalized data. As a brief example some origins are labelled with a '?', probably meaning that the origin is unknown.

Dataset is at the time of the project only 1.6 GB, available in CSV format. It will be processed using the Apache Spark API to handle the distributed informations in the cluster. Analysis tasks will be performed locally for conveniency. However, any Machine Learning task should be performed on the cluster for its computational power.

# A list of internal milestones up until project milestone 2
Until 11th November :
- Clean data!
- Get the list of main food origin
- Get the list of main food categories imported
- Find ways to visualize obtained data on maps
- Plan the Machine Learning experiment *Do they really add something to the project ?*

Until 18th November :
- Follow analysis based on previous results : Focus analysis on the main imported categories: get statistics about carbon prints, distance covered ?
- See if it's interesting to study  correlation between packaging and distance 
- Decide how to perform Machine Learning experiment, what algorithms etc.

Until 25th November :
- Start and perform Machine Learning experiments

# Questions for TAs
- We are tackling a lot of different questions regarding food import. But not all of them are socially related (although the main subject is). Is this an issue ?  

