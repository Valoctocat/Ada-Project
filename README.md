# Think Global Buy Local!  

# Abstract
 "Think Global buy local" is a rising motto used to address sustainable food trade. Indeed, a lot of food is continuously imported to have constant stock independently of seasonal products. While it may be required to import some products, others could be replaced by local production. In Switzerland, 48% of consumed food is imported. The possibility to promote local agriculture was an issue at stake during the [last votations in Switzerland](https://www.bfs.admin.ch/bfs/fr/home/statistiques/politique/votations/annee-2018/2018-09-23/souverainete-alimentaire.html). Food keeps local land in production and local money in the community. Local production also reduces food safety risks and emission of greenhouse gas while building community relations. 
 
[Open Food Facts](https://world.openfoodfacts.org/) dataset gives some good insights regarding foods origins. It gathers information about food products around the world as the ingredients, origin of ingredients, nutrition factors, manufacturing places or countries where they are sold. The dataset is filled by volonteers.
As Open Food Facts project started in France, most of the dataset gathers information about French food products.

Our analysis aims at making people aware of ecological concerns of food importation in France and hopefully changing ways of comsuptions towards a more sustainable food trade.

# Research questions
- From which countries does French food products mainly come from ? 
- What are the main categories of food products being imported? Is this justified?
- What is the distance distribution for the main imported food categories ?
- Is trade with other European countries noticeable ? 
- For further investigations: What is the share of those product that are organic? Are there any correlation between packaging and distance travelled ?

# Dataset

[Open Food Facts](https://world.openfoodfacts.org/) will be the main dataset used for our analysis. It is a collaborative, free and open database of food products from around the world, completed by volunteers. It is available on the EPFL IC cluster or publicly [here](https://world.openfoodfacts.org/data). Origins of ingredients are labelled under the *origins* feature, which will be our starting point for this subject.

Open Food Facts gathers data for more than 600k products worldwide, but only 23k have labelled ingredient origins and come from France, which accounts for only 4% of the dataset.  However, this should still be enough for a first analysis of the product importations. Other ways to enrich the dataset could be interesting, but have not been found yet as this unique project started recently (in 2012) and is still growing. Therefore, any statistical conclusion from the analysis will need to be studied carefully due to the small size of the population sample.

As the Open Food Fact project started in France, the dataset gathers mostly food products sold in French stores. Therefore, imformation about the situation in other countries may be less representative of food importations. We will then focus on products sold in France. Moreover, French products have a good share of origin labelled product that we can work on.
However, one must keep in mind that the dataset is highly biaised. Most of food products have a French origin and not a foreign one. This is because brands use to promote local food making it visible on the packaging, while origin of other aliments may not be easy to find for the volunteers adding products to the dataset.

Data cleaning will be a big part of this analysis as the project is open-sourced : anyone can contribute and add their favorite (or not!) products. This leads to inconsistencies and unnormalized data. As a brief example some origins are labelled with a '?', probably meaning that the origin is unknown.
Multiple languages are used to represent origin countries. To counter this issue, we are using a dataset by [mledoze](https://github.com/mledoze/countries) which gathers informations about translations of country names and location of the country center in geographical coordinates.

Dataset is at the time of the project only 1.6 GB, available in CSV format. It will be processed using the Apache Spark API to handle the distributed informations in the cluster. Analysis tasks will be performed locally for conveniency. However, any task demanding more computationnal power may be performed on the cluster.

# A list of internal milestones up until project milestone 2  

Up until 11th November :
- Clean the data - OK
- Get the list of main food origins - OK
- Get the list of main food categories imported - OK
- Find ways to visualize obtained data on maps - OK

Up until 18th November :
- Follow analysis based on previous results : Focus analysis on the main imported categories: get statistics about carbon prints, distance covered. Confront the data with what is necessary for the country.
-> Not enough data to consider carbon prints. We then used distance covered. 
- See if it is interesting to study correlation between packaging and distance
-> Remains to be done. We have enough data to do this analysis

Up until 25th November :
- Generate relevant visualizations for collected data - In Progress

# A list of internal milestones up until project milestone 3  

Up until December 2nd :
- Study correlation between packaging and distance
- Perform bootstrapping to get an interval of confidence for the share of the top exported categories for each country.
- Gather the interesting statistics to build the data story : 
   * Distance travelled for each Food category (median distance bootstrapped and Max Value)
   * Share of the top categories for each country (mean share bootsrapped)
- Document on Jekyll and D3

Up until December 9th :  
- Build the two interactive maps with D3 (more informations in the notebook)
- Set-up the Jekyll platform

Up until December 16th :
- Write the datastory in Jekyll
