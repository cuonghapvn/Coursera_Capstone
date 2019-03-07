# Living in Osaka, Japan
*Capstone project by Cuong Nguyen*

## Introduction
For the last few years I have been living in the city of Osaka,  one of Japan's most unsung cities, often overshadowed by its neighbor Kyoto and Tokyo. I like living here, and I'm living in a great neighbourhood. Unfortunately I cannot stay here forever: I'm renting a small house, and I have to think about a long-term plan.

So where in this city will I buy a new house?

**My requirement is quite simple:**

*1. I want to keep my lifestyle as before, it should be a neighbourhoods which are similar to my former one. (Tsurumi-ku)*

*2. I want my neighbourhood near Train Station*

*3. I want my neighbourhood has Vietnamese restaurants.*

To figure this out I want to compare the various neighbourhoods in Osaka to see how similar they are, and finally figure out if there is a neighbourhood similar to mine where I could also live. I will do this based on the different venues and ammenities available in the direct vicinity of the various neighbourhoods.

## Data
To know more about Osaka I need as much data as possible.
I will utilize neighbourhood’s information of Osaka, Foursquare information on venue categories, top tips, location data, ratings to tackle this task. 

Neighbourhood information can be accessed through: https://www.post.japanpost.jp/zipcode/dl/roman-zip.html

Neighbourhood's coordinates: http://nlftp.mlit.go.jp/isj/index.html; http://jusyo.jp/index.html

## Methodology

### Summary

First requirement is solved by applying K-means clustering to perform city segmentation. With the neighbourhoods being clustered into clusters, this task becomes finding the neighbourhoods within the same cluster as 'Imazuminami'.

The Second and Third requirement can be solved by providing venue and ratings information from Foursquare API. The neighbourhoods with high ratings of Train Station and Vietnamese restaurants will become our target neighbourhoods.

### Procedures

I. In order to get an accurate city segmentation, the whole city of Osaka are our population. 489 neighbourhoods in total.
![2019-03-07-16_19_26-Report---IBM-Watson.png](https://i.imgur.com/bQkCMk7.png)

II. Access Foursquare location data of each neighbourhoods, using onehot technique to get top 10 venues of each neighbourhood.

III. Apply Kmeans Cluster to segment all 489 neighbourhoods into 8 clusters.
![2019-03-07-16_38_25-Report---IBM-Watson.png](https://i.imgur.com/HsPr1ge.png)

IV. The ‘Imazuminami’ belongs to cluster 2, the other cluster 2 neighbourhoods: 
![2019-03-07-16_17_06.png](https://i.imgur.com/fKGkYEP.png)

V: Filter the data frame by searching for Train Station and Vietnamese Restaurants, turning out only 2 of all neighbourhoods has Train Station being one of their top venues. Narrow down our target neighbourhoods to these two neighbourhoods.
![2019-03-07-16_38_25-Report---IBM-Watson.png](https://i.imgur.com/JE1LesH.png)

VI: Utilize Foursquare to find more around each neighbourhood. 

•	OSAKA SHI NISHINARI KU TENGACHAYAHIGASHI: has 2 train stations but rating is not good
![2019-03-07-16_38_25-Report---IBM-Watson.png](https://i.imgur.com/sevWgq1.png)


•	OSAKA SHI SUMINOE KU IZUMI: also has 3 train stations with better rating
![2019-03-07-16_38_25-Report---IBM-Watson.png](https://i.imgur.com/pZGGIir.png)


VII: Explore the Vietnamese restaurants around the two neighbourhoods. It turns out they have the same Vietnamese Restaurants around the two neighbourhood, with an average rating of 7.9.
![2019-03-07-16_38_25-Report---IBM-Watson.png](https://i.imgur.com/kgNoqai.png)


## Results

By exploring the requirements of Train Station and Vietnamese Restaurants, the two neighbourhoods have the same Train Station and Vietnamese Restaurants selection. They are fit all the requirements.

## Discussion

These two neighbourhoods are so alike, let’s see the location of them. 
![2019-03-07-16_36_21-Report---IBM-Watson.png](https://i.imgur.com/sSEdUa9.jpg)

## Conclusion
This result has limitations. The venues used in the project are from the top 10 venues of each neighbourhood, which might neglect neighbourhoods with more venues but less frequency of Train Station and Vietnamese Restaurants. 

Secondly, we use 10km as our parameter of searching venues. This can be wrong if there’s no public transition to those venues.

In conclusion, “OSAKA SHI NISHINARI KU TENGACHAYAHIGASHI”, “OSAKA SHI SUMINOE KU IZUMI” meets the requirement but better choices may exist.


