# Data-Questers-CANDEV2022

# Challenge
Shared Services Canada (SSC) manages and supports IT infrastructure for 43 departments. One of our key metrics includes a customer satisfaction survey which identifies how departments feel SSC is providing service. Another key metric is the length of time it takes SSC to resolve incidents.

SSC’s main Information Technology Service Management (ITSM) tool currently is a tool called Enterprise Control Desk. This tool is used to track the life of service requests, incidents, problems, changes and configuration items. One area of concern is how long it takes for an incident to go from being opened to closed.

Overall, the majority of time we are meeting our targets but in many cases incidents may bounce around the organization resulting in a longer period of time before SSC resolves a ticket. Knowing when a ticket may be misassigned or open for a long period of time would help SSC improve our service delivery to our partners. Using the information provided will help improve our process to properly define which support team needs to be engaged. Additionally, defining the time between when an incident occurs and when SSC actively starts working on an incident would be another indicator to help SSC improve our processes.

Some metrics and questions we have of the data include:

- Average time that incidents spend in a particular status.
- Average time that incidents spend with a particular Support group (Assigned_Group).
- Mean time to restore service (MTRS), are there particular services that are taking longer on average to be restored?
- Are there particular organizations for whom it takes longer on average to restore services?
- Number of times an incident is reassigned during the life of the ticket.
- Is there a correlation between the number of times an incident is reassigned and how long it takes to restore?
- Is there a correlation to certain groups where tickets stay in a particular status that is resulting in longer times to restore service?
- Is there a correlation to certain services where tickets are not resolved as quickly as other services leading to greater MTRS?
- There are many Event Management tickets. What is the difference in incidents ticket including and excluding Event Management tickets?

Note: The metrics and questions have been reordered.
Note: The original data used for this challenge is not posted in this repository.

# Files
- AVGDATA directory: contains all the csv outputs for ALL data
- AVGDATA_JEM: contains all the csv outputs for JUST EVENT MANAGEMENT tickets
- AVGDATA_EEM: contains all the csv outputs for EXCLUDING EVENT MANAGEMENT tickets
- basic_statistics.ipynb: contains code that answers all the average time questions. Also compares just, excluding, and including Event Management Tickets averages.



# Team Members
Tejashwar Singh Banafar, Saint Mary's University  
Dennis Huynh, Queen's University  
Joonbum Yang, University of Toronto  
Fangyi Yu, Ontario Tech University  
