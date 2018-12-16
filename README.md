# Think Global Buy Local!  

## Abstract
"Think Global buy local" is a rising motto used to address sustainable food trade. Indeed, a lot of food is continuously imported throughout the year. Although seasonal products are highly produced during their respective month, they still constitute a non-negligeable share of the imported products. 
Buying local food keeps land in production and promotes local economic development by creating jobs and increasing trade. Local production also reduces food safety risks and raises transparency about the food that we buy.  In addition, avoiding long transportation by plane or by boat reduces greenhouse gas emission. . 
Our analysis is mostly based on informations regarding food import registered at France frontiers, resumed in a dataset from the [French government website]. Associated with other indications about the time of the year in which a product is in season and food production in France, this information gives us good insight to evaluate whether the importation of such products is really necessary.
This datastory is about analysing what are the dynamics of french seasonal food importations and hopefully will help change ways of consumptions towards a more sustainable food trade.

## Research questions
- From which countries does French food products mainly come from ?
- What are the main categories of food products being imported? 
- Are we importing products during the season in which they could be produced in France? Is this importation justified? 
- What is the distance distribution for the main imported food categories during the year?
- Is the food imported in France really for humans? 
- When is the right time to buy specific products? 

## Data
To perform our analysis, we used multiple datasets concerning importation and production In France. As indicated before, our main dataset concerning  importation in France comes from the [french government website](https://www.data.gouv.fr/en/datasets/statistiques-nationales-du-commerce-exterieur/#_). It gathers information about all the products that passed France customs each month in 2016.  For all the entries in the French territory, the mass (in kg)  and the origin of the product was registered. In this table, product categories are specified by their ‘CPF6’ code: An additional file, also found on the French government website, allows the association of these CPF6 code with the names of the products. 

The dataset, available in a csv format, is 73 MB, and represents  a total of 16M  product entries. However, the document contains information about all types of products, and not only food products. Food products represent 43221 entries. Our dataset contains very few missing values: they account for less than 10-4 of the values. 

Information about France food production in 2016 comes from the [FAO website](http://www.fao.org/faostat/fr/#data/QC). This dataset is a list of the annual mass produced in France for every food categories. This dataset, also a csv file,  is 6,6 MB and more than 300 different food categories are registered. Once again, missing values are rare and accounts for 2% of the dataset. 

We also needed information regarding the months in which a product is seasonal in France: These informations were obtained by web-scraping  of the following website: Greenpeace.fr[https://www.greenpeace.fr/guetteur/calendrier]. This is a simple association of food categories with the months in which they can be produced in France. 

A major part of our work was to match the products names together in  these different dataframes, in order to merge them. This was achieved by several standardization functions. Once merged, the combination of these file allowed us to have a good insight in French importation. For further analysis, we chose to study only products that can be produced in France. “Exotic” products like bananas or coconut are not taken in account. We assumed that these products are constantly imported all year, and the justification of this importation does not change according to the season in France, as they can never be produced in France. In addition, products like meats are not coherent with the concept of ‘seasonal’ products, and are therefore not considered. Finally, our analysis is based on 16165 entries of the importation dataset. 

## A list of internal milestones up until project milestone 3
After milestone 2, we realized that our previous dataset (Open Food Facts) was highly biased for the informations that we needed and we decided to restart our project on the current dataset. All the previously planned milestones had to be adapted to our new dataset, and all the phases of data cleaning and data description had to be re-done. 

Here is a list of what has been done since milestone 2: 
### 1/ General description and pre-process of datasets
- Web-scraping - Valentin Gabeff
- Analysis of dataset size and missing values - Valentin Gabeff
- Data cleaning 
- Standardization of our datasets in order to optimize their merging - Maxine Leonardi

### 2/ General Statistics / Plots for Datastory
- Main imported food categories globally and by month  
- Analysis of prevalence of imported cereals - Clara Nguyen
- Comparison of production and importation in France 
- Main importer countries in France globally and by month 
- Detailed analysis of particular countries (main importer or furthest origin) - Clara Nguyen
- Analysis of distribution of the distance traveled by the imported products. 
- Distance traveled by imported product in function of their importation month (bootstrapping,  boxplots) , and correlation of distance with how far the importation month is from the months in which the imported product is in season. - Maxine Leonardi
- Computation of Index of how ‘good’ or ‘bad’ the importation is based on mass and distance traveled by the imported product, and analysis of best and worst products - Valentin Gabeff

For all these tasks, we provided visualization of results using either pandas and matplotlib functions or plotly. 

### 3/ Tools:
All the tools require the previous creation of multiple dataframes and the computation of a lot of parameters, that are detailed in the notebook. 
- Tool 1:  Visualization of main importers and main food categories for each country on an interactive globe using Jekyll and D3. 
- Tool 2: For every food category: 
* Visualization of a boxplot of distances traveled by the product
* A table gathering information about when the product is seasonal in France, when it’s significantly more  imported, and with an index that indicates for each month whether buying this product in France is “good” or “bad”, considering the distance travelled and the mass imported. 
* A visualization of the mass imported each month, associated with the months in which they are seasonal. 

### 4/ Final layout of notebook and datastory: 
- Notebook layout and annotation 
- Global set up and layout of the datastory - Valentin Gabeff
- Writing of the datastory

### A list of internal milestones up until project milestone 4
For the presentation we have to:
- Create a poster to present
- Find ways to interactively show the audience how our tools work
- Decide and prepare what is going to be said
