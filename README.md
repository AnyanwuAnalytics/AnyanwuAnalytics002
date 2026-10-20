Data source: Kaggle (https://www.kaggle.com/datasets/prasad22/healthcare-dataset)

DATA STORY

This dataset belongs to the healthcare industry. The hospital's "products" are treatments, like asthma care or cancer treatment, and its "customers" are patients who arrive in very different states of urgency. Each row is one admission, so the same patient name can appear more than once. The data covers 8 May 2019 to 7 May 2024, which is exactly five years, so 2019 and 2024 are part years. It has 6 medical conditions (Arthritis, Diabetes, Hypertension, Obesity, Cancer and Asthma), 3 admission types (Elective, Urgent and Emergency), patients aged 13 to 89, and stays of 1 to 30 days. 

DATA CLEANING PROCESS

I kept an untouched copy of the raw data on a sheet called "Before" and cleaned a copy of it. I started with 55,500 rows and ended with 54,860.
1. I fixed the capital letters in 55,467 patient names (names like "LesLie TErRy" became "Leslie Terry").
2. I found and removed 534 rows that were duplicate values.
3. I found 108 negative bills (down to -$2,008). After removing the duplicates, 106 were left, and I removed them because a bill can't be negative.
4. I checked for empty cells and found none.
5. I appended two columns: Length of Stay (discharge date minus admission date) and Cost per Day (billing amount divided by length of stay).
6. I grouped ages into 10-year brackets, grouped stays into 3-day bands, and pulled the month and year from the admission date.
There are 17 columns in this dataset: 15 that came with the original data and two I appended. - Name, Age, Gender, Blood Type, Medical Condition, Date of Admission, Discharge Date, Admission Type, Room Number, Doctor, Hospital, Insurance Provider, Billing Amount, Medication, Test Results, Length of Stay, and Cost per Day.

PRE ANALYSIS BOARD

Before touching the data, I built a board to plan the analysis. 
I split the data into: 

 Independent variables (what I group or filter by): Name, Age, Gender, Blood Type, Medical Condition, Date of Admission, Doctor, Hospital, Insurance Provider, Room Number and Admission Type. 
 
Dependent variables (what I measure or what comes out): Billing Amount, Discharge Date, Medication, Test Results, Length of Stay and Cost per Day. 

Industry type 

Healthcare administration and services. It is a service business where care has to be accurate, fast and fairly billed. 
Who the stakeholders are and what they want:

•	Patients want accurate test results and a short stay. 

•	Doctors and hospitals want good outcomes and efficient care.

•	Insurance providers (Blue Cross, Medicare, Aetna, Cigna and UnitedHealthcare) watch billing and admission type to manage their risk.

•	Hospital administrators watch cost per day and room availability to keep the hospital running.

What success means to the industry: 

For the healthcare industry, success means patients get clear test results, recover and leave at a sensible pace so beds stay free, and are billed fairly for the care they receive, whether it is Emergency or Elective.

IN ANALYSIS

Each of the eight planned analyses became a PivotTable, then a chart. From each chart I wrote an observation (what the numbers show) and an insight (what it means). 




1. Yearly stay trend represented with a line chart
   <img width="896" height="327" alt="image" src="https://github.com/user-attachments/assets/3f9986a0-2276-4e96-8823-1ee1fe657624" />

 
Observation: the average stay is 15.60 days in 2019, 15.55 in 2020, 15.45 in 2021, 15.35 in 2022, 15.49 in 2023 and 15.75 in 2024. The lowest year is 2022 and the highest is 2024.

Insight: the average stay is very steady. The gap between the lowest and highest year is only 0.4 days, while individual stays range from 1 to 30 days. Also, 2019 and 2024 are part years, so they aren't a fair comparison with the full years.

2. Monthly billing trend represented with a line chart
   <img width="937" height="450" alt="image" src="https://github.com/user-attachments/assets/e0ba0c90-d424-44d1-9115-8d1a1f09af73" />

 
Observation: August is the top month with $121.58M, followed by July ($121.43M) and June ($120.49M). February is the lowest with $106.71M.

Insight: July is only $155K behind August, so I wouldn't call either one a clear peak. February looks low mostly because it has the fewest days. Adjusted per day, June is the best month ($803K a day) and May is the lowest ($744K a day), and February's gap to July shrinks from about 12% to about 4%. I can't see a seasonal surge in this data. This chart also adds up all five years, so each month shows five years combined.

3. Average billing by condition represented with bar chart
   <img width="772" height="450" alt="image" src="https://github.com/user-attachments/assets/5ef18f92-135d-43b1-9bb9-01e73bef3ce3" />

 

Observation: Obesity has the highest average bill at $25,859, then Diabetes ($25,714), Asthma ($25,685), Hypertension ($25,560), Arthritis ($25,543) and Cancer ($25,206).

Insight: only $653 (2.6%) separates the highest from the lowest, so the conditions are priced almost the same. Diabetes has the highest total billing ($236.5M), so "highest average" and "highest total" give different winners. Every condition brings in between 16.4% and 16.8% of the money, so the hospital doesn't depend on any one condition.







4. Test results, ages 13 to 32 represented with donut chart
   <img width="644" height="393" alt="image" src="https://github.com/user-attachments/assets/a05b79c7-bd65-4f5f-92a6-a054167fed4a" />


 
Observation: 34.20% of results are Normal, 33.15% are Abnormal and 32.64% are Inconclusive. 

Insight: the results split almost exactly into thirds. But all ages together also split into thirds (33.36%, 33.54% and 33.10%), so younger patients are not more uncertain. Their Inconclusive rate is actually a little lower than the whole hospital's.


5. Billing by age bracket represented with area chart
   <img width="854" height="450" alt="image" src="https://github.com/user-attachments/assets/f394f5ec-c3a0-4a05-b504-5f7cbc77361f" />

 
Observation: the 53-62 bracket bills the most ($212.1M). The middle brackets (23 to 82) bill between $202M and $212M each. The two edge brackets are smaller: 13-22 bills $103.8M and 83-92 bills $61.0M, which together make up 11.7% of billing.

Insight: the brackets differ in how many patients they have, not in how much each patient is billed. The average bill is about the same in every bracket ($25.4K to $25.9K). The edge brackets are smaller because they have fewer patients: 97% of the 13-22 bracket is aged 18 to 22, and very few patients are aged 86 to 89.

6. Test results by condition represented with clustered column chart
   <img width="772" height="450" alt="image" src="https://github.com/user-attachments/assets/9779a1a7-8742-4981-80a7-5b5bfc716f41" />

 

Observation: Asthma has the highest Normal rate (34.30%). Hypertension has the highest Inconclusive rate (33.51%). Arthritis has the highest Abnormal rate (34.25%).

Insight: every number is within about 1.5 points of a third, so these differences are small and could easily be chance. The test results do not tell me which condition is harder to diagnose, and the data has no confirmed diagnosis to compare them with, so I can't call this "accuracy". 




7. Length of stay vs cost per day represented with horizontal bar chart
   <img width="772" height="450" alt="image" src="https://github.com/user-attachments/assets/ea8be901-e23b-4a48-8a22-3755b5f4db74" />

 
Observation: cost per day is $15,531 for 1-3 day stays, $5,307 for 4-6 days, $3,269 for 7-9 days, $2,321 for 10-12 days and $877 for 28-30 days. That is a 94% drop.

Insight: this looks like early days are very expensive, but it isn't true. The average bill is about the same for every stay length ($25.4K to $25.9K), so cost per day falls only because the same bill is divided by more days. A one-day stay averages $25,346 per day and a 30-day stay averages $851 per day, and the bill is the same either way.

8. Top 5 doctors by cost per day represented with treemap chart
   <img width="761" height="357" alt="image" src="https://github.com/user-attachments/assets/e78b64c7-6826-4563-af05-29f63b4637d4" />

 
Observation: Omar Cruz ($50,654), David Cuevas ($50,651), John Walters ($50,615), Donna Fernandez ($50,527) and Jennifer Stark ($50,445).

Insight: these five doctors treated only 7 admissions in total, and every one was a 1-day stay billed at about $50K. That's a handful of cases, not a pattern. There are over 40,000 doctor names in the data and 77% of them have a single admission, so any ranking by cost per day will be topped by one-day stays with big bills.

POST ANALYSIS

After building the dashboard, three cards sit at the top: Total Billing ($1.404 Billion), Highest Average Billing by condition (Obesity) and Peak Billing Month (August). Seven of the eight charts sit underneath, and I introduced 2 slicers so anyone can filter by condition and month.

What the dashboard says:
1. The bill doesn't move with the stay, so cost per day is just division. The link between the size of a bill and the length of stay is zero (-0.005). The stays are spread evenly from 1 to 30 days, so about 10% of all admissions are 1 to 3 days and about 10% are 28 to 30 days. Because the bill stays at about $25.6K, cost per day falls as the stay gets longer ($15,531 for 1 to 3 days down to $877 for 28 to 30 days). That is a 94% drop caused by dividing the same bill by more days. The same trap shows up in the overall average. If you average the cost per day column, you get $3,399, but the middle admission has a cost per day of $1,653. Short stays with big cost per day numbers pull the average up. Across all 850,265 patient days in the data, the hospital billed $1,651 a day.
   
2. Monthly billing follows the number of admissions, not the size of the bill. The average bill is almost the same every month, between $25,283 and $26,064. What changes is how many patients come in. August has the most admissions (4,777), then July (4,762), and February has the fewest (4,199). But February also has the fewest days, and when I count admissions per day, every month sits between 29.3 and 30.9. The summer months (June, July and August) are the busiest by a small margin, about 31 a day against 29 or 30 in other months. So August is the top billing month because it has slightly more admissions and more days, not because patients are billed more. February's low number is mostly a short-month effect.
   
3. Conditions are nearly identical on every measure. Each condition has about 9,100 admissions (between 9,077 and 9,207). Average stays are 15.4 to 15.7 days and average bills are $25,206 to $25,859. Total billing differs by only 2.9% between the top condition (Diabetes) and the bottom one (Cancer), and each condition brings in between 16.4% and 16.8% of the money. Obesity wins on average bill and Diabetes wins on total. No condition is a big money maker or a big cost problem.
   
4. The age chart is a picture of patient numbers. The 13-22 and 83-92 brackets are small because they have fewer patients, 4,041 and 2,388 against about 8,000 in the middle brackets. The average bill is the same in every bracket ($25.4K to $25.9K), and the link between age and bill is zero (-0.003). So adults don’t bring in more per patient; there are just more adult patients.
   
5. Test results split into thirds everywhere. About 33.4% of results are Normal, 33.5% Abnormal and 33.1% Inconclusive for the whole hospital. The same thirds show up in every age group, every condition (Normal rates between 32.5% and 34.3%), every admission type (Inconclusive between 32.8% and 33.3%) and every stay length (between 33.1% and 33.6%). Inconclusive results don't cluster anywhere. That means they can't explain longer stays or higher costs.
   
6. The doctor ranking is built on almost nothing. The top five doctors by cost per day treated 7 admissions in total, all 1-day stays billed at about $50K, out of 54,860 admissions. The data has 40,276 different doctor names and 77% of them appear only once. A ranking that puts a one-admission doctor first is telling us about one bill, not about the doctor.

OVERALL RECOMMENDATION

Based on what the data shows, here is what I would suggest to each group.

For hospital administrators,

•	They should track the total bill per stay, not just cost per day. The bill is about the same whether a patient stays 2 days or 30, so cost per day only falls because it is divided by more days. A cost target built on cost per day would point you at the wrong problem.

•	They should plan staffing and beds using admissions per day, not monthly billing. August is the top month, but July is only $155K behind it, and admissions stay at about 30 a day in every month. This data shows no clear busy season.

•	They should set a minimum number of admissions (for example 5) before ranking doctors on cost per day. The top five doctors treated only 7 admissions in total. For doctors and clinical leaders

•	They should look at why about 1 in 3 test results is Inconclusive, and track how these leads to re-testing and longer stays. Hypertension has the highest Inconclusive rate (33.51%), so it is a place to start.

•	They should treat the difference between conditions with care. Every condition is within about 1.5 points of a third, so I would not change any testing process based on this alone.


For insurance providers,

•	They should ask for itemized claims before reviewing rates. Bills are almost the same across conditions (within 2.6%), age groups, admission types and lengths of stay, so the bill does not seem to reflect how much care a patient received.

For the finance team,

•	They should record the cost of care as well as the bill. With billing alone, nobody can say what a stay costs the hospital or whether it is financially healthy. 

CONCLUSION 

This analysis of 54,860 hospital admissions shows that a patient's bill stays at about $25.6K no matter how long they stay, that all six conditions bill within 2.6% of each other, that about a third of test results are Inconclusive for every age group and condition, and that doctor rankings built on one or two patients tell us very little. The data looks computer-generated and holds five years of billing with no cost or outcome information, so these patterns may not hold in a real hospital. Cleaning the data before analyzing it mattered, because removing 534 duplicates and 106 negative bills moved the peak month from July to August.


