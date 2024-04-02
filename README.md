# AirBnB MongoDB Analysis

## Dataset Details

### Origin of the Dataset
 The dataset used for this analysis comprises Airbnb listings for Toronto, Ontario, Canada. It is publicly available from [Inside Airbnb](http://insideairbnb.com/get-the-data/).

### Data Format
The original data file was in a compressed CSV format (`.csv.gz`); and it can be unzipped to a CSV file.

### Sample of Raw Data
Below is a table showing the first 20 rows from the original data file:

| id     | listing_url                         | scrape_id | last_scraped | source          | name                                               | description                                                                                                                                                                                                                                                                                                                 | neighborhood_overview                                                                                   | picture_url                                                                                             | host_id                                   | host_url                                  | host_name             | host_since        | host_location     | host_about                                                              | host_response_time | host_response_rate | host_acceptance_rate                                                                                  | host_is_superhost                                                                                                                 | host_thumbnail_url                                                                                                                   | host_picture_url                                                                                              | host_neighbourhood     | host_listings_count | host_total_listings_count        | host_verifications               | host_has_profile_pic | host_identity_verified   | neighbourhood                     | neighbourhood_cleansed            | neighbourhood_group_cleansed | latitude                    | longitude             | property_type   | room_type | accommodates  | bathrooms      | bathrooms_text | bedrooms      | beds          | amenities | price | minimum_nights | maximum_nights | minimum_minimum_nights | maximum_minimum_nights | minimum_maximum_nights | maximum_maximum_nights | minimum_nights_avg_ntm | maximum_nights_avg_ntm | calendar_updated | has_availability | availability_30 | availability_60 | availability_90 | availability_365 | calendar_last_scraped | number_of_reviews | number_of_reviews_ltm | number_of_reviews_l30d | first_review | last_review | review_scores_rating | review_scores_accuracy | review_scores_cleanliness | review_scores_checkin | review_scores_communication | review_scores_location | review_scores_value | license | instant_bookable | calculated_host_listings_count | calculated_host_listings_count_entire_homes | calculated_host_listings_count_private_rooms | calculated_host_listings_count_shared_rooms | reviews_per_month |
| ------ | ----------------------------------- | --------- | ------------ | --------------- | -------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | ----------------------------------------- | ----------------------------------------- | --------------------- | ----------------- | ----------------- | ----------------------------------------------------------------------- | ------------------ | ------------------ | ----------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------- | ---------------------- | ------------------- | -------------------------------- | -------------------------------- | -------------------- | ------------------------ | --------------------------------- | --------------------------------- | ---------------------------- | --------------------------- | --------------------- | --------------- | --------- | ------------- | -------------- | -------------- | ------------- | ------------- | --------- | ----- | -------------- | -------------- | ---------------------- | ---------------------- | ---------------------- | ---------------------- | ---------------------- | ---------------------- | ---------------- | ---------------- | --------------- | --------------- | --------------- | ---------------- | --------------------- | ----------------- | --------------------- | ---------------------- | ------------ | ----------- | -------------------- | ---------------------- | ------------------------- | --------------------- | --------------------------- | ---------------------- | ------------------- | ------- | ---------------- | ------------------------------ | ------------------------------------------- | -------------------------------------------- | ------------------------------------------- | ----------------- |
| 1419   | https://www.airbnb.com/rooms/1419   | 2.02E+13  | 2/15/2024    | previous scrape | Beautiful home in amazing area!                    | This large                                                                                                                                                                                                                                                                                                                  | The apartment                                                                                           | https://a0.muscache.com/pictures/76206750/d64310e4_original.jpg                                         | 1565                                      | https://www.airbnb.com/users/show/1565    | Alexandra             | 8/8/2008          | Vancouver, Canada | I live in                                                               | N/A                | N/A                | N/A                                                                                                   | f                                                                                                                                 | https://a0.muscache.com/im/pictures/user/7aeea16d-829a-4d68-8dff-6c9c0ce1d3bf.jpg?aki_policy=profile_small                           | https://a0.muscache.com/im/pictures/user/7aeea16d-829a-4d68-8dff-6c9c0ce1d3bf.jpg?aki_policy=profile_x_medium | Commercial Drive       | 1                   | 1                                | ['email', 'phone']               | t                    | t                        | Toronto, Ontario, Canada          | Little Portugal                   | 43.6459                      | \-79.4242                   | Entire home           | Entire home/apt | 10        |               | 3 baths        | 5              |               | ["Wifi"]      |           | 28    | 730            | 28             | 28                     | 730                    | 730                    | 28                     | 730                    |                        | t                | 0                | 0               | 0               | 0               | 2/15/2024        | 6                     | 0                 | 0                     | 7/19/2015              | 8/7/2017     | 5           | 5                    | 5                      | 5                         | 5                     | 5                           | 5                      |                     | f       | 1                | 1                              | 0                                           | 0                                            | 0.06                                        |
| 8077   | https://www.airbnb.com/rooms/8077   | 2.02E+13  | 2/15/2024    | previous scrape | Downtown Harbourfront Private Room                 | Guest room                                                                                                                                                                                                                                                                                                                  | https://a0.muscache.com/pictures/11780344/141c2c88_original.jpg                                         | 22795                                                                                                   | https://www.airbnb.com/users/show/22795   | Kathie & Larry                            | 6/22/2009             | Toronto, Canada   | My husband and I  | N/A                                                                     | N/A                | N/A                | f                                                                                                     | https://a0.muscache.com/im/pictures/user/9a077853-cb8c-49aa-91b4-d1bbd6b220a0.jpg?aki_policy=profile_small                        | https://a0.muscache.com/im/pictures/user/9a077853-cb8c-49aa-91b4-d1bbd6b220a0.jpg?aki_policy=profile_x_medium                        | Harbourfront                                                                                                  | 2                      | 3                   | ['email', 'phone']               | t                                | f                    |                          | Waterfront Communities-The Island | 43.6408                           | \-79.3767                    | Private room in rental unit | Private room          | 2               |           | 1.5 baths     |                |                | ["Wifi"]      |               | 180       | 365   | 180            | 180            | 365                    | 365                    | 180                    | 365                    |                        | t                      | 0                | 0                | 0               | 0               | 2/15/2024       | 169              | 0                     | 0                 | 8/20/2009             | 8/27/2013              | 4.84         | 4.81        | 4.89                 | 4.87                   | 4.9                       | 4.92                  | 4.83                        |                        | f                   | 2       | 1                | 1                              | 0                                           | 0.96                                         |
| 26654  | https://www.airbnb.com/rooms/26654  | 2.02E+13  | 2/15/2024    | city scrape     | World Class @ CN Tower, convention centre, Theatre | CN Tower during your visit to Toronto!<br /><br />Why not stay with us on location? You'll be glad you did.                                                                                                                                                                                                                 | There's a reason                                                                                        | https://a0.muscache.com/pictures/81811785/5dcd6dd9_original.jpg                                         | 113345                                    | https://www.airbnb.com/users/show/113345  | Adela                 | 4/25/2010         |                   | Welcome to Toronto!<br><br><br><br>After our first                      | within a few hours | 100%               | 41%                                                                                                   | f                                                                                                                                 | https://a0.muscache.com/im/users/113345/profile_pic/1440562246/original.jpg?aki_policy=profile_small                                 | https://a0.muscache.com/im/users/113345/profile_pic/1440562246/original.jpg?aki_policy=profile_x_medium       | Entertainment District | 6                   | 10                               | ['email', 'phone', 'work_email'] | t                    | t                        | Toronto, Ontario, Canada          | Waterfront Communities-The Island | 43.64608                     | \-79.3903                   | Entire condo          | Entire home/apt | 4         | 1             | 1 bath         | 1              | 2             | ["Wifi"]      | $164.00   | 28    | 1125           | 28             | 28                     | 1125                   | 1125                   | 28                     | 1125                   |                        | t                | 0                | 0               | 0               | 115             | 2/15/2024        | 42                    | 2                 | 0                     | 1/5/2011               | 9/1/2023     | 4.79        | 4.79                 | 4.79                   | 4.64                      | 4.76                  | 4.86                        | 4.67                   |                     | f       | 5                | 5                              | 0                                           | 0                                            | 0.26                                        |
| 307726 | https://www.airbnb.com/rooms/307726 | 2.02E+13  | 2/15/2024    | previous scrape | Boutique Chic at Maple Leaf Square                 | This is a private studio Please read full description below.                                                                                                                                                                                                                                                                | Our condo                                                                                               | https://a0.muscache.com/pictures/100fe901-bb9c-47ba-96b3-cce0b0514725.jpg                               | 1108156                                   | https://www.airbnb.com/users/show/1108156 | Karen                 | 9/4/2011          | Toronto, Canada   | I love traveling <br><br>As a host I share <br><br>I am a producer      | within an hour     | 100%               | 75%                                                                                                   | t                                                                                                                                 | https://a0.muscache.com/im/users/1108156/profile_pic/1317565617/original.jpg?aki_policy=profile_small                                | https://a0.muscache.com/im/users/1108156/profile_pic/1317565617/original.jpg?aki_policy=profile_x_medium      | Entertainment District | 2                   | 5                                | ['email', 'phone']               | t                    | t                        | Toronto, Ontario, Canada          | Waterfront Communities-The Island | 43.64221                     | \-79.3806                   | Entire condo          | Entire home/apt | 2         |               | 1 bath         |                |               | ["Wifi"]      |           | 28    | 1124           | 28             | 28                     | 1124                   | 1124                   | 28                     | 1124                   |                        | t                | 0                | 0               | 0               | 0               | 2/15/2024        | 66                    | 0                 | 0                     | 1/26/2012              | 5/28/2022    | 4.97        | 4.92                 | 4.86                   | 4.97                      | 4.98                  | 4.98                        | 4.86                   |                     | f       | 2                | 2                              | 0                                           | 0                                            | 0.45                                        |
| 314459 | https://www.airbnb.com/rooms/314459 | 2.02E+13  | 2/15/2024    | previous scrape | Cosy room by Toronto's Danforth Ave                | Cosy room                                                                                                                                                                                                                                                                                                                   | The neighbourhood is leafy                                                                              | https://a0.muscache.com/pictures/64761885/18b6f53c_original.jpg                                         | 1615944                                   | https://www.airbnb.com/users/show/1615944 | Julia                 | 1/16/2012         | Toronto, Canada   | I am a writer,                                                          | N/A                | N/A                | N/A                                                                                                   | f                                                                                                                                 | https://a0.muscache.com/im/pictures/user/fa79efbe-11e8-4b27-a0d1-042530e9801b.jpg?aki_policy=profile_small                           | https://a0.muscache.com/im/pictures/user/fa79efbe-11e8-4b27-a0d1-042530e9801b.jpg?aki_policy=profile_x_medium | The Pocket             | 2                   | 2                                | ['email', 'phone', 'work_email'] | t                    | t                        | Toronto, Ontario, Canada          | Blake-Jones                       | 43.67739                     | \-79.336                    | Private room in home  | Private room    | 1         |               | 1 shared bath  |                | ["Wifi"]      |               | 28        | 1125  | 28             | 28             | 1125                   | 1125                   | 28                     | 1125                   |                        | t                      | 0                | 0                | 0               | 0               | 2/15/2024       | 37               | 0                     | 0                 | 7/5/2012              | 1/31/2023              | 5            | 4.97        | 4.78                 | 4.97                   | 5                         | 4.94                  | 4.92                        |                        | f                   | 1       | 0                | 1                              | 0                                           | 0.26                                         |
| 325432 | https://www.airbnb.com/rooms/325432 | 2.02E+13  | 2/15/2024    | previous scrape | Great 'hood, no car needed, 3.5br                  | Conveniently-located                                                                                                                                                                                                                                                                                                        | Family friendly                                                                                         | https://a0.muscache.com/pictures/3873323/838e7a53_original.jpg                                          | 1664812                                   | https://www.airbnb.com/users/show/1664812 | Mark                  | 1/28/2012         | Toronto, Canada   | Husband of                                                              | N/A                | N/A                | N/A                                                                                                   | f                                                                                                                                 | https://a0.muscache.com/im/users/1664812/profile_pic/1327775021/original.jpg?aki_policy=profile_small                                | https://a0.muscache.com/im/users/1664812/profile_pic/1327775021/original.jpg?aki_policy=profile_x_medium      | High Park North        | 1                   | 1                                | ['email', 'phone']               | t                    | t                        | Toronto, Ontario, Canada          | High Park North                   | 43.66106                     | \-79.4561                   | Entire home           | Entire home/apt | 8         |               | 2 baths        | 4              |               | ["Wifi"]      |           | 28    | 50             | 28             | 28                     | 50                     | 50                     | 28                     | 50                     |                        | t                | 0                | 0               | 0               | 0               | 2/15/2024        | 0                     | 0                 | 0                     |                        |              |             |                      |                        |                           |                       |                             |                        |                     | f       | 1                | 1                              | 0                                           | 0                                            |                                             |
| 27423  | https://www.airbnb.com/rooms/27423  | 2.02E+13  | 2/15/2024    | city scrape     | Executive Studio Unit- Ideal for One Person        | Brand new Private washroom and washer/dryer.  Single bed and convertible queen size futon.  Access to shared backyard and huge two level deck with BBQ.  Well lit separate entrance. No pets allowed.<br /><br />This is perfect for someone with a laptop and a suitcase.  Looking only for long term rentals (3+ months). | https://a0.muscache.com/pictures/176936/b687ed16_original.jpg                                           | 118124                                                                                                  | https://www.airbnb.com/users/show/118124  | Brent                                     | 5/4/2010              | Toronto, Canada   | I love to travel  | within a few hours                                                      | 100%               | 100%               | f                                                                                                     | https://a0.muscache.com/im/pictures/user/User-118124/original/fd8e76c5-f8a1-4547-b324-43e396699cfb.jpeg?aki_policy=profile_small  | https://a0.muscache.com/im/pictures/user/User-118124/original/fd8e76c5-f8a1-4547-b324-43e396699cfb.jpeg?aki_policy=profile_x_medium  | Greenwood-Coxwell                                                                                             | 1                      | 1                   | ['email', 'phone', 'work_email'] | t                                | t                    |                          | South Riverdale                   | 43.66884                          | \-79.3273                    | Entire rental unit          | Entire home/apt       | 1               | 1         | 1 bath        | 0              | 1              | ["Wifi"]      | $75.00        | 90        | 365   | 90             | 90             | 365                    | 365                    | 90                     | 365                    |                        | t                      | 10               | 13               | 13              | 146             | 2/15/2024       | 28               | 1                     | 0                 | 6/7/2010              | 8/31/2023              | 4.93         | 5           | 4.85                 | 5                      | 5                         | 4.85                  | 4.85                        |                        | f                   | 1       | 1                | 0                              | 0                                           | 0.17                                         |
| 335446 | https://www.airbnb.com/rooms/335446 | 2.02E+13  | 2/15/2024    | city scrape     | Quiet Oasis near Eaton Centre                      | Charming attic                                                                                                                                                                                                                                                                                                              | Nestled in                                                                                              | https://a0.muscache.com/pictures/miso/Hosting-335446/original/74cfe83d-d94d-4f06-8542-ed69ebfb2414.jpeg | 1704172                                   | https://www.airbnb.com/users/show/1704172 | Vanessa               | 2/5/2012          | Toronto, Canada   | \-- The Fancy <br>                                                      | thin an hour       | 100%               | 100%                                                                                                  | t                                                                                                                                 | https://a0.muscache.com/im/pictures/user/c5a552a0-8e85-43e0-b855-c33bad4da1d6.jpg?aki_policy=profile_small                           | https://a0.muscache.com/im/pictures/user/c5a552a0-8e85-43e0-b855-c33bad4da1d6.jpg?aki_policy=profile_x_medium | Garden District        | 3                   | 8                                | ['email', 'phone']               | t                    | t                        | Toronto, Ontario, Canada          | Moss Park                         | 43.65744                     | \-79.3723                   | Private room in condo | Private room    | 1         | 1             | 1 private bath | 1              | 1             | ["Wifi"]      | $100.00   | 28    | 1125           | 28             | 28                     | 1125                   | 1125                   | 28                     | 1125                   |                        | t                | 0                | 0               | 2               | 277             | 2/15/2024        | 121                   | 1                 | 0                     | 3/8/2012               | 12/17/2023   | 4.85        | 4.72                 | 4.7                    | 4.97                      | 4.96                  | 4.53                        | 4.78                   |                     | t       | 2                | 1                              | 1                                           | 0                                            | 0.83                                        |
| 30931  | https://www.airbnb.com/rooms/30931  | 2.02E+13  | 2/15/2024    | previous scrape | Downtown Toronto - Waterview Condo                 | Split level waterfront                                                                                                                                                                                                                                                                                                      | https://a0.muscache.com/pictures/227971/e8ebd7e4_original.jpg                                           | 22795                                                                                                   | https://www.airbnb.com/users/show/22795   | Kathie & Larry                            | 6/22/2009             | Toronto, Canada   | My husband and I  | N/A                                                                     | N/A                | N/A                | f                                                                                                     | https://a0.muscache.com/im/pictures/user/9a077853-cb8c-49aa-91b4-d1bbd6b220a0.jpg?aki_policy=profile_small                        | https://a0.muscache.com/im/pictures/user/9a077853-cb8c-49aa-91b4-d1bbd6b220a0.jpg?aki_policy=profile_x_medium                        | Harbourfront                                                                                                  | 2                      | 3                   | ['email', 'phone']               | t                                | f                    |                          | Waterfront Communities-The Island | 43.64015                          | \-79.3763                    | Entire rental unit          | Entire home/apt       | 2               |           | 1.5 baths     | 1              |                | ["Wifi"]      |               | 180       | 365   | 180            | 180            | 365                    | 365                    | 180                    | 365                    |                        | t                      | 0                | 0                | 0               | 0               | 2/15/2024       | 1                | 0                     | 0                 | 8/11/2010             | 8/11/2010              | 5            |             |                      |                        |                           |                       |                             |                        | f                   | 2       | 1                | 1                              | 0                                           | 0.01                                         |
| 339418 | https://www.airbnb.com/rooms/339418 | 2.02E+13  | 2/15/2024    | city scrape     | Cozy Room in Midtown Near Subway                   | The Apartment                                                                                                                                                                                                                                                                                                               | https://a0.muscache.com/pictures/miso/Hosting-339418/original/a0fd55b3-ee51-4cee-9e00-e2c2aca14805.jpeg | 1027776                                                                                                 | https://www.airbnb.com/users/show/1027776 | Willy                                     | 8/27/2011             | Toronto, Canada   | Both my wife      | N/A                                                                     | N/A                | N/A                | f                                                                                                     | https://a0.muscache.com/im/pictures/user/User-1027776/original/1c7aca8c-6bdf-4e11-9aa8-a48a3ee5b0a1.jpeg?aki_policy=profile_small | https://a0.muscache.com/im/pictures/user/User-1027776/original/1c7aca8c-6bdf-4e11-9aa8-a48a3ee5b0a1.jpeg?aki_policy=profile_x_medium | Davisville                                                                                                    | 1                      | 2                   | ['phone', 'work_email']          | t                                | t                    |                          | Mount Pleasant West               | 43.69954                          | \-79.3933                    | Private room in rental unit | Private room          | 2               | 1         | 1 shared bath | 1              | 0              | ["Microwave"] | $60.00        | 28        | 90    | 28             | 28             | 1125                   | 1125                   | 28                     | 1125                   |                        | t                      | 0                | 0                | 0               | 0               | 2/15/2024       | 85               | 0                     | 0                 | 3/6/2012              | 2/29/2020              | 4.5          | 4.33        | 4.11                 | 4.59                   | 4.67                      | 4.65                  | 4.36                        |                        | f                   | 1       | 0                | 1                              | 0                                           | 0.58                                         |
| 40456  | https://www.airbnb.com/rooms/40456  | 2.02E+13  | 2/15/2024    | previous scrape | Downtown- King Size Bed and Parking                | 2 bedroom apartment                                                                                                                                                                                                                                                                                                         | This is nice                                                                                            | https://a0.muscache.com/pictures/b36b6ae3-20aa-4ad7-b6cf-3b8cbad0859c.jpg                               | 174063                                    | https://www.airbnb.com/users/show/174063  | Denis                 | 7/20/2010         | Toronto, Canada   | I enjoy hosting                                                         | within an hour     | 100%               | 100%                                                                                                  | t                                                                                                                                 | https://a0.muscache.com/im/users/174063/profile_pic/1315102314/original.jpg?aki_policy=profile_small                                 | https://a0.muscache.com/im/users/174063/profile_pic/1315102314/original.jpg?aki_policy=profile_x_medium       | Parkdale               | 4                   | 5                                | ['email', 'phone']               | t                    | t                        | Toronto, Ontario, Canada          | South Parkdale                    | 43.63539                     | \-79.4401                   | Entire home           | Entire home/apt | 5         |               | 1 bath         | 2              |               | ["Microwave"] | 750       | 1125  | 750            | 750            | 1125                   | 1125                   | 750                    | 1125                   |                        | t                      | 29               | 59               | 89              | 364             | 2/15/2024       | 113              | 2                     | 0                 | 8/3/2010              | 6/19/2023              | 4.64         | 4.65        | 4.67                 | 4.95                   | 4.96                      | 4.58                  | 4.69                        |                        | f                   | 4       | 4                | 0                              | 0                                           | 0.69                                         |
| 361557 | https://www.airbnb.com/rooms/361557 | 2.02E+13  | 2/15/2024    | previous scrape | Downtown/Stylish 2 Bdr.   Apt /Garden +Parking     | convenient                                                                                                                                                                                                                                                                                                                  | https://a0.muscache.com/pictures/409083ee-e3bf-4a81-abee-4604fcb2edf7.jpg                               | 174063                                                                                                  | https://www.airbnb.com/users/show/174063  | Denis                                     | 7/20/2010             | Toronto, Canada   | I enjoy hosting   | within an hour                                                          | 100%               | 100%               | t                                                                                                     | https://a0.muscache.com/im/users/174063/profile_pic/1315102314/original.jpg?aki_policy=profile_small                              | https://a0.muscache.com/im/users/174063/profile_pic/1315102314/original.jpg?aki_policy=profile_x_medium                              | Parkdale                                                                                                      | 4                      | 5                   | ['email', 'phone']               | t                                | t                    | Toronto, Ontario, Canada | South Parkdale                    | 43.63557                          | \-79.44                      | Entire home                 | Entire home/apt       | 5               |           | 1 bath        | 9              |                | ["Microwave"] | 750           | 1125      | 750   | 750            | 1125           | 1125                   | 750                    | 1125                   |                        | t                      | 29                     | 59               | 89               | 364             | 2/15/2024       | 65              | 0                | 0                     | 8/9/2012          | 2/5/2022              | 4.76                   | 4.65         | 4.71        | 4.97                 | 4.95                   | 4.67                      | 4.72                  |                             | f                      | 4                   | 4       | 0                | 0                              | 0.46                                        |
| 42892  | https://www.airbnb.com/rooms/42892  | 2.02E+13  | 2/15/2024    | city scrape     | Downtown 3 Beds 2 Baths @ Union & Harbourfront     | Modern and stylish                                                                                                                                                                                                                                                                                                          | Downtown                                                                                                | https://a0.muscache.com/pictures/miso/Hosting-42892/original/ec92b62d-8bf7-43f1-9e35-a0a5a6855e75.jpeg  | 187320                                    | https://www.airbnb.com/users/show/187320  | Downtown Suite Living | 8/1/2010          | Toronto, Canada   | Hey there<br><br>We look <br><br>Relax, You're Home!<br><br>Thanks,<br> | within a few hours | 100%               | 44%                                                                                                   | t                                                                                                                                 | https://a0.muscache.com/im/users/187320/profile_pic/1444258888/original.jpg?aki_policy=profile_small                                 | https://a0.muscache.com/im/users/187320/profile_pic/1444258888/original.jpg?aki_policy=profile_x_medium       | Entertainment District | 12                  | 13                               | ['email', 'phone']               | t                    | t                        | Toronto, Ontario, Canada          | Waterfront Communities-The Island | 43.6445                      | \-79.3802                   | Entire condo          | Entire home/apt | 4         | 2             | 2 baths        | 3              | 3             | ["Microwave"] | $140.00   | 30    | 365            | 90             | 90                     | 365                    | 365                    | 90                     | 365                    |                        | t                | 29               | 59              | 89              | 364             | 2/15/2024        | 0                     | 0                 | 0                     |                        |              |             |                      |                        |                           |                       |                             |                        |                     | f       | 12               | 7                              | 5                                           | 0                                            |                                             |
| 361831 | https://www.airbnb.com/rooms/361831 | 2.02E+13  | 2/15/2024    | previous scrape | Townhome/Condo at The Mona Lisa                    | https://a0.muscache.com/pictures/4047716/99afc6b1_original.jpg                                                                                                                                                                                                                                                              | 1828773                                                                                                 | https://www.airbnb.com/users/show/1828773                                                               | Silvana                                   | 2/28/2012                                 |                       |                   | N/A               | N/A                                                                     | N/A                | f                  | https://a0.muscache.com/im/users/1828773/profile_pic/1330491234/original.jpg?aki_policy=profile_small | https://a0.muscache.com/im/users/1828773/profile_pic/1330491234/original.jpg?aki_policy=profile_x_medium                          | Willowdale                                                                                                                           | 1                                                                                                             | 2                      | ['email', 'phone']  | t                                | f                                |                      | Willowdale East          | 43.77873                          | \-79.4125                         | Private room in rental unit  | Private room                | 1                     |                 | 1 bath    | 1             |                | ["Microwave"]  | 28            | 365           | 28        | 28    | 365            | 365            | 28                     | 365                    |                        | t                      | 0                      | 0                      | 0                | 0                | 2/15/2024       | 0               | 0               | 0                |                       |                   |                       |                        |              |             |                      |                        |                           |                       | f                           | 1                      | 0                   | 1       | 0                |                                |
| 43964  | https://www.airbnb.com/rooms/43964  | 2.02E+13  | 2/15/2024    | previous scrape | Private Basement Apartment with Parking            | Very bright                                                                                                                                                                                                                                                                                                                 | super                                                                                                   | https://a0.muscache.com/pictures/5ce26405-6792-427e-83a8-dcdf8061e3ba.jpg                               | 192364                                    | https://www.airbnb.com/users/show/192364  | Mitra                 | 8/5/2010          | Toronto, Canada   | Love to meet                                                            | within an hour     | 100%               | 96%                                                                                                   | t                                                                                                                                 | https://a0.muscache.com/im/pictures/user/9052c613-bda0-43d4-bded-b8c21634bb13.jpg?aki_policy=profile_small                           | https://a0.muscache.com/im/pictures/user/9052c613-bda0-43d4-bded-b8c21634bb13.jpg?aki_policy=profile_x_medium | Wexford/Maryvale       | 1                   | 1                                | ['email', 'phone']               | t                    | t                        | Toronto, Ontario, Canada          | Wexford/Maryvale                  | 43.74922                     | \-79.2919                   | Entire home           | Entire home/apt | 4         |               | 1 bath         | 2              |               | ["Microwave"] | 1         | 31    | 1              | 1              | 31                     | 31                     | 1                      | 31                     |                        | t                      | 0                | 0                | 0               | 0               | 2/15/2024       | 67               | 13                    | 0                 | 1/4/2017              | 9/25/2023              | 4.96         | 4.96        | 4.99                 | 4.99                   | 4.97                      | 4.85                  | 4.88                        | STR-2012-FMQPHC        | f                   | 1       | 1                | 0                              | 0                                           | 0.77                                         |
| 44452  | https://www.airbnb.com/rooms/44452  | 2.02E+13  | 2/15/2024    | city scrape     | Yonge & Bloor Studio Skyline                       | https://a0.muscache.com/pictures/395bd5b5-795a-4721-bd14-2d5988e8cf6c.jpg                                                                                                                                                                                                                                                   | 195095                                                                                                  | https://www.airbnb.com/users/show/195095                                                                | Urbano                                    | 8/8/2010                                  | Toronto, Canada       | Boutique          | within a day      | 100%                                                                    | 80%                | t                  | https://a0.muscache.com/im/users/195095/profile_pic/1315086005/original.jpg?aki_policy=profile_small  | https://a0.muscache.com/im/users/195095/profile_pic/1315086005/original.jpg?aki_policy=profile_x_medium                           | Rosedale                                                                                                                             | 13                                                                                                            | 19                     | ['email', 'phone']  | t                                | t                                |                      | Rosedale-Moore Park      | 43.67193                          | \-79.3859                         | Entire rental unit           | Entire home/apt             | 2                     | 1               | 1 bath    | 1             | 1              | ["Microwave"]  | $126.00       | 28            | 365       | 28    | 28             | 365            | 365                    | 28                     | 365                    |                        | t                      | 0                      | 0                | 0                | 219             | 2/15/2024       | 66              | 2                | 0                     | 10/4/2010         | 8/4/2023              | 4.18                   | 4.52         | 4.03        | 4.79                 | 4.84                   | 4.95                      | 4.23                  |                             | f                      | 13                  | 9       | 4                | 0                              | 0.41                                        |
| 363057 | https://www.airbnb.com/rooms/363057 | 2.02E+13  | 2/15/2024    | city scrape     | Charming Century House in Beaches                  | Our charming beach                                                                                                                                                                                                                                                                                                          | one of the best                                                                                         | https://a0.muscache.com/pictures/miso/Hosting-363057/original/8b6a08ac-1379-466a-844e-fb09d8e63083.jpeg | 1816495                                   | https://www.airbnb.com/users/show/1816495 | Katharine             | 2/27/2012         | Toronto, Canada   |  Carpe diem!                                                            | within a few hours | 100%               | 78%                                                                                                   | f                                                                                                                                 | https://a0.muscache.com/im/users/1816495/profile_pic/1405397556/original.jpg?aki_policy=profile_small                                | https://a0.muscache.com/im/users/1816495/profile_pic/1405397556/original.jpg?aki_policy=profile_x_medium      | The Beaches            | 3                   | 5                                | ['email', 'phone']               | t                    | t                        | Toronto, Ontario, Canada          | The Beaches                       | 43.67262                     | \-79.3006                   | Entire home           | Entire home/apt | 7         | 1.5           | 1.5 baths      | 3              | 4             | ["Microwave"] | $168.00   | 1     | 270            | 1              | 28                     | 270                    | 270                    | 3.3                    | 270                    |                        | t                | 22               | 41              | 62              | 197             | 2/15/2024        | 43                    | 18                | 0                     | 7/5/2017               | 1/12/2024    | 4.51        | 4.42                 | 4.47                   | 4.86                      | 4.91                  | 5                           | 4.42                   | STR-2203-GGLHHF     | f       | 3                | 3                              | 0                                           | 0                                            | 0.53                                        |
| 44469  | https://www.airbnb.com/rooms/44469  | 2.02E+13  | 2/15/2024    | city scrape     | Yonge & Bloor 2 Bedroom Apartment                  | https://a0.muscache.com/pictures/250462/fa72a3f3_original.jpg                                                                                                                                                                                                                                                               | 195095                                                                                                  | https://www.airbnb.com/users/show/195095                                                                | Urbano                                    | 8/8/2010                                  | Toronto, Canada       | Boutique property | within a day      | 100%                                                                    | 80%                | t                  | https://a0.muscache.com/im/users/195095/profile_pic/1315086005/original.jpg?aki_policy=profile_small  | https://a0.muscache.com/im/users/195095/profile_pic/1315086005/original.jpg?aki_policy=profile_x_medium                           | Rosedale                                                                                                                             | 13                                                                                                            | 19                     | ['email', 'phone']  | t                                | t                                |                      | Rosedale-Moore Park      | 43.67129                          | \-79.3863                         | Private room in rental unit  | Private room                | 2                     | 1               | 1 bath    | 1             | 1              | ["Microwave"]  | $104.00       | 30            | 1000      | 30    | 30             | 1000           | 1000                   | 30                     | 1000                   |                        | t                      | 0                      | 0                | 0                | 258             | 2/15/2024       | 8               | 0                | 0                     | 9/22/2011         | 8/27/2017             | 4                      | 4.5          | 4           | 4.38                 | 4.75                   | 4.75                      | 4.13                  |                             | f                      | 13                  | 9       | 4                | 0                              | 0.05                                        |
| 366973 | https://www.airbnb.com/rooms/366973 | 2.02E+13  | 2/15/2024    | city scrape     | Spacious Modern Cozy King W Toronto                | Great location                                                                                                                                                                                                                                                                                                              | https://a0.muscache.com/pictures/89639651/c5025077_original.jpg                                         | 1015670                                                                                                 | https://www.airbnb.com/users/show/1015670 | Grace                                     | 8/24/2011             | Toronto, Canada   | I'm from Canada.  | N/A                                                                     | N/A                | N/A                | f                                                                                                     | https://a0.muscache.com/im/users/1015670/profile_pic/1401721067/original.jpg?aki_policy=profile_small                             | https://a0.muscache.com/im/users/1015670/profile_pic/1401721067/original.jpg?aki_policy=profile_x_medium                             | Fashion District                                                                                              | 1                      | 1                   | ['email', 'phone']               | t                                | t                    |                          | Waterfront Communities-The Island | 43.64226                          | \-79.4008                    | Entire loft                 | Entire home/apt       | 2               | 1         | 1 bath        | 1              | 1              | ["Microwave"] | $361.00       | 28        | 112   | 28             | 28             | 112                    | 112                    | 28                     | 112                    |                        | t                      | 23               | 53               | 83              | 358             | 2/15/2024       | 9                | 0                     | 0                 | 7/1/2014              | 9/12/2017              | 4.89         | 5           | 4.78                 | 4.78                   | 4.89                      | 4.56                  | 4.44                        |                        | f                   | 1       | 1                | 0                              | 0                                           | 0.08                                         |
> *Note: Some text in fields has been clipped to prevent line-wrapping*

### Data Scrubbing
Upon initial review, the dataset appeared well-structured and did not require extensive cleaning before import. However, a few adjustments were necessary to ensure the integrity and usability of the data within MongoDB Compass:

- **Handling Missing Values**: Fields with missing values were treated as `null` to maintain consistency across the dataset and ensure that queries would correctly interpret the absence of data.

- **Boolean Value Conversion**: Fields that used 't' and 'f' to represent boolean values were converted to native boolean types (`true`/`false`). This conversion was essential to utilize MongoDB's ability to perform boolean operations accurately.

No further scrubbing was deemed necessary as the dataset maintained a high quality of formatting and completeness. All relevant fields were correctly labeled, and no extraneous information required removal. Future analysis may necessitate additional data transformation, but the initial state of the data is robust enough for the current scope of analysis.

## Analysis

### Analysis 1

1. Show exactly two documents from the `listings` collection in any order.
    ``` js
    db.listings_clean.find().limit(2)
    ```
    **Results**:
    ``` js
    {
        _id: ObjectId('6608dae4fd431e4805715fe5'),
        id: 1419,
        listing_url: 'url',
        scrape_id: 20240214201029,
        last_scraped: 2024-02-15T00:00:00.000Z,
        source: 'previous scrape',
        name: 'Beautiful home in amazing area!',
        description: "large",
        neighborhood_overview: "(see (URL HIDDEN)",
        picture_url: 'url',
        host_id: 1565,
        host_url: 'url',
        host_name: 'Alexandra',
        host_since: 2008-08-08T00:00:00.000Z,
        host_location: 'Vancouver, Canada',
        host_about: ' love to travel! ',
        host_response_time: 'N/A',
        host_response_rate: 'N/A',
        host_acceptance_rate: 'N/A',
        host_is_superhost: false,
        host_thumbnail_url: 'url',
        host_picture_url: 'url',
        host_neighbourhood: 'Commercial Drive',
        host_listings_count: 1,
        host_total_listings_count: 1,
        host_verifications: "['email', 'phone']",
        host_has_profile_pic: true,
        host_identity_verified: true,
        neighbourhood: 'Toronto, Ontario, Canada',
        neighbourhood_cleansed: 'Little Portugal',
        latitude: 43.6459,
        longitude: -79.42423,
        property_type: 'Entire home',
        room_type: 'Entire home/apt',
        accommodates: 10,
        bathrooms_text: '3 baths',
        bedrooms: 5,
        amenities: [
            'Wifi',
            'First aid kit',
        ],
        minimum_nights: 28,
        maximum_nights: 730,
        minimum_minimum_nights: 28,
        maximum_minimum_nights: 28,
        minimum_maximum_nights: 730,
        maximum_maximum_nights: 730,
        minimum_nights_avg_ntm: 28,
        maximum_nights_avg_ntm: 730,
        has_availability: true,
        availability_30: 0,
        availability_60: 0,
        availability_90: 0,
        availability_365: 0,
        calendar_last_scraped: 2024-02-15T00:00:00.000Z,
        number_of_reviews: 6,
        number_of_reviews_ltm: 0,
        number_of_reviews_l30d: 0,
        first_review: 2015-07-19T00:00:00.000Z,
        last_review: 2017-08-07T00:00:00.000Z,
        review_scores_rating: 5,
        review_scores_accuracy: 5,
        review_scores_cleanliness: 5,
        review_scores_checkin: 5,
        review_scores_communication: 5,
        review_scores_location: 5,
        review_scores_value: 5,
        instant_bookable: false,
        calculated_host_listings_count: 1,
        calculated_host_listings_count_entire_homes: 1,
        calculated_host_listings_count_private_rooms: 0,
        calculated_host_listings_count_shared_rooms: 0,
        reviews_per_month: 0.06
    }
    {
        _id: ObjectId('6608dae4fd431e4805715fe6'),
        id: 8077,
        listing_url: 'url',
        scrape_id: 20240214201029,
        last_scraped: 2024-02-15T00:00:00.000Z,
        source: 'previous scrape',
        name: 'Downtown Harbourfront Private Room',
        description: 'luxury',
        picture_url: 'url',
        host_id: 22795,
        host_url: 'url',
        host_name: 'Kathie & Larry',
        host_since: 2009-06-22T00:00:00.000Z,
        host_location: 'Toronto, Canada',
        host_about: 'enjoyed',
        host_response_time: 'N/A',
        host_response_rate: 'N/A',
        host_acceptance_rate: 'N/A',
        host_is_superhost: false,
        host_thumbnail_url: 'url',
        host_picture_url: 'url',
        host_neighbourhood: 'Harbourfront',
        host_listings_count: 2,
        host_total_listings_count: 3,
        host_verifications: "['email', 'phone']",
        host_has_profile_pic: true,
        host_identity_verified: false,
        neighbourhood_cleansed: 'Waterfront Communities-The Island',
        latitude: 43.6408,
        longitude: -79.37673,
        property_type: 'Private room in rental unit',
        room_type: 'Private room',
        accommodates: 2,
        bathrooms_text: '1.5 baths',
        amenities: [
            'Gym',
            'Wifi'
        ],
        minimum_nights: 180,
        maximum_nights: 365,
        minimum_minimum_nights: 180,
        maximum_minimum_nights: 180,
        minimum_maximum_nights: 365,
        maximum_maximum_nights: 365,
        minimum_nights_avg_ntm: 180,
        maximum_nights_avg_ntm: 365,
        has_availability: true,
        availability_30: 0,
        availability_60: 0,
        availability_90: 0,
        availability_365: 0,
        calendar_last_scraped: 2024-02-15T00:00:00.000Z,
        number_of_reviews: 169,
        number_of_reviews_ltm: 0,
        number_of_reviews_l30d: 0,
        first_review: 2009-08-20T00:00:00.000Z,
        last_review: 2013-08-27T00:00:00.000Z,
        review_scores_rating: 4.84,
        review_scores_accuracy: 4.81,
        review_scores_cleanliness: 4.89,
        review_scores_checkin: 4.87,
        review_scores_communication: 4.9,
        review_scores_location: 4.92,
        review_scores_value: 4.83,
        instant_bookable: false,
        calculated_host_listings_count: 2,
        calculated_host_listings_count_entire_homes: 1,
        calculated_host_listings_count_private_rooms: 1,
        calculated_host_listings_count_shared_rooms: 0,
        reviews_per_month: 0.96
    }
    ```
    **Insights**: This query can be used to understand the structure and fields of the dataset immediately. It helps in identifying which fields might require cleaning or transformation.

2. Show exactly 10 documents in any order, but "prettyprint" in easier to read format.
    ``` js
    db.listings_clean.find().limit(10).pretty()
    ```
    **Results**:
    ``` js
    {
        _id: ObjectId('6608dae4fd431e4805715fe5'),
        id: 1419,
        listing_url: 'https://www.airbnb.com/rooms/1419',
        scrape_id: 20240214201029,
        last_scraped: 2024-02-15T00:00:00.000Z,
        source: 'previous scrape',
        name: 'Beautiful home in amazing area!',
        description: "city.",
        neighborhood_overview: "(see (URL HIDDEN)",
        picture_url: 'https',
    }
    {
        _id: ObjectId('6608dae4fd431e4805715fe6'),
        id: 8077,
        listing_url: 'https://www.airbnb.com/rooms/8077',
        scrape_id: 20240214201029,
        last_scraped: 2024-02-15T00:00:00.000Z,
        source: 'previous scrape',
        name: 'Downtown Harbourfront Private Room',
        description: 'entrance.',
        picture_url: 'https://a0.muscache.com/pictures/11780344/141c2c88_original.jpg',
        host_id: 22795,
    }
    {
        _id: ObjectId('6608dae4fd431e4805715fe7'),
        id: 26654,
        listing_url: 'https://www.airbnb.com/rooms/26654',
        scrape_id: 20240214201029,
        last_scraped: 2024-02-15T00:00:00.000Z,
        source: 'city scrape',
        name: 'World Class @ CN Tower, convention centre, Theatre',
        description: "CN Tower",
        neighborhood_overview: "vibrant",
        picture_url: '.jpg',
    }
    ```
    > *Note: Only first 10 lines of each results are included, otherwise it will be too long.*

    **Insights**: The pretty-printed documents give a clearer view of the data and it also helps in finding null values or outliers that might not be immediately seen in the raw data.

3. Choose two hosts who are superhosts, and show all of the listings offered by both of the two hosts.
    ``` js
    db.listings_clean.find(
        {
            "host_id": { "$in": [1910540, 195095] },
            "host_is_superhost": true
        },
        {
            "_id": 0,
            "name": 1,
            "price": 1,
            "neighbourhood": 1,
            "host_name": 1,
            "host_is_superhost": 1
        }
    )
    ```
    **Results**:
    ``` js
    {
        name: 'Yonge & Bloor Studio Skyline',
        host_name: 'Urbano',
        host_is_superhost: true,
        price: '$126.00'
    }
    {
        name: 'Yonge & Bloor 2 Bedroom Apartment',
        host_name: 'Urbano',
        host_is_superhost: true,
        price: '$104.00'
    }
    {
        name: 'Fountain View Studio - Eaton center',
        host_name: 'Urbano',
        host_is_superhost: true,
        neighbourhood: 'Toronto, Ontario, Canada',
        price: '$125.00'
    }
    ```
    **Insights**: The results might show that these hosts as superhost have more complete and well-maintained listings.

4. Find all the unique `host_name` values.
    ``` js
    db.listings_clean.distinct("host_name")
    ```
    **Results**:
    ``` js
    [
        365,               '(Phone Number Hidden)', '1162417 Ontario Inc.',
        '6ix',             'A',                     'AMG Luxe',
        'Aaesha',          'Aahan',                 'Aaiza',
        ...
    ]
    ```
    **Insights**: The result can show the level of competition among hosts. A large number of unique host names might suggest a highly competitive market with many individual property owners.

5. Find all of the places that have more than 2 `beds` in a neighborhood of your choice, ordered by `review_scores_rating` descending.
    ``` js
    db.listings_clean.aggregate([
        { $match: { 
            "neighbourhood": "Toronto, Ontario, Canada",
            "beds": { $gt: 2 }, 
            "review_scores_rating": { $ne: null }
        }},
        { $sort: { 
            "review_scores_rating": -1
        }},
        { $project: { 
            "name": 1, 
            "beds": 1, 
            "review_scores_rating": 1, 
            "price": 1 
        }}
    ])
    ```
    **Results**:
    ``` js
    {
        _id: ObjectId('6608dae4fd431e48057160a4'),
        name: 'lovely 2 +1 bdrm home +  garage in  midtown',
        beds: 5,
        price: '$232.00',
        review_scores_rating: 5
    }
    ```
    **Insights**: Listings with more than two beds are likely suitable for families or groups. It also quickly provides guests with a list that meets their needs (>2 beds in this case).

6. Show the number of listings per host.
    ``` js
    db.listings_clean.aggregate([
        { $group: { _id: "$host_id", numberOfListings: { $sum: 1 } } }
    ])
    ```
    **Results**:
    ``` js
    {
        _id: 56278408,
        numberOfListings: 1
    }
    {
        _id: 512991042,
        numberOfListings: 1
    }
    {
        _id: 42328887,
        numberOfListings: 1
    }
    ```
    **Insights**: This query can show the presence of commercial hosts in the dataset. A small number of hosts with a large count of listings could indicate a more commercialized property rental environment, whereas more single-listing hosts suggest a community of individuals sharing their own homes.

7. Find the average `review_scores_rating` per neighborhood, and only show those that are `4` or above, sorted in descending order of rating.
    ``` js
    db.listings_clean.aggregate([
        { $group: { _id: "$neighbourhood", averageRating: { $avg: "$review_scores_rating" } } },
        { $match: { averageRating: { $gte: 4 } } },
        { $sort: { averageRating: -1 } }
    ])
    ```
    **Results**:
    ``` js
    {
        _id: 'Toronto, Etobicoke, Canada',
        averageRating: 5
    }
    {
        _id: 'Toronto, North York, Canada',
        averageRating: 5
    }
    {
        _id: 'Vaughan, Ontario, Canada',
        averageRating: 5
    }
    ```
    **Insights**: The neighborhoods with higher average review scores might be seen as more desirable locations or could be indicative of higher-quality listings within those areas. This can inform potential guests about the best places to stay and hosts about areas where they may need to improve their services to stay competitive.