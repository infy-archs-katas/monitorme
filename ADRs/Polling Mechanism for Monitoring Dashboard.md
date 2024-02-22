# Polling Mechanism for Monitoring Dashboard

## Status
ACCEPTED

## Context
The Hospital Software System requires a mechanism to update and display vital metrics on monitoring dashboards. The system must strike a balance between real-time updates and server load to provide an efficient and responsive user experience.

## Decision
We choose a polling mechanism for delivering vital metrics to the monitoring dashboard of the Single Page Application (SPA). The polling approach involves periodic requests for updated data at predefined intervals, ensuring a timely display of metrics without overwhelming the server with continuous requests.

## Consequences
By employing a polling mechanism, we achieve a balance between real-time updates and reduced server load. The monitoring dashboard receives updated information at regular intervals, optimizing resource utilization and responsiveness.
