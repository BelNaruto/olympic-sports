# Olympic Sports API

The **Olympic Sports API** provides comprehensive access to data from the Olympic Games, including real-time updates, athlete statistics, event information, and historical records. Ideal for developers, sports analysts, and Olympic enthusiasts, this API delivers detailed insights into various Olympic sports and events, enabling robust integration into applications and services. This API can be found [here](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/olympic-sports-api)

## Key Features

- **Live Event Data**: Access real-time updates during Olympic events, including scores, medals, and athlete performance.
- **Athlete Statistics**: Retrieve detailed profiles and statistics for Olympic athletes, including performance metrics and historical achievements.
- **Event Information**: Get information on Olympic events, including schedules, locations, and results.
- **Medal Counts**: Track medal counts by country, sport, and event.
- **Historical Data**: Access past Olympic results, records, and athlete statistics for comprehensive analysis.

## Getting Started

1. **Sign Up**: Create an account on RapidAPI.
2. **Subscribe**: Choose a subscription plan that fits your needs.
3. **API Key**: Obtain your unique API key to start making requests.
4. **Documentation**: For detailed usage instructions, visit the [Olympic Sports API Documentation](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/olympic-sports-api).


## Route: `GET /countryIds`

This route handles GET requests to retrieve a list of country IDs.

### Request
- **Method:** `GET`
- **URL:** `/countryIds`

### Response
- **Status Code:** `200 OK`
- **Content-Type:** `application/json`
- **Body:**
    ```json
    {
        "countryIds": [/* Array of country IDs */]
    }
    ```

### Example Usage
```javascript
fetch('/countryIds')
    .then(response => response.json())
    .then(data => console.log(data));
```

## Route: `GET /medals/athletes`

This route handles GET requests to retrieve medal data for athletes, filtered by year and paginated by page number.

### Request
- **Method:** `GET`
- **URL:** `/medals/athletes`
- **Query Parameters:**
  - `year` (optional, default: `'2012'`): The year for which the medal data is requested.
  - `page` (optional, default: `'1'`): The page number for pagination.

### Response
- **Status Code:** `200 OK` (on success), `400 Bad Request` (on missing query parameters), `500 Internal Server Error` (on server error)
- **Content-Type:** `application/json`
- **Body:**
  - On success:
    ```json
    {
        /* Medal data based on the specified year and page */
    }
    ```
  - On error:
    - Missing year or page:
      ```json
      {
          "message": "Please provide the year"
      }
      ```
      or
      ```json
      {
          "message": "Please provide the page number"
      }
      ```
    - Server error:
      ```json
      {
          "message": "Something went wrong please try again later!"
      }
      ```

### Example Usage
```javascript
fetch('/medals/athletes?year=2020&page=2')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));
```

## Route: `GET /medals/countries`

This route handles GET requests to retrieve medal data by countries for a specified year.

### Request
- **Method:** `GET`
- **URL:** `/medals/countries`
- **Query Parameters:**
  - `year` (optional, default: `'2012'`): The year for which the medal data is requested.

### Response
- **Status Code:** `200 OK` (on success), `400 Bad Request` (on missing query parameter), `500 Internal Server Error` (on server error)
- **Content-Type:** `application/json`
- **Body:**
  - On success:
    ```json
    {
        /* Medal data by countries based on the specified year */
    }
    ```
  - On error:
    - Missing year:
      ```json
      {
          "message": "Please provide the year"
      }
      ```
    - Server error:
      ```json
      {
          "message": "Something went wrong please try again later!"
      }
      ```

### Example Usage
```javascript
fetch('/medals/countries?year=2020')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error('Error:',
```

## Route: `GET /medals/bycountry`

This route handles GET requests to retrieve medal data for a specific country based on the year and country ID.

### Request
- **Method:** `GET`
- **URL:** `/medals/bycountry`
- **Query Parameters:**
  - `year` (optional, default: `'2012'`): The year for which the medal data is requested.
  - `countryId` (optional, default: `'5'`): The ID of the country for which the medal data is requested.

