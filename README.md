# EDA  and ML Project on Hotel Booking Analysis
## Objective
My major goal is to conduct EDA on the hotel booking dataset and make insightful inferences about broad hotel booking trends and how different components interact. Also to apply ML to predict possibility of booking.
## Data Set
A dataset of hotel reservations is downloaded from Kaggle. A city hotel and a resort hotel's reservations are included in this dataset. The following characteristics are present. 

```
 - hotel: Name of hotel ( City or Resort)
- is_canceled: Whether the booking is canceled or not (0 for no canceled and 1 for canceled)
- lead_time: time (in days) between booking transaction and actual arrival.
- arrival_date_year: Year of arrival
- arrival_date_month: month of arrival
- arrival_date_week_number: week number of arrival date.
- arrival_date_day_of_month: Day of month of arrival date
- stays_in_weekend_nights: No. of weekend nights spent in a hotel
- stays_in_week_nights: No. of weeknights spent in a hotel
- adults: No. of adults in single booking record.
- children: No. of children in single booking record.
- babies: No. of babies in single booking record. 
- meal: Type of meal chosen 
- country: Country of origin of customers (as mentioned by them)
- market_segment: What segment via booking was made and for what purpose.
- distribution_channel: Via which medium booking was made.
- is_repeated_guest: Whether the customer has made any booking before(0 for No and 1 for Yes)
- previous_cancellations: No. of previous canceled bookings.
- previous_bookings_not_canceled: No. of previous non-canceled bookings.
- reserved_room_type: Room type reserved by a customer.
- assigned_room_type: Room type assigned to the customer.
- booking_changes: No. of booking changes done by customers
- deposit_type: Type of deposit at the time of making a booking (No deposit/ Refundable/ No refund)
- agent: Id of agent for booking
- company: Id of the company making a booking
- days_in_waiting_list: No. of days on waiting list.
- customer_type: Type of customer(Transient, Group, etc.)
- adr: Average Daily rate.
- required_car_parking_spaces: No. of car parking asked in booking
- total_of_special_requests: total no. of special request.
- reservation_status: Whether a customer has checked out or canceled,or not showed 
- reservation_status_date: Date of making reservation status.
```
* Total number of rows in data: 119390
* Total number of columns: 32

## Data Cleaning and Feature Engineering
### (1) Removing Duplicate rows
All duplicate rows were dropped.
### (2) Handling null values
Handling null values

* Null values in columns `company` and `agent` were replaced by 0.
* Null values in column `country` were replaced by 'others'.
* Null values in column `children` were replaced by the mean of the column.

### (3) Converting columns to appropriate data types
* Changed data type of `children`, `company`, `agent` to int type.
* Changed data type of `reservation_status_date` to date type.
### (4) Removing outliers
One outlier was found in the `adr` column. Simply dropped it.
### (5) Creating new columns
* Created new column total_stay by adding `stays_in_weekend_nights`+`stays_in_week_nights`.
* Created new column `total_people` by adding `adults`+`children`+`babies`.

## Exploratory Data Analysis
Performed EDA and tried answering the following questions:

```
Q1) Which agent makes the most no. of bookings?
Q2) Which room type is in most demand and which room type generatesthe highest adr?
Q3) Which meal type is the most preffered meal of customers?
Q4) What is the percentage of bookings in each hotel?
Q5) Which is the most common channel for booking hotels?
Q6) From which country most of the guests are coming ?
Q7) How long do people stay at the hotels?
Q8) What is preferred stay length in each hotel?
Q9) Which hotel has a high chance that its customer will return for another stay?
```
Mainly performed using Matplotlib and Seaborn library and the following graph and plots had been used:

* Bar Plot.
* Scatter Plot.
* Pie Chart.
* Heatmap.
* Box Plot

## Developed ML Models:
```
1. Logistic Regression
2. K-Nearest Neighbor sClassifier
3. Decision Tree Classifier
4. Random Forest Classifier
```

## Conclusion
### EDA
```(1) Around 60% bookings are for City hotel and 40% bookings are for Resort hotel, therefore City Hotel is busier than Resort hotel. Also the overall adr of City hotel is slightly higher than Resort hotel.
(2) Mostly guests stay for less than 5 days in hotel and for longer stays Resort hotel is preferred.
(3) Both hotels have significantly higher booking cancellation rates and very few guests less than 3 % return for another booking in City hotel. 5% guests return for stay in Resort hotel.
(4) Most of the guests came from european countries, with most of guests coming from Portugal.
(5) Guests use different channels for making bookings out of which most preferred way is TA/TO.
(6) Almost 30% of bookings via TA/TO are cancelled.
and many more...
```
### ML
```
So I got an accuracy score of 97 % using the Random Forest Classifier which is highest among all models
```
## Challenges 
```
(1) A lot of the data were duplicates.
(2) Incorrect datatype format for the data was included.
(3) It was challenging to select the best visualisation techniques.
(4) The dataset contained a large number of null values.
```
