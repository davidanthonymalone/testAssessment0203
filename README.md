# Restful Booker API – Performance Test Assessment


## What's Included

- `homeOfficeTestAssess.jmx` – The full JMeter test plan.
- `PerformanceTestingAssessment.pdf` – My write up explaining the approach, how I met the criteria, test types, results, and screenshots.
- `data/users.csv` – CSV file with variables for the JMeter script.
  

## What I Did

- Covered all major endpoints (Auth, Create, Get, Patch, Update, Delete bookings).
- Added correlation (e.g. token + booking ID extraction).
- Used CSV + user-defined variables for data-driven testing.
- Implemented retry logic (for example, on login failures).
- Added timers to space out requests more realistically.
- Used assertions to validate response codes and body content.

## Test Types Set Up

- **Load Test**: 50 users (this is the only test I actually ran).
- **Spike Test**: Spikes to 30 users every 10 minutes.
- **Stress Test**: Gradual ramp-up from 10 to 140 users.
- **Soak Test**: 10 users over 12 hours.

Each test has its own thread group, and I made an educated guess at the profiles since I didn’t have access to real usage data.

## Monitoring

I set up Grafana with InfluxDB to see what was going on during the test. The dashboards showed throughput, response time, errors, and active threads. With more time, I would’ve added more panels (e.g. CPU, memory).



Thanks for reading.