### Response
- **Status Code:** `200 OK` (on success), `400 Bad Request` (on missing query parameters), `500 Internal Server Error` (on server error)
- **Content-Type:** `application/json`
- **Body:**
  - On success:
    ```json
    {
        /* Medal data for the specified country and year */
    }
    ```
  - On error:
    - Missing year:
      ```json
      {
          "message": "Please provide the year"
      }
      ```
    - Missing countryId:
      ```json
      {
          "message": "Please provide the countryId"
      }
      ```
    - Server error:
      ```json
      {
          "message": "Something went wrong please try again later!"
      }
      ```

### Example Usage
```javascript
fetch('/medals/bycountry?year=2020&countryId=10')
   
```

## Route: `GET /sports`

This route handles GET requests to retrieve the available sports for a specified year.

### Request
- **Method:** `GET`
- **URL:** `/sports`
- **Query Parameters:**
  - `year` (optional, default: `'2024'`): The year for which the available sports data is requested.

### Response
- **Status Code:** `200 OK` (on success), `400 Bad Request` (on missing query parameter), `500 Internal Server Error` (on server error)
- **Content-Type:** `application/json`
- **Body:**
  - On success:
    ```json
    {
        /* Available sports data based on the specified year */
    }
    ```
  - On error:
    - Missing year:
      ```json
      {
          "message": "Please provide the year"
      }
      ```
    - Server error:
      ```json
      {
          "message": "Something went wrong please try again later!"
      }
      ```
## Route: `GET /athletes`

This route handles GET requests to retrieve a list of athletes for a specified year, with pagination support.

### Request
- **Method:** `GET`
- **URL:** `/athletes`
- **Query Parameters:**
  - `year` (optional, default: `'2024'`): The year for which the athlete data is requested.
  - `page` (optional, default: `'1'`): The page number for pagination.

### Response
- **Status Code:** `200 OK` (on success), `400 Bad Request` (on missing query parameters), `500 Internal Server Error` (on server error)
- **Content-Type:** `application/json`
- **Body:**
  - On success:
    ```json
    {
        /* Athlete data based on the specified year and page */
    }
    ```
  - On error:
    - Missing year:
      ```json
      {
          "message": "Please provide the year"
      }
      ```
    - Missing page:
      ```json
      {
          "message": "Please provide the page"
      }
      ```
    - Server error:
      ```json
      {
          "message": "Something went wrong please try again later!"
      }
      ```


## Route: `GET /results`

This route handles GET requests to retrieve event results for a specified year.

### Request
- **Method:** `GET`
- **URL:** `/results`
- **Query Parameters:**
  - `year` (optional, default: `'2024'`): The year for which the event results are requested.

### Response
- **Status Code:** `200 OK` (on success), `400 Bad Request` (on missing query parameter), `500 Internal Server Error` (on server error)
- **Content-Type:** `application/json`
- **Body:**
  - On success:
    ```json
    {
        /* Event results data based on the specified year */
    }
    ```
  - On error:
    - Missing year:
      ```json
      {
          "message": "Please provide the year"
      }
      ```
    - Server error:
      ```json
      {
          "message": "Something went wrong please try again later!"
      }
      ```

## Route: `GET /results/sports`

This route handles GET requests to retrieve event results for a specific sport and year.

### Request
- **Method:** `GET`
- **URL:** `/results/sports`
- **Query Parameters:**
  - `year` (optional, default: `'2024'`): The year for which the event results are requested.
  - `sportId` (optional, default: `'2'`): The ID of the sport for which the event results are requested.

### Response
- **Status Code:** `200 OK` (on success), `400 Bad Request` (on missing query parameters), `500 Internal Server Error` (on server error)
- **Content-Type:** `application/json`
- **Body:**
  - On success:
    ```json
    {
        /* Event results data for the specified sport and year */
    }
    ```
  - On error:
    - Missing year:
      ```json
      {
          "message": "Please provide the year"
      }
      ```
    - Missing sportId:
      ```json
      {
          "message": "Please provide the sportId"
      }
      ```
    - Server error:
      ```json
      {
          "message": "Something went wrong please try again later!"
      }
      ```

## Route: `GET /schedule/all`

This route handles GET requests to retrieve schedule data for a specified year, and optionally for a specific month and day.

