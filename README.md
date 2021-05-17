# Argyle Fleet Calculator

### Demo

#### Insurance Periods by Activity ([Argyle Activities API](https://argyle.com/docs/api-reference/activities))
<img width="1608" alt="image" src="https://user-images.githubusercontent.com/22115481/118556010-926fbc00-b78d-11eb-8108-710cd9346180.png">

#### Insurance Periods by Month/Year
<img width="550" alt="image" src="https://user-images.githubusercontent.com/22115481/118556253-d82c8480-b78d-11eb-8149-978cd5f671da.png">

#### Insurance Periods by Activity Type
<img width="1526" alt="image" src="https://user-images.githubusercontent.com/22115481/118556318-eda1ae80-b78d-11eb-94cc-ab31333e4181.png">

#### Period Time Breakdown
<img width="600" alt="image" src="https://user-images.githubusercontent.com/22115481/118555222-a23ad080-b78c-11eb-9e53-ccb9ec4aa887.png">


### Overview
[This](https://github.com/Argyle-Prebuilds/fleet-calculator/blob/main/notebooks/Fleet%20Calculator.ipynb) notebook takes data from the [Argyle Activities API](https://argyle.com/docs/api-reference/activities) and delivers a breakdown of gig driver's time and distance across the following periods, for insurance purposes:

*   **P1** - Gig App is on and worker is waiting for request
*   **P2** - worker has accepted request and is going to the pickup location
*   **P3** - worker has picked up asset (food, human etc) and is going to the drop off location (P3 Ends when worker has dropped off the asset)

### Install dependencies
```bash
pip install -r requirements.txt
```

### Run Fleet Calculator notebook
```bash
cd notebooks && jupyter notebook "Fleet Calculator.ipynb"
```

Click on the **Cell** dropdown in notebook's toolbar and select **Run All** to run all cells and generate outputs.

### Configure notebook settings
The first cell lets you configure Calculator settings
```python
# Plug in your Argyle credentials
CLIENT_ID = "YOUR_ARGYLE_CLIENT_ID"
CLIENT_SECRET = "YOUR_ARGYLE_CLIENT_SECRET"

# Difference between trips can be considered as P1 Time as long as it doesn't exceed P1_MAX_TIME
P1_MAX_TIME = 60 # minutes; 60 mins by default

# Limit the list of activities received from Argyle API
ACTIVITIES_LIMIT = 50000

# Filter activities by employer(s)
EMPLOYER_FILTER = ["uber", "lyft"]
```
