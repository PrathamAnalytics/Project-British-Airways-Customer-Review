# British Airways Customer Review Analysis

# Project Overview 
This project analyzes customer reviews for British Airways (BA) to assess passenger satisfaction across various factors, including service quality, comfort, food, and entertainment. The project combines review text analysis with numerical rating insights to provide a data-driven overview of BA's customer experience.

- **Data Sources:** BA review data, country data for geographic insights.

- **Objectives:** Understand drivers of customer satisfaction and provide actionable insights for service improvement.

# Data Description 

This project leverages data from customer reviews of British Airways flights, combined with country information to analyze global perspectives on service quality. The dataset includes detailed reviews left by passengers on various aspects of their flight experience, such as comfort, food quality, and customer service. This data allows for a comprehensive exploration of factors that impact customer satisfaction, including flight route, traveler type, and regional feedback patterns.

### Data Sources
1. **Customer Review Data ([ba_reviews.csv](./ba_reviews.csv))**  
   This file contains the primary data on individual reviews, with information on:
   - **Review Details**: Text-based feedback summarizing the reviewer’s experience.
   - **Ratings**: Quantitative scores (1-5 scale) across categories such as seating comfort, in-flight entertainment, food and beverages, and ground service.
   - **Traveler Information**: Insights into traveler demographics and flight details, including traveler type (business, leisure) and seat class (economy, business).
   - **Flight Route & Aircraft Model**: Specific flight paths and the type of aircraft used, which help contextualize service quality in various scenarios.

2. **Country Data (`Countries.csv`)**  
   The country dataset enriches the analysis by linking reviews to geographical regions. This data enables segmentation of reviews based on the origin of the reviewer, facilitating an understanding of satisfaction trends by country or region. Key fields include:
   - **Country Name and Code**: Standardized country information to correlate with review origins.
   - **Continent and Region**: Classification to analyze regional trends, allowing for a breakdown of satisfaction across continents or specific regions.

### Purpose of the Data
The combination of review and country data supports a multi-dimensional analysis of British Airways' customer feedback. By correlating reviews with geographical information, we aim to reveal:
   - **Regional Service Preferences**: How satisfaction varies by traveler origin, potentially indicating regional expectations for service.
   - **Performance by Flight and Traveler Type**: Insights into how specific routes, aircraft types, and traveler categories (business vs. leisure) impact overall ratings.
   - **Category-Specific Strengths and Weaknesses**: Analysis of key service areas like cabin staff, entertainment, and food quality to identify operational improvement areas.

This dataset provides a strong foundation for both quantitative and qualitative insights into the British Airways customer experience, forming the basis for strategic recommendations on service improvements.

# British Airways Reviews Dataset
- **Columns:** `Header`, `Author`, `Date`, `Place`, `Content`, `Aircraft`, `Traveller Type`, `Seat Type`, `Route`, `Date Flown`, `Recommended`, `Trip Verified`, `Rating`, `Seat Comfort`, `Cabin Staff Service`, `Food Beverages`, `Ground Service`, `Value for Money`, `Entertainment`
- **Sample Size:** **5,000+** reviews spanning **10** countries.
- **Metrics Captured:** Ratings on seat comfort, cabin staff service, food/beverages, ground service, value for money, and entertainment.
```mermaid
%% Simplified ER Diagram for British Airways Review Analysis
erDiagram
    REVIEW {
        int review_id PK "Primary Key: Unique Review Identifier"
        string header "Review Summary Header"
        string author "Author of the Review"
        date date "Review Date"
        string place "Author's Place of Origin"
        text content "Full Review Content"
        string aircraft "Aircraft Model"
        string traveller_type "Type of Traveller"
        string seat_type "Class of Seat"
        string route "Travel Route"
        date date_flown "Flight Date"
        boolean recommended "Recommended by Reviewer (Yes/No)"
        boolean trip_verified "Trip Verification Status"
        int rating "Overall Rating (1-5)"
        int seat_comfort "Seat Comfort Rating (1-5)"
        int cabin_staff_service "Cabin Staff Service Rating (1-5)"
        int food_beverages "Food and Beverages Rating (1-5)"
        int ground_service "Ground Service Rating (1-5)"
        int value_for_money "Value for Money Rating (1-5)"
        int entertainment "Entertainment Rating (1-5)"
    }
    
    COUNTRY {
        string country_name PK "Country Name"
        string country_code "ISO Country Code"
        string continent "Continent"
        string region "Geographical Region"
    }

    REVIEW ||--|{ COUNTRY : "has_country"

```
# Executive Summary 
This analysis reveals that BA's overall satisfaction rating averages **2.5 out of 5**, with critical areas for improvement in food/beverages, entertainment, and ground service. The data shows that **90%** of reviews are negative for economy class, while business and first-class satisfaction rates are slightly better but below industry standards.

# Top Insights
**Economy Class Discontent:** **85%** of economy passengers rate food and comfort as poor.

**Business Class Complaints:** **70%** indicate service issues.

**Entertainment Lacks Appeal:** **80%** of reviewers rate entertainment poorly, citing outdated screens and limited options.

# Key Insights 

1. **Seat Comfort**
Average rating across classes is **2.1/5**, with economy class rating at **1.8/5**.
Key complaints include narrow seats and lack of legroom, particularly on **A320** aircraft.
()
2. **Cabin Staff Service**
Service in business class has an average rating of **3.0/5**, showing more positive feedback compared to economy **(2.0/5)**.
Notable feedback includes inconsistent attentiveness and long wait times.
()
3. **Food and Beverages**
Ranked among the lowest categories with an average rating of **1.9/5**.
Economy passengers describe food as "bland" and "limited in choice", while first-class passengers note better, but inconsistent quality.
()
4. **Entertainment**
Average rating of **1.7/5**, largely due to outdated or malfunctioning screens.
()
**Suggestion for British Airways:** Invest in upgraded in-flight entertainment systems to boost satisfaction.

# Technical Overview 
**Languages Used:** Python (Data Analysis), SQL (Data Manipulation)

**Tools:** Pandas, Matplotlib, Seaborn for data processing; Tableau for dashboard creation.

**Models Used:** Sentiment analysis using Natural Language Processing (NLP) for review text.

**Data Handling:** Merged BA Reviews dataset with Countries dataset for region-based analysis.

# Data Limitations 
**Sample Bias:** Predominantly negative reviews may skew data, overrepresenting dissatisfied customers.

**Geographic Imbalance:** Most reviews are from UK and US passengers, which may not reflect global sentiments.

**Limited Verification:** Only **60%** of reviews are verified, which could impact data reliability.

# Recommendations 

1. **Service Quality Improvement -**
Increase staff training for better service consistency in economy and business classes.
Target highly rated cabin crew for routes with lowest satisfaction to standardize experience.

2. **Seat and Comfort Enhancements -**
Consider investing in more comfortable seating, especially in economy class.
Prioritize upgrades on long-haul flights, where comfort ratings are particularly low.

3. **Culinary Upgrade -**
Introduce regional food choices, especially on international routes.
Explore partnerships with gourmet brands to elevate in-flight food options.

4. **Enhanced In-Flight Entertainment -**
Modernize entertainment systems by installing high-definition screens with updated libraries.
Implement additional media and gaming options to cater to a wider audience.

# Conclusion 

In summary, BA's services have significant room for improvement, with immediate action recommended on economy seating comfort, food quality, and entertainment offerings. Addressing these factors could greatly enhance customer satisfaction and retain passenger loyalty.

---
