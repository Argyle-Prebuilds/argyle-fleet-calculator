# Argyle Fleet Calculator

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