### Request
- **Method:** `GET`
- **URL:** `/schedule/all`
- **Query Parameters:**
  - `year` (optional, default: `'2016'`): The year for which the schedule data is requested.
  - `month` (optional): The month for which the schedule data is requested.
  - `day` (optional): The day for which the schedule data is requested.

### Response
- **Status Code:** `200 OK` (on success), `400 Bad Request` (on missing query parameter), `500 Internal Server Error` (on server error)
- **Content-Type:** `application/json`
- **Body:**
  - On success:
    ```json
    {
        /* Schedule data based on the specified year, month, and day */
    }
    ```
  - On error:
    - Missing year:
      ```json
      {
          "message": "Please provide the year"
      }
      ```
    - Server error:
      ```json
      {
          "error": "Something went wrong please try again later!"
      }
      ```
## Route: `GET /schedule/sport`

This route handles GET requests to retrieve the schedule data for a specific sport and year.

### Request
- **Method:** `GET`
- **URL:** `/schedule/sport`
- **Query Parameters:**
  - `year` (optional, default: `'2016'`): The year for which the schedule data is requested.
  - `sportId` (optional, default: `'2'`): The ID of the sport for which the schedule data is requested.

### Response
- **Status Code:** `200 OK` (on success), `400 Bad Request` (on missing query parameters), `500 Internal Server Error` (on server error)
- **Content-Type:** `application/json`
- **Body:**
  - On success:
    ```json
    {
        /* Schedule data based on the specified year and sport */
    }
    ```
  - On error:
    - Missing year:
      ```json
      {
          "message": "Please provide the year"
      }
      ```
    - Missing sportId:
      ```json
      {
          "message": "Please provide the sportId"
      }
      ```
    - Server error:
      ```json
      {
          "error": "Something went wrong please try again later!"
      }
      ```

## Route: `GET /news`

This route handles GET requests to retrieve news articles, with pagination support.

### Request
- **Method:** `GET`
- **URL:** `/news`
- **Query Parameters:**
  - `page` (optional, default: `'1'`): The page number for pagination.
  - `perPage` (optional, default: `'20'`): The number of news articles per page.

### Response
- **Status Code:** `200 OK` (on success), `400 Bad Request` (on missing query parameters), `500 Internal Server Error` (on server error)
- **Content-Type:** `application/json`
- **Body:**
  - On success:
    ```json
    {
        /* News articles data based on the specified page and perPage */
    }
    ```
  - On error:
    - Missing page:
      ```json
      {
          "message": "Please provide the page"
      }
      ```
    - Missing perPage:
      ```json
      {
          "message": "Please provide the perPage"
      }
      ```
    - Server error:
      ```json
      {
          "error": "Something went wrong please try again later!"
      }
      ```





## Commonly Asked Questions

### 1. What kind of data can I access through the Olympic Sports API?
You can access live event data, athlete statistics, event information, medal counts, and historical data.

### 2. How do I authenticate my API requests?
You need to include your API key in the headers of your requests as specified in the API documentation.

### 3. Are there usage limits for the API?
Yes, usage limits depend on the subscription plan you select. Check the RapidAPI dashboard for details.

### 4. Can I filter data by specific sports, events, or athletes?
Yes, the API allows filtering to retrieve data for specific sports, events, or athletes.

### 5. Is historical data available for past Olympic Games?
Yes, the Olympic Sports API includes historical data for past Olympic Games, allowing for detailed analysis and comparisons.

### 6. How frequently is the data updated?
The data is updated in real-time during live events and periodically for historical data and schedules.

### 7. Can I access data for both Summer and Winter Olympics?
Yes, the API provides data for both Summer and Winter Olympic Games, covering a wide range of sports and events.

### 8. What formats does the API support for data responses?
The API supports data responses in JSON format, making it easy to integrate into various applications.

### 9. Are there specific endpoints for different types of data (e.g., scores, athlete stats)?
Yes, the API includes specific endpoints for various types of data, such as event scores, athlete statistics, and medal counts.

### 10. How can I stay updated on changes to the API?
You can stay informed about updates and changes by checking the API documentation and RapidAPI dashboard regularly.

For more information and to start using the Olympic Sports API, visit [Olympic Sports API on RapidAPI](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/olympic-sports-api).
