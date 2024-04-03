# AirBnB MongoDB Analysis

## Dataset Origin

This dataset is grabbing from [AirBnB listings data website](http://insideairbnb.com/get-the-data.html). It shows lots of detailed informations about the airbnb around the world. I choose to focus on analyzing the airbnb in Denver, Colorado, United States. The [Raw Dataset](data/listings.csv) we grabbed from the website is in csv format.

## Raw Data Table (First 20 rows)
  
| id  | listing_url | scrape_id | last_scraped | source | name | description | neighborhood_overview | picture_url | host_id | host_url | host_name | host_since | host_location | host_about | host\_response\_time | host\_response\_rate | host\_acceptance\_rate | host\_is\_superhost | host\_thumbnail\_url | host\_picture\_url | host_neighbourhood | host\_listings\_count | host\_total\_listings_count | host_verifications | host\_has\_profile_pic | host\_identity\_verified | neighbourhood | neighbourhood_cleansed | neighbourhood\_group\_cleansed | latitude | longitude | property_type | room_type | accommodates | bathrooms | bathrooms_text | bedrooms | beds | amenities | price | minimum_nights | maximum_nights | minimum\_minimum\_nights | maximum\_minimum\_nights | minimum\_maximum\_nights | maximum\_maximum\_nights | minimum\_nights\_avg_ntm | maximum\_nights\_avg_ntm | calendar_updated | has_availability | availability_30 | availability_60 | availability_90 | availability_365 | calendar\_last\_scraped | number\_of\_reviews | number\_of\_reviews_ltm | number\_of\_reviews_l30d | first_review | last_review | review\_scores\_rating | review\_scores\_accuracy | review\_scores\_cleanliness | review\_scores\_checkin | review\_scores\_communication | review\_scores\_location | review\_scores\_value | license | instant_bookable | calculated\_host\_listings_count | calculated\_host\_listings\_count\_entire_homes | calculated\_host\_listings\_count\_private_rooms | calculated\_host\_listings\_count\_shared_rooms | reviews\_per\_month |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 607435380788232654 | https://www.airbnb.com/rooms/607435380788232654 | 20231229025659 | 2023-12-29 | city scrape | Home in Denver · 1 bedroom · 1 bed · 1 shared bath |     |     | https://a0.muscache.com/pictures/miso/Hosting-607435380788232654/original/18997281-dc60-4432-bac1-3948e6f6174c.jpeg | 430149575 | https://www.airbnb.com/users/show/430149575 | Roye | 2021-11-02 |     |     | within an hour | 100% | 75% | f   | https://a0.muscache.com/im/pictures/user/c8b951f8-c431-4126-a649-11dab14bfe43.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/c8b951f8-c431-4126-a649-11dab14bfe43.jpg?aki\_policy=profile\_x_medium | Congress Park | 8   | 23  | \['email', 'phone'\] | t   | t   |     | North Park Hill |     | 39.76039 | -104.92968 | Private room in home | Private room | 1   |     | 1 shared bath |     | 1   | \[\] | $35.00 | 30  | 365 | 30  | 30  | 365 | 365 | 30.0 | 365.0 |     | t   | 30  | 60  | 90  | 365 | 2023-12-29 | 2   | 0   | 0   | 2022-07-01 | 2022-08-01 | 3.0 | 2.5 | 2.5 | 3.0 | 3.5 | 4.0 | 3.0 |     | f   | 6   | 2   | 4   | 0   | 0.11 |
| 545714833502855511 | https://www.airbnb.com/rooms/545714833502855511 | 20231229025659 | 2023-12-29 | city scrape | Rental unit in Denver · 2 bedrooms · 3 beds · 2 baths |     |     | https://a0.muscache.com/pictures/miso/Hosting-545714833502855511/original/72050442-7cc5-4efe-95c3-a1ccb10e485d.jpeg | 169214047 | https://www.airbnb.com/users/show/169214047 | Jerrod | 2018-01-22 | Chicago, IL |     | N/A | N/A | 0%  | f   | https://a0.muscache.com/im/pictures/user/b7709ffb-1e7a-4382-acf4-e91c339d0c37.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/b7709ffb-1e7a-4382-acf4-e91c339d0c37.jpg?aki\_policy=profile\_x_medium | East | 1   | 2   | \['email', 'phone'\] | t   | t   |     | Hale |     | 39.72785 | -104.93783 | Entire rental unit | Entire home/apt | 6   |     | 2 baths |     | 3   | \[\] | $149.00 | 30  | 365 | 30  | 30  | 365 | 365 | 30.0 | 365.0 |     | t   | 29  | 59  | 89  | 364 | 2023-12-29 | 0   | 0   | 0   |     |     |     |     |     |     |     |     |     |     | f   | 1   | 1   | 0   | 0   |     |
| 43920210 | https://www.airbnb.com/rooms/43920210 | 20231229025659 | 2023-12-29 | previous scrape | Guest suite in Denver · ★4.38 · 3 bedrooms · 4 beds · 2 baths |     |     | https://a0.muscache.com/pictures/2c67d672-58b4-4453-8252-7c96e3c6b1d7.jpg | 3484713 | https://www.airbnb.com/users/show/3484713 | Vu  | 2012-09-05 | United States | I work Denver, CO, San Diego and Sacramento, CA. I proudly served in the United States Marine Corps for almost 10 years. My ultimate passion is leadership because everyone has the ability to Influence people in a positive way! I’m a true believer of “How you do something is how you do Everything!” and the best way to judge anything is from consistency and proven results. Overall... “BE A GOOD PERSON” | within a day | 67% | 91% | f   | https://a0.muscache.com/im/users/3484713/profile\_pic/1346892319/original.jpg?aki\_policy=profile_small | https://a0.muscache.com/im/users/3484713/profile\_pic/1346892319/original.jpg?aki\_policy=profile\_x\_medium | Anatolia Village | 11  | 11  | \['email', 'phone', 'work_email'\] | t   | t   |     | Sloan Lake |     | 39.75398 | -105.03047 | Entire guest suite | Entire home/apt | 10  |     | 2 baths |     | 4   | \[\] |     | 29  | 1125 | 29  | 29  | 1125 | 1125 | 29.0 | 1125.0 |     |     | 0   | 0   | 0   | 0   | 2023-12-29 | 13  | 0   | 0   | 2020-07-13 | 2021-04-30 | 4.38 | 4.31 | 4.54 | 4.62 | 4.62 | 4.38 | 4.38 | 2021-BFN-0000590 | f   | 2   | 2   | 0   | 0   | 0.31 |
| 52429527 | https://www.airbnb.com/rooms/52429527 | 20231229025659 | 2023-12-29 | previous scrape | Townhouse in Denver · ★4.78 · 3 bedrooms · 4 beds · 2.5 baths |     |     | https://a0.muscache.com/pictures/prohost-api/Hosting-52429527/original/783259fd-90dc-459c-906e-cf7fd8b02a56.jpeg | 107279139 | https://www.airbnb.com/users/show/107279139 | Kyle And Kimberly | 2016-12-14 | Denver, CO | Enjoy an unparalleled experience while visiting Colorado. Our Guest Experience Team is here for you 24/7 during your stay. Feel free to ask us where the local hot spots are for restaurants, bars, music venues, and even hiking trails. We are local ambassadors for the neighborhood & Colorado. | within an hour | 100% | 100% | t   | https://a0.muscache.com/im/pictures/user/24a07b59-0721-4996-8424-9fa45fc9308a.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/24a07b59-0721-4996-8424-9fa45fc9308a.jpg?aki\_policy=profile\_x_medium | South | 58  | 70  | \['email', 'phone'\] | t   | t   |     | Five Points |     | 39.75852 | -104.98846 | Entire townhouse | Entire home/apt | 8   |     | 2.5 baths |     | 4   | \[\] | $190.00 | 1   | 365 | 2   | 4   | 365 | 365 | 2.9 | 365.0 |     | t   | 4   | 21  | 51  | 231 | 2023-12-29 | 68  | 27  | 0   | 2021-10-11 | 2023-11-20 | 4.78 | 4.88 | 4.62 | 4.78 | 4.78 | 4.93 | 4.59 | 2021-BFN-0005677 | f   | 20  | 20  | 0   | 0   | 2.52 |
| 632494576047532593 | https://www.airbnb.com/rooms/632494576047532593 | 20231229025659 | 2023-12-29 | previous scrape | Townhouse in Denver · ★New · 2 bedrooms · 2 beds · 2.5 baths |     |     | https://a0.muscache.com/pictures/miso/Hosting-632494576047532593/original/5fb15a86-606c-42bb-852e-e9eb9a14cc72.jpeg | 416194740 | https://www.airbnb.com/users/show/416194740 | Clayton | 2021-07-31 | Colorado, United States | I was born and raised in beautiful Boulder, Colorado. After graduating from the University of Arizona in Tucson I moved to Denver where I currently split my time between Summit County and the city of Denver. When I'm not working as an engineer I'm enjoying the mountains skiing in the winter and hiking in the summer. | within an hour | 100% | 100% | t   | https://a0.muscache.com/im/pictures/user/1559f942-2e95-4ea0-b3fd-fde29763c271.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/1559f942-2e95-4ea0-b3fd-fde29763c271.jpg?aki\_policy=profile\_x_medium | West | 2   | 2   | \['email', 'phone'\] | t   | t   |     | West Colfax |     | 39.736019 | -105.05072 | Entire townhouse | Entire home/apt | 5   |     | 2.5 baths |     | 2   | \[\] | $87.00 | 29  | 365 | 29  | 29  | 365 | 365 | 29.0 | 365.0 |     | t   | 0   | 0   | 0   | 13  | 2023-12-29 | 0   | 0   | 0   |     |     |     |     |     |     |     |     |     |     | t   | 1   | 1   | 0   | 0   |     |
| 687768125161080215 | https://www.airbnb.com/rooms/687768125161080215 | 20231229025659 | 2023-12-29 | previous scrape | Home in Denver · ★5.0 · 2 bedrooms · 2 beds · 1 bath |     | Quite, tree-lined street with older brick homes and lively energy. | https://a0.muscache.com/pictures/miso/Hosting-687768125161080215/original/c3dc320b-d83d-4335-a31d-383cc05a08e4.jpeg | 133612752 | https://www.airbnb.com/users/show/133612752 | Ryan | 2017-06-05 | Denver, CO |     | N/A | N/A | 91% | f   | https://a0.muscache.com/im/pictures/user/77af985d-0225-46da-9f09-8125e990f039.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/77af985d-0225-46da-9f09-8125e990f039.jpg?aki\_policy=profile\_x_medium | Northwest | 1   | 1   | \['email', 'phone'\] | t   | f   | Denver, Colorado, United States | Sunnyside |     | 39.77143 | -105.02028 | Entire home | Entire home/apt | 3   |     | 1 bath |     | 2   | \[\] | $300.00 | 29  | 1125 | 29  | 29  | 1125 | 1125 | 29.0 | 1125.0 |     | t   | 0   | 0   | 27  | 27  | 2023-12-29 | 12  | 12  | 0   | 2022-12-31 | 2023-09-04 | 5.0 | 5.0 | 5.0 | 5.0 | 5.0 | 4.92 | 4.92 | 2022-BFN-0019698 | f   | 1   | 1   | 0   | 0   | 0.99 |
| 43316442 | https://www.airbnb.com/rooms/43316442 | 20231229025659 | 2023-12-29 | city scrape | Townhouse in Denver · ★4.96 · 3 bedrooms · 5 beds · 4 baths |     | Jefferson Park is centrally located to Downtown Denver but is a very quiet and safe feeling area. A really nice park is a 1 minute walk from our place. | https://a0.muscache.com/pictures/f2a3fb17-b931-4657-a857-b754b6e13df6.jpg | 299373263 | https://www.airbnb.com/users/show/299373263 | Dania | 2019-10-01 |     |     | within an hour | 100% | 95% | f   | https://a0.muscache.com/im/pictures/user/f2983010-c147-4f02-9558-b7719f39844c.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/f2983010-c147-4f02-9558-b7719f39844c.jpg?aki\_policy=profile\_x_medium | Jefferson Park | 2   | 2   | \['email', 'phone'\] | t   | t   | Denver, Colorado, United States | Jefferson Park |     | 39.74803 | -105.02243 | Entire townhouse | Entire home/apt | 8   |     | 4 baths |     | 5   | \[\] | $408.00 | 4   | 29  | 4   | 5   | 29  | 29  | 4.1 | 29.0 |     | t   | 20  | 47  | 74  | 238 | 2023-12-29 | 28  | 12  | 1   | 2020-08-02 | 2023-12-26 | 4.96 | 4.96 | 4.86 | 5.0 | 5.0 | 5.0 | 4.75 | 2019-BFN-0011462 | f   | 1   | 1   | 0   | 0   | 0.67 |
| 53892390 | https://www.airbnb.com/rooms/53892390 | 20231229025659 | 2023-12-29 | city scrape | Guesthouse in Denver · ★4.97 · 1 bedroom · 1 bed · 1 bath |     |     | https://a0.muscache.com/pictures/miso/Hosting-53892390/original/1e3db06b-2115-44f9-ad7b-225ff51e5277.jpeg | 436546995 | https://www.airbnb.com/users/show/436546995 | Conor | 2021-12-18 | Denver, CO |     | within an hour | 100% | 100% | t   | https://a0.muscache.com/im/pictures/user/d71e0bf6-4c7a-4521-bdd8-305564ef56c7.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/d71e0bf6-4c7a-4521-bdd8-305564ef56c7.jpg?aki\_policy=profile\_x_medium | Chaffee Park | 1   | 2   | \['email', 'phone'\] | t   | t   |     | Chaffee Park |     | 39.79137 | -105.02354 | Entire guesthouse | Entire home/apt | 2   |     | 1 bath |     | 1   | \[\] | $121.00 | 2   | 180 | 2   | 2   | 1125 | 1125 | 2.0 | 1125.0 |     | t   | 6   | 36  | 66  | 246 | 2023-12-29 | 59  | 20  | 0   | 2022-02-20 | 2023-11-27 | 4.97 | 5.0 | 4.97 | 4.98 | 5.0 | 4.88 | 4.93 | 2021-BFN-0010714 | f   | 1   | 1   | 0   | 0   | 2.61 |
| 842293747258462739 | https://www.airbnb.com/rooms/842293747258462739 | 20231229025659 | 2023-12-29 | city scrape | Home in Denver · ★4.88 · 3 bedrooms · 6 beds · 3.5 baths |     | River North, commonly known as RiNo, is a vibrant and trendy neighborhood located just north of downtown Denver, Colorado. Known for its unique blend of art, culture, and urban living, RiNo has become a popular destination for residents and visitors alike.  <br>  <br>One of the defining features of RiNo is its thriving arts scene. The neighborhood is home to numerous art galleries, studios, and street murals, making it a haven for artists and art lovers. You can stroll down the streets of RiNo and find colorful murals adorning the sides of buildings, adding a vibrant and creative touch to the neighborhood's aesthetic.  <br>  <br>RiNo also boasts an eclectic mix of shops, boutiques, and restaurants, offering a diverse range of culinary experiences. From trendy breweries and cocktail bars to innovative restaurants and food halls, there's something for everyone's palate in RiNo. The neighborhood is also known for its lively nightlife scene, with various entertainment options, including li | https://a0.muscache.com/pictures/prohost-api/Hosting-842293747258462739/original/ef3a8205-7859-482e-ae3e-1378d0e3dfdb.png | 456393682 | https://www.airbnb.com/users/show/456393682 | Jasmine | 2022-04-27 | Denver, CO |     | within an hour | 100% | 98% | t   | https://a0.muscache.com/im/pictures/user/b0fe8031-5ef4-4d27-bd0d-6a39db3e29e5.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/b0fe8031-5ef4-4d27-bd0d-6a39db3e29e5.jpg?aki\_policy=profile\_x_medium | Five Points | 1   | 6   | \['email', 'phone'\] | t   | t   | Denver, Colorado, United States | Five Points |     | 39.756066 | -104.982419 | Entire home | Entire home/apt | 9   |     | 3.5 baths |     | 6   | \[\] | $561.00 | 1   | 30  | 1   | 2   | 1125 | 1125 | 1.3 | 1125.0 |     | t   | 21  | 35  | 60  | 333 | 2023-12-29 | 16  | 16  | 0   | 2023-05-20 | 2023-10-22 | 4.88 | 4.81 | 4.88 | 5.0 | 4.81 | 4.94 | 4.56 | 2023-BFN-0015672 | t   | 1   | 1   | 0   | 0   | 2.14 |
| 717942620254550220 | https://www.airbnb.com/rooms/717942620254550220 | 20231229025659 | 2023-12-29 | city scrape | Home in Denver · 2 bedrooms · 2 beds · 2 baths |     |     | https://a0.muscache.com/pictures/miso/Hosting-717942620254550220/original/7773a0e5-3988-4d4b-8cea-c212c3f98ee4.jpeg | 110328442 | https://www.airbnb.com/users/show/110328442 | David | 2017-01-07 | Denver, CO | I love to travel, the outdoors, and hanging out with my dog. | N/A | N/A | N/A | f   | https://a0.muscache.com/im/pictures/user/b376138f-4006-40f2-bd34-171cc1767ae3.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/b376138f-4006-40f2-bd34-171cc1767ae3.jpg?aki\_policy=profile\_x_medium | Northwest | 1   | 1   | \['email', 'phone', 'work_email'\] | t   | t   |     | Sunnyside |     | 39.77790239999999 | -105.0237574 | Entire home | Entire home/apt | 2   |     | 2 baths |     | 2   | \[\] | $128.00 | 30  | 45  | 30  | 30  | 1125 | 1125 | 30.0 | 1125.0 |     | t   | 30  | 60  | 90  | 365 | 2023-12-29 | 0   | 0   | 0   |     |     |     |     |     |     |     |     |     |     | t   | 1   | 1   | 0   | 0   |     |
| 991710271661703752 | https://www.airbnb.com/rooms/991710271661703752 | 20231229025659 | 2023-12-29 | city scrape | Rental unit in Denver · Studio · 1 bed · 1 bath |     |     | https://a0.muscache.com/pictures/prohost-api/Hosting-991710271661703752/original/bc631020-9e70-410f-9fa7-33a0969f4f32.jpeg | 263502162 | https://www.airbnb.com/users/show/263502162 | Landing | 2019-05-22 | San Francisco, CA | Landing provides tens of thousands of furnished apartments in over 200 cities throughout the US. Every furnished Landing is complete with custom furniture and every homeware essential. Landing apartments are professionally managed and include 24/7 customer support. | within an hour | 91% | 98% | f   | https://a0.muscache.com/im/pictures/user/1567535f-99cd-4c14-95b3-2bb134463ebf.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/1567535f-99cd-4c14-95b3-2bb134463ebf.jpg?aki\_policy=profile\_x_medium | Five Points South | 2561 | 3142 | \['phone'\] | t   | t   |     | West Colfax |     | 39.73960417213702 | -105.04635025178685 | Entire rental unit | Entire home/apt | 2   |     | 1 bath |     | 1   | \[\] | $93.00 | 30  | 180 | 30  | 30  | 180 | 180 | 30.0 | 180.0 |     | t   | 30  | 60  | 90  | 365 | 2023-12-29 | 0   | 0   | 0   |     |     |     |     |     |     |     |     |     |     | t   | 55  | 55  | 0   | 0   |     |
| 935117721555945908 | https://www.airbnb.com/rooms/935117721555945908 | 20231229025659 | 2023-12-29 | city scrape | Home in Denver · ★4.83 · 2 bedrooms · 2 beds · 2 baths |     |     | https://a0.muscache.com/pictures/miso/Hosting-935117721555945908/original/49a0ee87-ce52-4285-b454-dc55c91bf92b.jpeg | 71753330 | https://www.airbnb.com/users/show/71753330 | Luke | 2016-05-13 | Denver, CO | Southern gent who enjoys traveling and experiencing life. | within an hour | 100% | 100% | f   | https://a0.muscache.com/im/pictures/user/User-71753330/original/7d4c16d6-c497-4673-94fa-9f83774aa80a.jpeg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/User-71753330/original/7d4c16d6-c497-4673-94fa-9f83774aa80a.jpeg?aki\_policy=profile\_x_medium | Northwest | 1   | 1   | \['email', 'phone'\] | t   | t   |     | West Highland |     | 39.76547288243867 | -105.04667108515007 | Entire home | Entire home/apt | 5   |     | 2 baths |     | 2   | \[\] | $319.00 | 2   | 90  | 1   | 2   | 90  | 90  | 1.3 | 90.0 |     | t   | 24  | 54  | 84  | 359 | 2023-12-29 | 12  | 12  | 2   | 2023-09-05 | 2023-12-28 | 4.83 | 4.83 | 4.83 | 4.92 | 5.0 | 5.0 | 4.75 | 2023-BFN-0000532 | t   | 1   | 1   | 0   | 0   | 3.10 |
| 861888024999339284 | https://www.airbnb.com/rooms/861888024999339284 | 20231229025659 | 2023-12-29 | city scrape | Rental unit in Denver · ★4.60 · 1 bedroom · 1 bed · 1 bath |     |     | https://a0.muscache.com/pictures/miso/Hosting-861888024999339284/original/bcf51455-bd99-4765-8e7b-bbfe811842e3.jpeg | 302323071 | https://www.airbnb.com/users/show/302323071 | Quincy | 2019-10-14 |     |     | within an hour | 100% | 100% | f   | https://a0.muscache.com/im/pictures/user/0499d55f-0a7a-4b05-a807-cfabc7c21d8a.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/0499d55f-0a7a-4b05-a807-cfabc7c21d8a.jpg?aki\_policy=profile\_x_medium | Hotel District | 2   | 2   | \['email', 'phone'\] | t   | t   |     | Union Station |     | 39.7550852 | -105.0011372 | Entire rental unit | Entire home/apt | 2   |     | 1 bath |     | 1   | \[\] | $165.00 | 2   | 365 | 2   | 2   | 1125 | 1125 | 2.0 | 1125.0 |     | t   | 0   | 0   | 0   | 0   | 2023-12-29 | 9   | 9   | 0   | 2023-08-27 | 2023-11-12 | 4.6 | 4.7 | 4.9 | 4.5 | 4.9 | 5.0 | 4.2 | 2023-BFN-0012848 | f   | 1   | 1   | 0   | 0   | 2.16 |
| 53485317 | https://www.airbnb.com/rooms/53485317 | 20231229025659 | 2023-12-29 | city scrape | Home in Denver · ★4.80 · 1 bedroom · 1 bed · 1 private bath |     |     | https://a0.muscache.com/pictures/de729207-4713-4097-b32a-1c56b43ed07c.jpg | 425969928 | https://www.airbnb.com/users/show/425969928 | Henry | 2021-10-04 |     |     | within an hour | 100% | 77% | f   | https://a0.muscache.com/im/pictures/user/9c3b243a-635e-4f6e-a97a-a609673450f4.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/9c3b243a-635e-4f6e-a97a-a609673450f4.jpg?aki\_policy=profile\_x_medium | West | 6   | 10  | \['email', 'phone'\] | t   | t   |     | West Colfax |     | 39.73978 | -105.03364 | Private room in home | Private room | 1   |     | 1 private bath |     | 1   | \[\] | $33.00 | 29  | 365 | 29  | 29  | 365 | 365 | 29.0 | 365.0 |     | t   | 10  | 40  | 70  | 345 | 2023-12-29 | 5   | 1   | 0   | 2022-01-15 | 2023-04-01 | 4.8 | 4.6 | 4.6 | 5.0 | 5.0 | 5.0 | 4.6 |     | f   | 4   | 0   | 4   | 0   | 0.21 |
| 787141047994076229 | https://www.airbnb.com/rooms/787141047994076229 | 20231229025659 | 2023-12-29 | city scrape | Home in Denver · ★4.89 · 2 bedrooms · 2 beds · 2 baths |     |     | https://a0.muscache.com/pictures/miso/Hosting-787141047994076229/original/0475fa0b-cedc-478c-808d-a5df240025c7.jpeg | 34955862 | https://www.airbnb.com/users/show/34955862 | Scott | 2015-06-03 | Denver, CO | Scott Hemerda is a founding principal and owner of Vacation Rental Collective (VRC), offering premier vacation rentals along the Front Range, including the greater Denver metropolitan area. As a native Coloradoan, Scott spent his childhood in Littleton, studied at Colorado State University in Fort Collins, and raised his family in Parker. His daily commute to downtown Denver led to a love of the city in addition to his established love of the surrounding suburbs and mountains. Scott worked in financial services as the Director of Institutional Relationships for 18 years at TIAA-CREF, where he managed relationships worth 20 billion in assets. In addition to leading the top performing relationship management team, Scott supported and retained clients through challenging service model and system changes all evidence of his superior relationship management skills. Scott married his high school sweetheart and they have three children. A lover of sports, he instilled the values of collaboration, teamwork, and good sportsmanship as a role model participating in softball and basketball and then as a coach for all of his children in their numerous activities. Scott grew up skiing and now enjoys hiking and exploring the mountains with his wife. Business trips, family vacations, and romantic getaways have cultivated his love and expertise on the needs of vacationers. | within an hour | 100% | 99% | f   | https://a0.muscache.com/im/pictures/user/624e0095-07d8-4aa3-a317-18e1de36d9c7.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/624e0095-07d8-4aa3-a317-18e1de36d9c7.jpg?aki\_policy=profile\_x_medium | LoDo | 111 | 128 | \['email', 'phone'\] | t   | t   |     | Cole |     | 39.76270271567261 | -104.96561272589412 | Entire home | Entire home/apt | 4   |     | 2 baths |     | 2   | \[\] | $295.00 | 2   | 365 | 2   | 2   | 365 | 365 | 2.0 | 365.0 |     | t   | 23  | 53  | 83  | 358 | 2023-12-29 | 28  | 28  | 0   | 2023-01-15 | 2023-09-23 | 4.89 | 4.96 | 4.96 | 4.93 | 4.93 | 4.89 | 4.86 | 2022-BFN-0013398 | t   | 43  | 43  | 0   | 0   | 2.41 |
| 1037391989033116078 | https://www.airbnb.com/rooms/1037391989033116078 | 20231229025659 | 2023-12-29 | city scrape | Home in Denver · ★New · 1 bedroom · 1 bed · 1 bath |     |     | https://a0.muscache.com/pictures/miso/Hosting-1037391989033116078/original/eb6c550c-e30f-44b7-a55b-78f92967e03a.jpeg | 185063162 | https://www.airbnb.com/users/show/185063162 | Opuluxe | 2018-04-18 |     | Welcome to Opuluxe! We're a short term rental management company and we specialize in offering top-notch short-term rental experiences for travelers. We couldn't do it without the help of our amazing team of property managers, who share our dedication to guest satisfaction. Whether you're here for business or leisure, book your stay today and let us make your travel experience truly opulent. We look forward to hosting you! | within an hour | 90% | 96% | f   | https://a0.muscache.com/im/pictures/user/User-185063162/original/ec7a1f01-304a-407c-9f58-d71b5ed11afd.png?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/User-185063162/original/ec7a1f01-304a-407c-9f58-d71b5ed11afd.png?aki\_policy=profile\_x_medium | Woodland Brooke | 64  | 218 | \['email', 'phone'\] | t   | t   |     | City Park West |     | 39.75037 | -104.96341 | Entire home | Entire home/apt | 2   |     | 1 bath |     | 1   | \[\] | $60.00 | 30  | 365 | 30  | 30  | 365 | 365 | 30.0 | 365.0 |     | t   | 30  | 60  | 90  | 259 | 2023-12-29 | 0   | 0   | 0   |     |     |     |     |     |     |     |     |     |     | f   | 4   | 2   | 2   | 0   |     |
| 968038142577757342 | https://www.airbnb.com/rooms/968038142577757342 | 20231229025659 | 2023-12-29 | city scrape | Condo in Denver · ★5.0 · 1 bedroom · 1 bed · 1 bath |     |     | https://a0.muscache.com/pictures/prohost-api/Hosting-968038142577757342/original/d7bdc8e9-e387-422f-ab94-2ff2fa43bec4.jpeg | 142202943 | https://www.airbnb.com/users/show/142202943 | JZ Vacation Rentals | 2017-07-24 | St. Louis, MO | Staying with JZ Vacation Rentals, you will have the assurance of vacationing not only in a totally equipped and luxury home but also a home with loads of unique character to personalize your stay and make it memorable. The JZ Family team of Interior Designers have a 150 point Inspection process for every property within the JZ Brand to ensure quality control and maintain the best uniform elevated experience. Your vacation time & Experience is so valuable! Therefore, our Quality control team professionally inspects every property to maintain the best experience that you deserve across our entire inventory of properties within our Brand. All our property includes but is not limited to memory foam mattresses, Luxury sheets with mattress protectors, Duvets, Ceiling fans, smart TV’s, and designer finishes throughout every location with the addition of the JZ perks to make your stay perfect. | within an hour | 100% | 92% | f   | https://a0.muscache.com/im/pictures/user/050c0c7a-ebcc-42dc-92b9-9b35856352a2.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/050c0c7a-ebcc-42dc-92b9-9b35856352a2.jpg?aki\_policy=profile\_x_medium | Soulard | 50  | 50  | \['email', 'phone', 'work_email'\] | t   | t   |     | Highland |     | 39.7593461250016 | -105.01492148292007 | Entire condo | Entire home/apt | 2   |     | 1 bath |     | 1   | \[\] | $141.00 | 1   | 731 | 1   | 3   | 1125 | 1125 | 1.4 | 1125.0 |     | t   | 9   | 39  | 69  | 344 | 2023-12-29 | 7   | 7   | 0   | 2023-09-18 | 2023-11-18 | 5.0 | 5.0 | 5.0 | 5.0 | 5.0 | 5.0 | 5.0 | 2021-BFN-0001467 | f   | 26  | 26  | 0   | 0   | 2.04 |
| 867558537288806613 | https://www.airbnb.com/rooms/867558537288806613 | 20231229025659 | 2023-12-29 | city scrape | Home in Denver · ★4.80 · 3 bedrooms · 3 beds · 2.5 baths |     | The Urbanist Magazine described the Baker neighborhood as Denver's hippest new neighborhood. You are one block away from South Broadway and less than a mile from all that Sante Fe Art district has to offer. Within a couple of blocks there are shops, restaurants, bars, dispensaries, breweries, distilleries, coffee shops, pot shops, yoga, bowling, movies, and light grocery shopping. | https://a0.muscache.com/pictures/miso/Hosting-867558537288806613/original/be88edca-7679-4508-8213-ed1084df0b5a.jpeg | 2619306 | https://www.airbnb.com/users/show/2619306 | Zack | 2012-06-12 | Denver, CO | Laid back EX-Asian Equity trader and now full-time Airbnb Property Manager. I used to live/work in Bangkok, Thailand, and I absolutely love that part of the world. If you are looking for recommendations, please don't hesitate to ask! I'm a Colorado native, and I love showing people parts of Denver & Colorado that aren't in travel guides. | within an hour | 100% | 99% | t   | https://a0.muscache.com/im/pictures/user/40731907-3c33-4cf7-bc9b-3dcc67d3d63a.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/40731907-3c33-4cf7-bc9b-3dcc67d3d63a.jpg?aki\_policy=profile\_x_medium | Speer | 104 | 141 | \['email', 'phone'\] | t   | t   | Denver, Colorado, United States | Lincoln Park |     | 39.73136 | -104.99696 | Entire home | Entire home/apt | 6   |     | 2.5 baths |     | 3   | \[\] | $192.00 | 1   | 7   | 1   | 4   | 7   | 7   | 3.1 | 7.0 |     | t   | 24  | 54  | 84  | 86  | 2023-12-29 | 25  | 25  | 3   | 2023-05-02 | 2023-12-18 | 4.8 | 4.8 | 4.48 | 4.96 | 5.0 | 4.84 | 4.68 | 2022-BFN-0023538 | t   | 58  | 53  | 5   | 0   | 3.10 |
| 625484815499127868 | https://www.airbnb.com/rooms/625484815499127868 | 20231229025659 | 2023-12-29 | city scrape | Condo in Denver · 1 bedroom · 1 bed · 1.5 baths |     |     | https://a0.muscache.com/pictures/miso/Hosting-625484815499127868/original/7653abe5-7c03-4ca8-bfca-b6890c0514f7.jpeg | 277980890 | https://www.airbnb.com/users/show/277980890 | Kevin | 2019-07-21 | Denver, CO | I am the creator of Artificially Intelligent Matchmaker, the talking dating app that speaks to you for a week to get to know you then introduces you to people. I also created Talking App Kit which adds talking abilities to any iPhone app. Do you own an iPhone app? I can make it fly. This is me: (Website hidden by Airbnb) And me talking: (Website hidden by Airbnb) In first half of Life 2.0 on Netflix, here: (Website hidden by Airbnb) | N/A | N/A | N/A | f   | https://a0.muscache.com/im/pictures/user/7f2950d5-2dac-4bcb-9d90-e35070d597f3.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/7f2950d5-2dac-4bcb-9d90-e35070d597f3.jpg?aki\_policy=profile\_x_medium | North Capitol Hill | 1   | 1   | \['phone'\] | t   | t   |     | North Capitol Hill |     | 39.747002 | -104.981819 | Entire condo | Entire home/apt | 1   |     | 1.5 baths |     | 1   | \[\] | $90.00 | 29  | 365 | 29  | 29  | 365 | 365 | 29.0 | 365.0 |     | t   | 29  | 59  | 62  | 62  | 2023-12-29 | 0   | 0   | 0   |     |     |     |     |     |     |     |     |     |     | f   | 1   | 1   | 0   | 0   |     |
| 5536068 | https://www.airbnb.com/rooms/5536068 | 20231229025659 | 2023-12-29 | city scrape | Condo in Denver · ★5.0 · 1 bedroom · 1 bed · 1 bath |     | It's in the heart of downtown Denver close to the various city highlights. | https://a0.muscache.com/pictures/3e563ce7-7f0a-4224-a0f0-df71eb59846b.jpg | 28706795 | https://www.airbnb.com/users/show/28706795 | Bryan | 2015-03-03 | Denver, CO | Hi my name is Bryan Balducki and I am a Colorado Realtor, investor, and property manager. I am a native to Colorado and love it. Feel free to ask me any questions regarding activities in CO. My hobbies include snowboarding, reading, hiking, camping, traveling, weight lifting, and home improvement. I have been air bnbing since 2015 and I also manage rentals. I love airbnb because it allows me to meet and help different people. If you are interested in purchasing a home in Colorado, feel free to reach out as I would love to help. Thank you! | within an hour | 100% | 94% | f   | https://a0.muscache.com/im/pictures/user/31666577-01c7-4910-a0a1-e902959f1cb0.jpg?aki\_policy=profile\_small | https://a0.muscache.com/im/pictures/user/31666577-01c7-4910-a0a1-e902959f1cb0.jpg?aki\_policy=profile\_x_medium | Southeast | 2   | 8   | \['email', 'phone'\] | t   | t   | Denver, Colorado, United States | CBD |     | 39.74815 | -104.99489 | Entire condo | Entire home/apt | 2   |     | 1 bath |     | 1   | \[\] | $65.00 | 30  | 1125 | 30  | 30  | 1125 | 1125 | 30.0 | 1125.0 |     | t   | 11  | 11  | 19  | 72  | 2023-12-29 | 13  | 2   | 1   | 2015-03-18 | 2023-12-20 | 5.0 | 5.0 | 4.77 | 4.85 | 5.0 | 4.92 | 4.73 |     | f   | 2   | 2   | 0   | 0   | 0.12 |

## Data Scrubbing

Since the raw dataset has many columns that need to modify because of several reasons. In the next step we will scrub the orginal dataset to make sure the updated version is clearer, simplier, and easier to analysis. The [Cleaned Dataset](data/listings_clean.csv) has following modifications.

+ Delete the whole **description** column in the table using text editor since it is blank for all the rows inside the table so there is no meaning to include this column in the table.
+ Rename the column **host_listings_count** as **host_current_listings_count** using text editor to make the meaning of the column clearer and easier for reader to understand. shows its relationship with the latter coloumn **host_total_listings_count** more directly.
+ Delete the whole **neighbourhood** and **neighbourhood_group_cleansed** two columns in the table using text editor since the first one is always same "Denver" and the second one is blank for all the rows inside the table so there is no meaning to include these two columns in the table.
+ Delete the whole **bathrooms** column in the table using text editor since it is blank for all the rows inside the table so there is no meaning to include this column in the table, and rename the latter column **bathrooms_text** as **bathroom** to make the table more understandable.
+ Delete the whole **bedrooms** column in the table using text editor since it is blank for all the rows inside the table so there is no meaning to include this column in the table.
+ Delete the whole **amenities** column in the table using text editor since it is blank for all the rows inside the table so there is no meaning to include this column in the table.
+ For all the night related coloumn, only keep **minimium_nights** and **maxium_nights** two column and delete all other columns since most of these coumns has no use in later analyzing process. Therefore, to make the table clearer and easier to understand, we can just delete these columns.
+ Delete all the **availability** related columns in the table using text editor since they are irrevelant with later analysis.
+ Delete the whole **calendar_updated** column in the table using text editor since it is blank for all the rows inside the table so there is no meaning to include this column in the table.
+ Delete the whole **latitude** and **longtitude** two columns in the table using text editor since these two rows won't be considered in latter analysis process. Also, there two columns don't contain important informations reader required.
+ Delete all four coloumns that related to the **calculated_host_listings_count** in the table using text editor since these four rows won't be considered in latter analysis process. Also, there four columns don't contain important informations reader required.
+ Delete the whole **first review** and **last review** two columns in the table using text editor since these two rows won't be considered in latter analysis process. Also, there two columns don't contain important informations reader required.
+ Only keep the **numbers_of_review** column since the latter two related columns won't effect the accuracy of the analysis

## Data Analysis in MongoDB

1. show exactly two documents from the `listings` collection in any order

```
db.listings.find().limit(2)
```

Result (only show first three documents):

```
{
  "_id": ObjectId("607435380788232654"),
  "listing_url": "https://www.airbnb.com/rooms/607435380788232654",
  "scrape_id": "20231229025659",
  "last_scraped": "2023-12-29",
  "source": "city scrape",
  "name": "Home in Denver · 1 bedroom · 1 bed · 1 shared bath",
  "neighborhood_overview": "",
  "picture_url": "https://a0.muscache.com/pictures/miso/Hosting-607435380788232654/original/18997281-dc60-4432-bac1-3948e6f6174c.jpeg",
  "host_id": 430149575,
  "host_url": "https://www.airbnb.com/users/show/430149575",
  "host_name": "Roye",
  "host_since": "2021-11-02",
  "host_location": "",
  "host_about": "",
  "host_response_time": "within an hour",
  "host_response_rate": "100%",
  "host_acceptance_rate": "75%",
  "host_is_superhost": "f",
  "host_thumbnail_url": "https://a0.muscache.com/im/pictures/user/c8b951f8-c431-4126-a649-11dab14bfe43.jpg?aki_policy=profile_small",
  "host_picture_url": "https://a0.muscache.com/im/pictures/user/c8b951f8-c431-4126-a649-11dab14bfe43.jpg?aki_policy=profile_x_medium",
  "host_neighbourhood": "Congress Park",
  "host_current_listings_count": 8,
  "host_total_listings_count": 23,
  "host_verifications": ["email", "phone"],
  "host_has_profile_pic": "t",
  "host_identity_verified": "t",
  "neighbourhood_cleansed": "North Park Hill",
  "property_type": "Private room in home",
  "room_type": "Private room",
  "accommodates": 1,
  "bathrooms": "1 shared bath",
  "beds": 1,
  "price": "$35.00",
  "minimum_nights": 30,
  "maximum_nights": 365,
  "has_availability": true,
  "calendar_last_scraped": "2023-12-29",
  "number_of_reviews": 2,
  "review_scores_rating": 3.0,
  "review_scores_accuracy": 2.5,
  "review_scores_cleanliness": 2.5,
  "review_scores_checkin": 3.0,
  "review_scores_communication": 3.5,
  "review_scores_location": 4.0,
  "review_scores_value": 3.0,
  "license": "",
  "instant_bookable": "f",
  "reviews_per_month": 0.11
}
```

```
{
  "_id": ObjectId("545714833502855511"),
  "id": 545714833502855511,
  "listing_url": "https://www.airbnb.com/rooms/545714833502855511",
  "scrape_id": "20231229025659",
  "last_scraped": "2023-12-29",
  "source": "city scrape",
  "name": "Rental unit in Denver · 2 bedrooms · 3 beds · 2 baths",
  "neighborhood_overview": "",
  "picture_url": "https://a0.muscache.com/pictures/miso/Hosting-545714833502855511/original/72050442-7cc5-4efe-95c3-a1ccb10e485d.jpeg",
  "host_id": 169214047,
  "host_url": "https://www.airbnb.com/users/show/169214047",
  "host_name": "Jerrod",
  "host_since": "2018-01-22",
  "host_location": "Chicago, IL",
  "host_about": "",
  "host_response_time": "N/A",
  "host_response_rate": "N/A",
  "host_acceptance_rate": "0%",
  "host_is_superhost": "f",
  "host_thumbnail_url": "https://a0.muscache.com/im/pictures/user/b7709ffb-1e7a-4382-acf4-e91c339d0c37.jpg?aki_policy=profile_small",
  "host_picture_url": "https://a0.muscache.com/im/pictures/user/b7709ffb-1e7a-4382-acf4-e91c339d0c37.jpg?aki_policy=profile_x_medium",
  "host_neighbourhood": "East",
  "host_current_listings_count": 1,
  "host_total_listings_count": 2,
  "host_verifications": ["email", "phone"],
  "host_has_profile_pic": "t",
  "host_identity_verified": "t",
  "neighbourhood_cleansed": "Hale",
  "property_type": "Entire rental unit",
  "room_type": "Entire home/apt",
  "accommodates": 6,
  "bathrooms": "2 baths",
  "beds": 3,
  "price": "$149.00",
  "minimum_nights": 30,
  "maximum_nights": 365,
  "has_availability": true,
  "calendar_last_scraped": "2023-12-29",
  "number_of_reviews": 0,
  "review_scores_rating": "",
  "review_scores_accuracy": "",
  "review_scores_cleanliness": "",
  "review_scores_checkin": "",
  "review_scores_communication": "",
  "review_scores_location": "",
  "review_scores_value": "",
  "license": "",
  "instant_bookable": "f",
  "reviews_per_month": ""
}
```

2. show exactly 10 documents in any order, only show `id`,`name`,`host_id`,`host_name`, and `price`, but "prettyprint" in easier to read format, using the `pretty()` function.

```
db.listings.find({},{_id: 1,name: 1,host_id: 1,host_name: 1,price: 1}).limit(10).pretty()
```

Result (only show first three documents):

```
{
  "_id": ObjectId("607435380788232654"),
  "name": "Home in Denver · 1 bedroom · 1 bed · 1 shared bath",
  "host_id": 430149575,
  "host_name": "Roye",
  "price": "$35.00"
}
```

```
{
  "_id": ObjectId("545714833502855511"),
  "name": "Rental unit in Denver · 2 bedrooms · 3 beds · 2 baths",
  "host_id": 169214047,
  "host_name": "Jerrod",
  "price": "$149.00"
}
```

```
{
  "_id": ObjectId("43920210"),
  "name": "Guest suite in Denver · ★4.38 · 3 bedrooms · 4 beds · 2 baths",
  "host_id": 3484713,
  "host_name": "Vu",
  "price": ""
}
```

3. choose two hosts (by reffering to their `host_id` values) who are superhosts (available in the `host_is_superhost` field), and show all of the listings offered by both of the two hosts (only show the `name`, `price`, `neighbourhood`, `host_name`, and `host_is_superhost` for each result)

```
var superhosts = db.listings.find({ host_is_superhost: "t" }).limit(2);
var allListings = [];
superhosts.forEach(function(superhost) {
    var listings = db.listings.find({ host_id: superhost.host_id }, { name: 1, price: 1, neighbourhood_cleansed: 1, host_name: 1, host_is_superhost: 1 }).toArray();
    allListings = allListings.concat(listings);});
printjson(allListings);
```

Result (only show first three documents):

```
{
  "name": "Guesthouse in Denver · ★4.99 · 2 bedrooms · 2 beds · 1 bath",
  "price": "$77.00",
  "neighbourhood_cleansed": "Highland",
  "host_name": "Jennifer & Giovanni",
  "host_is_superhost": "t"
}
```

```
{
  "name": "Cottage in Denver · ★4.92 · 1 bedroom · 1 bed · 1 bath",
  "price": "$127.00",
  "neighbourhood_cleansed": "Highland",
  "host_name": "Jennifer & Giovanni",
  "host_is_superhost": "t"
}
```

```
{
  "name": "Home in Denver · ★5.0 · 6 bedrooms · 9 beds · 4 baths",
  "price": "$299.00",
  "neighbourhood_cleansed": "Congress Park",
  "host_name": "Jenny",
  "host_is_superhost": "t"
}
```

4. find all the unique `host_name` values (see [the docs](https://docs.mongodb.com/manual/reference/method/db.collection.distinct/))

```
var uniqueHostNames = db.listings.distinct("host_name");
```

Result (only show first three documents):

```
{ "host_name": "Roye" }
```

```
{ "host_name": "Jerrod" }
```

```
{ "host_name": "Vu" }
```

5. find all of the places that have more than 2 `beds` in `neighbourhood_cleansed` fields named "Five Points" in the data file), ordered by `review_scores_rating` descending (only show the `name`, `beds`, `review_scores_rating`, and `price` coloumns)

```
db.listings.find({
    neighborhood_cleansed: "Five Points",
    beds: { $gt: 2 }
}, {
    name: 1, 
    beds: 1,
    review_scores_rating: 1,
    price: 1
}).sort({
    review_scores_rating: -1});
```

Result (only show first three documents):

```
{
  "name": "Hostel in Denver · 1 bedroom · 8 beds · 4 shared baths",
  "beds": 8,
  "review_scores_rating": null,
  "price": "$314.00"
}
```

```
{
  "name": "Rental unit in Denver · 2 bedrooms · 4 beds · 2 baths",
  "beds": 4,
  "review_scores_rating": null,
  "price": "$104.00"
}
```

```
{
  "name": "Home in Denver · 4 bedrooms · 4 beds · 2.5 baths",
  "beds": 4,
  "review_scores_rating": null,
  "price": "$1,600.00"
}
```

6. show the number of listings per host

```
db.listings.aggregate([
    {
        $group: {
            _id: "$host_id",
            count: { $sum: 1 }
        }
    }
]);
```

Result (only show first three documents):

```
{
  "host_id": 589,
  "count": 1
}
```

```
{
  "host_id": 666,
  "count": 2
}
```

```
{
  "host_id": 774,
  "count": 1
}
```

7. find the average `review_scores_rating` per `neighborhood_cleansed`, and only show those that are `4` or above, sorted in descending order of rating (see [the docs](https://docs.mongodb.com/manual/reference/operator/aggregation/sort/))

```
db.listings.aggregate([
    {
        $group: {
            _id: "$neighbourhood_cleansed",
            avg_rating: { $avg: "$review_scores_rating" }
        }
    },
    {
        $match: {
            avg_rating: { $gte: 4 }
        }
    },
    {
        $sort: {
            avg_rating: -1
        }
    }
]);
```

Result (only show first three documents):

```
{
  "neighbourhood_cleansed": "Sun Valley",
  "avg_rating": 4.78
}
```

```
{
  "neighbourhood_cleansed": "Clayton",
  "avg_rating": 4.65659090909091
}
```

```
{
  "neighbourhood_cleansed": "Whittier",
  "avg_rating": 4.64695652173913
}
```
