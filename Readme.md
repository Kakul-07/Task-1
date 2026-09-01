Kakul Rajput
Student No. - 2511029
Domain - ML

Task - 1  Exploratory Data Analysis (EDA): Accident Dataset
. This task is perform EDA on Accident Dataset, clean all incosistencies, identify patterns and derive meaningful insights

 Dataset Overview :  202000 Rows
                     48 Columns.

**Column Names** :
       ['accident_id', 'accident_datetime', 'state', 'district', 'area_type',
       'latitude', 'longitude', 'road_type', 'road_condition', 'road_lighting',
       'number_of_lanes', 'speed_limit_kmph', 'estimated_speed_kmph',
       'junction_type', 'traffic_signal_present', 'median_present',
       'weather_condition', 'visibility_km', 'temperature_c', 'rainfall_mm',
       'driver_age', 'driver_gender', 'driving_experience_years',
       'license_status', 'alcohol_involved', 'distraction_involved',
       'mobile_phone_used', 'fatigue_involved', 'helmet_seatbelt_used',
       'vehicle_type', 'vehicle_age_years', 'vehicle_brand', 'vehicle_model',
       'vehicle_condition', 'overloading_status', 'primary_cause',
       'secondary_cause', 'emergency_services_called', 'ambulance_called',
       'police_called', 'response_time_minutes', 'hospitalization_required',
       'num_vehicles', 'num_injuries', 'num_fatalities', 'accident_severity',
       'insurance_claim_filed', 'insurance_claim_amount']

       **Added Columns**:
       ['year', 'month', 'day']


**Missing Values** :
secondary_cause             139075
insurance_claim_amount      110904
response_time_minutes       105773
vehicle_model                43941
vehicle_brand                38666
driver_age                   28244
vehicle_age_years            28244
driving_experience_years     28244
visibility_km                12121
speed_limit_kmph             10112
overloading_status           10109
temperature_c                10097
latitude                      9978
longitude                     9978
number_of_lanes               8086
hospitalization_required      8072
median_present                8069
traffic_signal_present        8063
junction_type                 6065
road_lighting                 6064
district                      6062
driver_gender                 6058
weather_condition             4038                            


**Missing Values**:
secondary_cause             68.849010
insurance_claim_amount      54.902970
response_time_minutes       52.362871
vehicle_model               21.752970
vehicle_brand               19.141584
vehicle_age_years           13.982178
driver_age                  13.982178
driving_experience_years    13.982178
visibility_km                6.000495
speed_limit_kmph             5.005941
overloading_status           5.004455
temperature_c                4.998515
latitude                     4.939604
longitude                    4.939604
number_of_lanes              4.002970
hospitalization_required     3.996040
median_present               3.994554
traffic_signal_present       3.991584
junction_type                3.002475
road_lighting                3.001980
district                     3.000990
driver_gender                2.999010
weather_condition            1.999010



**Duplicates** :  980 duplicate rows


. `num_fatalities` contains negative values, including `-1`. Negative fatalities are logically impossible.

. `Outlier Analysis`
   The IQR method was used to identify potential numerical outliers:
    Q1 = first quartile
    Q3 = third quartile
    IQR = Q3 − Q1 
    Lower bound = Q1 − 1.5 × IQR 
    Upper bound = Q3 + 1.5 × IQR

** DATASET TRENDS**

  .`Accident severity`
  The dataset is dominated by Minor accidents, followed by Moderate, Severe and Fatal accidents.

  .`Estimated speed and severity`
  Average estimated speed increases with accident severity.

  .`Injuries and severity`
  Severe accidents have substantially more injuries on average than Minor accident.

  .`Alcohol Involvement`
   Fatal percentage:
     Alcohol = No -- 2.57%
     Alcohol = Yes -- 12.32%

     Alcohol-involved accidents shows a larger share of fatal outcomes .

   .`Road condition`
     Non-dry road conditions show higher fatal proportions than dry roads.

   .`Weather`
     Clear weather has a lower severe/fatal distribution than foggy, rainy and stormy conditions.

   .`Area type`
    Urban areas have more accident records overall, but rural and semi-urban areas have higher fatal proportions.    

   .`Vehicle type`  
     Two-wheelers are the largest vehicle category followed by cars and trucks

   .`Emergency services`
    Accidents where emergency services were called show a much higher proportion of severe and fatal outcomes than records where they were not called  

   .`Hospitalization`
     Accidents requiring hospitalization contain a much higher proportion of severe and fatal cases than accidents not requiring hospitalization.


   .`speed_violation`
      ```python
           df["speed_violation"] = (df["estimated_speed_kmph"] > df["speed_limit_kmph"])```

           This converts the comparison between estimated speed and legal speed into a Boolean feature.




`Important Inconsistencies`:
  .duplicate rows
  .Repeated accident IDs
  .Missing values
  .Inconsistent capitalization/spacing
  .Different representations of Yes/No
  .`rain` and `rainy` representing the same weather category
  .Negative fatalities
  .Unusual driver ages
  .Suspicious geographic coordinates
  .Conditional missingness in emergency-response
  .Speed above the speed limit



`Meaningful Insights`:
   .Minor accidents dominate the dataset
   .Higher estimated speed is associated with higher accident severity
   .Alcohol-involved accidents have a much higher fatal proportion than non-alcohol-involved accidents.
   .Adverse weather conditions are associated with higher severe/fatal proportions.
   .Non-dry road conditions show higher fatal proportions than dry roads.
   .Rural and semi-urban accidents have higher severe/fatal proportions than urban accidents.
   .Two-wheelers are the largest vehicle group, making them an important group for further analysis.
   .Weather, drunk driving, poor road condition, distracted driving and overspeeding are among the most frequent recoded  cause
   .Severe accidents have substantially more injuries on average.
   .Emergency-service and hospitalization variables strongly reflect accident severity.
   .Speed violations are common and should be considered as a meaningful derived feature.