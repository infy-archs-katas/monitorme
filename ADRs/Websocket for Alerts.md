# WebSocket-Based Real-Time Alerts to Nurse Station SPA Client

## Status
ACCEPTED

## Context
The Hospital Software System requires a mechanism to deliver real-time alerts to nurse stations, ensuring timely awareness of critical events. Traditional polling mechanisms may introduce latency, impacting the responsiveness of alert delivery to nurse stations.

## Decision
We opt for a WebSocket-based approach to deliver real-time alerts to the Nurse Station Single Page Application (SPA) clients. This decision leverages the WebSocket protocol's bidirectional communication, enabling instant push notifications to nurse stations upon the detection of anomalies or critical events.Timely delivery of alert remains essential part of patient monitoring

## Consequences
The use of WebSocket-based real-time alerts reduces latency and ensures that nurse stations receive critical information promptly. This decision aligns with the need for timely responsiveness in the context of patient monitoring.
