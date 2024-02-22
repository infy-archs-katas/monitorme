
# Hospital Software System Architecture

## Overview

The Hospital Software System is designed to facilitate comprehensive patient monitoring, including real-time metrics capturing and alerting. It interacts with the MonitorMe Metrics Capturing System for retrieving patient vital metrics and the MonitorMe Alerting System for receiving alerts based on real-time anomaly detection.

## High Level Architecture

![](https://github.com/infy-archs-katas/monitorme/blob/main/diagrams/C2-HospitalSystem.png)

## Component Details

| Component Name  | Component Description | Technology Choices |
| ------------- | ------------- | ------------- |
| **Administration UI Application**  | An application for hospital administrators to perform tasks such as adding patients for monitoring, assigning monitoring devices, assigning nurses to nurse stations, and mapping patients to nurse stations.  | Single Page Application using React  |
| **Database**  | Database component to store data related to patients, monitoring devices, nurses, and nurse stations.  | PostgreSQL  |
| **Nurse Station UI Application**  | UI application for nurses to monitor patient vital metrics. It utilizes React with embedded Grafana dashboards for a visual representation of vital metrics.  | React with embedded Grafana dashboards  |
| **Vitals UI Application **  | UI application for medical staff to generate consolidated patient's vital profile for a requested time period. It includes upload functionality to MyMedicalData for a given patient.  | React Single Page Application  |
| **API Component - Vitals REST Service**  | REST service for exposing vital measurements per vital type.  | Node.js  |
| **API Component - Real-Time Alerts WebSocket Service**  | WebSocket service for pushing real-time alerts to single-page clients (web clients).  | Node.js  |
| **API Component - Snapshot REST Service**  | REST service for exposing snapshotting and snapshot upload functions, with secure integration with MyMedicalData via HTTP interface.  | Node.js  |


## Architectural Characteristics

| Characteristics  | Decisions |
| ------------- | ------------- |
| **Scalability**  | Utilize a microservices architecture to allow individual components to scale independently based on demand. |
| **Data Storage**  | Use PostgreSQL for storing patient-related data due to its relational capabilities and ability to handle complex queries efficiently. |
| **Real-Time Communication**  | Implement WebSocket service for real-time alerts to ensure timely delivery to single-page clients. Node.js is chosen for its event-driven, non-blocking architecture. |
| **Polling for Vital Metrics**  | Employ polling mechanism for delivering vital metrics through REST services and Grafana dashboards at pre-defined intervals, providing a balance between real-time updates and reduced server load. |
| **UI Framework**  | Adopt React for building single-page applications, ensuring a responsive and interactive user interface. |
| **Integration with External Systems**  | Use Node.js for API components to provide REST services and integrate securely with MyMedicalData via HTTP interfaces. Pull timeseries data from a metrics software system to avoid hosting it locally. Ensure that only authorized hospital systems can pull metrics for their own patients, and nurse stations can only monitor and receive alerts for the patients they attend. |
| **Visualization**  | Embed Grafana dashboards within React applications to visualize patient vital metrics efficiently. |
| **Security**  | Implement secure communication using HTTPS for REST services, ensuring confidentiality and integrity of data during transmission. Perform access control and authentication for API endpoints. Only allow authorized hospital systems to pull metrics for their own patients, and nurse stations can only monitor and receive alerts for the patients they attend. |
| **Fault Tolerance**  | Design the system with fault tolerance mechanisms such as redundant services, load balancing, and graceful degradation to ensure continued operation in the presence of failures. |
| **Recoverability**  | Implement data backup and recovery strategies to minimize data loss in case of failures. Utilize logging and monitoring tools to detect and troubleshoot issues promptly. |
| **Deployability**  | Use containerization (e.g., Docker) for application deployment, enabling consistent and portable deployments across different environments. Implement continuous integration and delivery (CI/CD) pipelines for automated and reliable deployments. |
| **Maintainability**  | Encourage code modularity and maintainability by adopting microservices architecture and using technologies like React and Node.js with well-defined APIs. |


## Architectural Choice

- Microservices

## Deployment View
Below is the deployment view based on the architecture choice 

![](https://github.com/infy-archs-katas/monitorme/blob/main/diagrams/VMS-DeploymentView.png)

## Devops Model
Below is the devops approach following the gitops approach 

![](https://github.com/infy-archs-katas/monitorme/blob/main/diagrams/VMS-DevopsView.png)

