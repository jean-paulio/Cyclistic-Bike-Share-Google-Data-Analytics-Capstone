# Cyclistic Bike Share Google Data Analytics Capstone

## 🚴 Introduction
The Cyclistic Bike Share Case Study is the final capstone project for the google Data Analytics Professional Certificate. In this project, I will execute the data analysis process of Ask, Prepare, Process, Analyze, Share, and Act in order to create actionable suggestions for the company.

## 💬 Scenario
I am a junior data analyst working on the marketing analyst team at Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, my team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, my team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve our recommendations, so they must be backed up with compelling data insights and professional data visualizations. Therefore, my team and I have to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, we will design a new marketing strategy to convert casual riders into annual members.

## ⚙️ Process
### 1. Ask
**Business Task** - Understand how members and casual riders differ to design a targeted marketing strategy aimed at converting casual riders into more profitable annual members.
> Three Guiding Questions
> 1. How do annual members and casual riders use Cyclistic bikes differently?
> 2. Why would casual riders buy Cyclistic annual memberships?
> 3. How can Cyclistic use digital media to influence casual riders to become members?

### 2. Prepare
**Data Source:** [divvy-tripdata](https://divvy-tripdata.s3.amazonaws.com/index.html) <br>
[Note that the data has been made available by Motivate International Inc. under this [<ins>license</ins>](https://www.divvybikes.com/data-license-agreement).]

The data I will be analyzing will be all trips from the year **2025**.

**Tools:** <br>
- Data cleaning & processing - SQL on Google Big Query
- Data vizualization - [Tableau](https://public.tableau.com/app/profile/jean.paul.montelus/viz/2025CyclisticBikeShare/2025CyclisticBikeShare)

### 3. Process
The data was processed in 3 steps:
1) Data Combining
2) Data Cleaning
3) Data Analysis

#### Data Combining
The 12 tables from **January 2025 to December 2025** were stacked and combined into a single table. The table consists of 5,552,994 rows. 

The data set consists of 13 variables, as shown in the following: <br>

| No. | Variable | Description |
| :--- | :--- | :--- |
| 1 | `ride_id` | Unique ID assigned to each ride |
| 2 | `rideable_type` | Classic or Electric Bike |
| 3 | `started_at` | Date and time at the start of trip |
| 4 | `ended_at` | Date and time at the end of trip |
| 5 | `start_station_name` | Name of the station where the ride journey started |
| 6 | `start_station_id` | ID of the station where the ride journey started |
| 7 | `end_station_name` | Name of the station where the ride journey ended |
| 8 | `end_station_id` | ID of the station where the ride journey ended |
| 9 | `start_lat` | Latitude of starting station |
| 10 | `start_lng` | Longitude of starting station |
| 11 | `end_lat` | Latitude of ending station |
| 12 | `end_lng` | Longitude of ending station |
| 13 | `member_casual` | Membership status of each rider (Member or Non-Member) |

#### Data Cleaning
To clean the data:
- All trips with any null values were removed.
- Three columns were added:
  - ride_length_in_mins
  - day_of_week
  - month
- Trips with durations less than 1 minute or trips 24 hours or greater were removed.

In total, **3,591,248** rows were returned, meaning 1,961,746 rows were removed.

### 4. Analyze
#### Data Analysis
The cleaned data is imported into Tableau for analysis and the figures plotted are displayed in the following.

### Total Rides in 2025
<img width="2390" height="1269" alt="image" src="https://github.com/user-attachments/assets/0a64a0a1-2c34-429c-b276-bd7671e6d4a7" /> <br>
- With 2,296,802 trips, members accounted for about about **63.96%** of all trips in 2025.
- With 1,294,446 trips, casual riders accounted for about **36.04%** of all trips in 2025

#### Average Ride Length
<img width="1372" height="683" alt="image" src="https://github.com/user-attachments/assets/21e56056-d3fb-43a4-9157-a04530944a75" /> <br>
- Casual riders had an average ride length of **22.21 minutes**, which is a significant margin larger than the average ride length of members of **12.18 minutes**.

#### Ride Times (Casual vs Member)
<img width="2950" height="881" alt="image" src="https://github.com/user-attachments/assets/6d64b6ff-29d1-404c-98f4-17ab149b976c" /> <br>
- Casual riders have **one peak** time frame with the most bike rides of their group being in the evening between **3:00 to 7:00 PM**. It can be inferred this peak represents casual riders taking trips after work.
- Members have **two peaks** in the day, with the first smaller peak being in the morning between **7:00 to 9:00 AM**, and the next larger peak being between **4:00 to 7:00 PM**. It can be inferred these peaks are from commutes to work in the morning, and rides taken after work.
 
#### Monthly Average Ride Length
<img width="2562" height="1261" alt="image" src="https://github.com/user-attachments/assets/398975e6-3d2d-4fb8-b115-138929525a2e" /> <br>
- Casual riders shows a distinct seasonal peak in average ride length between March and October, especially during the summer months of June to August, with an average time of about **24 minutes**.
- Members also have their peak ride length average in the summer months of June to August at around **13 minutes**. However, members exhbit far less variance, maintaining a low standard deviation across all months.

#### Weekly Average Ride Length
<img width="2558" height="1271" alt="image" src="https://github.com/user-attachments/assets/38c2d257-7779-46f6-8462-079e2815bf37" /> <br>
- Casual riders have their longest average ride lengths on weekends at around **25 minutes**, and their lowest average on Wednesdays at an average of **18 minutes**.
- Members follow this same trend with their highest times on weekends at around **13.6 minutes** and lowest on Wednesdays at **11.56 minutes**.
  - Again, members exhibit less variance than members do, showing a more stable pattern.

#### Monthly Total Rides
<img width="2560" height="1276" alt="image" src="https://github.com/user-attachments/assets/fbe9ab3d-e236-4b31-a932-923e04ae4bcc" /> <br>
- Similar to the trend in ride length, the monthly ride count peaks in the summer months of **June to August** for casual riders.
- Members also have a **peak within summer** starting in **June**, the trend just lasts slightly longer into the month of **October**.

#### Weekly Total Rides
<img width="2560" height="1274" alt="image" src="https://github.com/user-attachments/assets/91ddfeaf-3737-424f-bf85-18bc77750678" /> <br>
- Casual riders and members have inverse riding patterns throughout the day as **members have highest activity on weekdays (Mon-Fri)** and less trips on weekends, whereas **casual riders have highest activity on weekends (Sat-Sun)**, and less activity on weekdays.

### 5. Share
<img width="2783" height="2698" alt="2025 Cyclistic Bike Share" src="https://github.com/user-attachments/assets/587e1ad2-c896-45e4-a25f-51b1bda1fe1b" /> <br>
View [Cyclistic Bike Share Dashboard](https://public.tableau.com/app/profile/jean.paul.montelus/viz/2025CyclisticBikeShare/2025CyclisticBikeShare).

#### <ins>Insights<ins>
**Similarities:**
- Summer and part of Fall is the busiest season as **May to October are the most popular months** for both members and casual riders. 
- Both have their highest number of rides in the evening with a **peak window of rides started between 4:00 and 7:00 PM**.
  - Likely a reflection of users riding after work.
- Both have **higher average ride durations in the summer months** on the monthly basis, and **higher average durations on weekends**, on the weekly basis.
- Both members and casual riders **prefer classic bikes over electric bikes**.
  
**Differences:**
- The **disparity between the number of rides** between members and casual riders **is largest** during the Winter season **from December to January**.
  - This huge dropoff for casual riders during winter supports the idea of their rides mostly being for leisure as opposed to members using rides for utility. 
- **Members have a second peak** of usage **in the morning between 7:00 - 9:00 AM**, likely a reflection of users commuting to work.
- **Members** have a **significantly shorter average ride length** of **12.41 minutes** than casual riders do with **23.82 minutes**.  
- **Members** show **consistent rides** throughout the week while **casual riders have the busiest activites on weekends and lowest activities during weekdays**.
  - This may indicate that the Cyclistic members use the bicycles for purpose-oriented rides such as work or errands while the casual riders use bicycles for leisure or recreational activities.
 
### 6. Act
#### <ins>Recommendations</ins>
From the analysis above, we can design marketing strategies to convert casual riders to Cyclistic members. Here are my suggested approach:

- **Seasonal Campaigns** <br>
  - Launch seasonal campaigns by offering limited-time discounts, special weekdays offers, or extended ride durations for members during these seasons to help.
  - With the months of May to October having higher activity from casual members, beginning these promotions in the month of April would be the prime time.
- **Membership Plan Options** <br>
  - Having the choice of 3 separate packages of an annual, 6-month, or 3-month subscription would allow users to choose membership types according to their own preferences.
  - Shorter-term membership plans will incentivise users who know they will not be using the service at all times of the year. 
- **Membership Rewards System** <br>
  - Implement a membership loyalty points system for users to collect points for each ride. Rewards such as membership discount will be given based on the number of points collected.
  - This will encourage riders to use the service more frequently, driving engagement and loyalty.
- **Membership-Exclusive Events** <br>
  - Organize member-exclusive events such as group rides, urban exploration challenges, or themed cycling events.
  - This approach will help to maintain the brand of the company with an active community providing unique experiences to members.
  - These events should also be promoted for social media engagement.

## ☑️ Conclusion
In conclusion, this analysis provides valuable insights into the preferences and behaviors of Cyclistic members and casual riders. By tailoring strategies to the identified differences and preferences, Cyclistic can effectively convert casual riders into portential members.

