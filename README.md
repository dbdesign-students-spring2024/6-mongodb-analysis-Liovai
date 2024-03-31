# AirBnB MongoDB Analysis

## Dataset Details

### Origin of the Dataset
 The dataset used for this analysis comprises Airbnb listings for Toronto, Ontario, Canada. It is publicly available from [Inside Airbnb](http://insideairbnb.com/get-the-data/).

### Data Format
The original data file was in a compressed CSV format (`.csv.gz`); and it can be unzipped to a CSV file.

### Sample of Raw Data
Below is a table showing the first 20 rows from the original data file:

| id | listing_url | name | host_id | host_url | host_name | neighbourhood | price | number_of_reviews | last_review |
|----|-------------|------|---------|----------|-----------|---------------|-------|-------------------|-------------|
|1419| URL1        | Name1| 12345   | URLH1    | Alice     | Neighborhood1 | $100  | 200               | 2020-01-01  |
| 2  | URL2        | Name2| 67890   | URLH2    | Bob       | Neighborhood2 | $150  | 150               | 2020-01-02  |
| ... | ...        | ...  | ...     | ...      | ...       | ...           | ...   | ...               | ...         |
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