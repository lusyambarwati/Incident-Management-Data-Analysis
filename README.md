# Incident Management Data Analysis

##  Background

### Incident Management

In ITIL (Information Technology Infrastructure Library) terminology, an ‘incident’ is defined as:<br/> 

An unplanned interruption to an IT service or reduction in the quality of an IT 
service. Failure of a configuration item that has not yet impacted service is also 
an incident, for example failure of one disk from a mirror set.<br/>

Incident Management is the process for dealing with all incidents; this can 
include failures, questions or queries reported by the users (usually via a 
telephone call to the Service Desk), by technical staff, or automatically detected 
and reported by event monitoring tools.

###  Purpose/goal/objective
The primary goal of the Incident Management process is to restore normal 
service operation as quickly as possible and minimize the adverse impact on 
business operations, thus ensuring that the best possible levels of service quality 
and availability are maintained. ‘Normal service operation’ is defined here as 
service operation within SLA limits.

### Value to business 

The value of Incident Management includes:<br/>
- The ability to detect and resolve incidents which results in lower downtime to the business, which in turn means higher availability of the service. This means that the business is able to exploit the functionality of the service as designed. 
- The ability to align IT activity to real-time business priorities. This is because Incident Management includes the capability to identify business priorities and dynamically allocate resources as necessary. 
- The ability to identify potential improvements to services. This happens as a result of understanding what constitutes an incident and also from being in contact with the activities of business operational staff. 
- The Service Desk can, during its handling of incidents, identify additional service or training requirements found in IT or the business.

Incident Management is highly visible to the business, and it is therefore easier to 
demonstrate its value than most areas in Service Operation. For this reason, 
Incident Management is often one of the first processes to be implemented in 
Service Management projects. The added benefit of doing this is that Incident 
Management can be used to highlight other areas that need attention – thereby 
providing a justification for expenditure on implementing other processes

### Metrics 
The metrics that should be monitored and reported upon to judge the efficiency
and effectiveness of the Incident Management process, and its operation, will 
include: 
- Total numbers of Incidents (as a control measure) 
- Breakdown of incidents at each stage (e.g. logged, work in progress, closed etc) 
- Size of current incident backlog 
- Number and percentage of major incidents 
- Mean elapsed time to achieve incident resolution or circumvention, broken down by impact code 
- Percentage of incidents handled within agreed response time (incident response-time targets may be specified in SLAs, for example, by impact and urgency codes) 
- Average cost per incident 
- Number of incidents reopened and as a percentage of the total 
- Number and percentage of incidents incorrectly assigned 
- Number and percentage of incidents incorrectly categorized 
- Percentage of Incidents closed by the Service Desk without reference to other levels of support (often referred to as ‘first point of contact’) 
- Number and percentage the of incidents processed per Service Desk agent 
- Number and percentage of incidents resolved remotely, without the need for a visit 
- Number of incidents handled by each Incident Model 
- Breakdown of incidents by time of day, to help pinpoint peaks and ensure matching of resources.


### Data Set Information:

This is an event log of an incident management process extracted from data gathered from the audit system of an instance of the ServiceNowTM platform used by an IT company. The event log is enriched with data loaded from a relational database underlying a corresponding process-aware information system. Information was anonymized for privacy.



### Attribute Information:

1. number: incident identifier (24,918 different values);
2. incident state: eight levels controlling the incident management process transitions from opening until closing the case;
3. active: boolean attribute that shows whether the record is active or closed/canceled;
4. reassignment_count: number of times the incident has the group or the support analysts changed;
5. reopen_count: number of times the incident resolution was rejected by the caller;
6. sys_mod_count: number of incident updates until that moment;
7. made_sla: boolean attribute that shows whether the incident exceeded the target SLA;
8. caller_id: identifier of the user affected;
9. opened_by: identifier of the user who reported the incident;
10. opened_at: incident user opening date and time;
11. sys_created_by: identifier of the user who registered the incident;
12. sys_created_at: incident system creation date and time;
13. sys_updated_by: identifier of the user who updated the incident and generated the current log record;
14. sys_updated_at: incident system update date and time;
15. contact_type: categorical attribute that shows by what means the incident was reported;
16. location: identifier of the location of the place affected;
17. category: first-level description of the affected service;
18. subcategory: second-level description of the affected service (related to the first level description, i.e., to category);
19. u_symptom: description of the user perception about service availability;
20. cmdb_ci: (confirmation item) identifier used to report the affected item (not mandatory);
21. impact: description of the impact caused by the incident (values: 1â€“High; 2â€“Medium; 3â€“Low);
22. urgency: description of the urgency informed by the user for the incident resolution (values: 1â€“High; 2â€“Medium; 3â€“Low);
23. priority: calculated by the system based on 'impact' and 'urgency';
24. assignment_group: identifier of the support group in charge of the incident;
25. assigned_to: identifier of the user in charge of the incident;
26. knowledge: boolean attribute that shows whether a knowledge base document was used to resolve the incident;
27. u_priority_confirmation: boolean attribute that shows whether the priority field has been double-checked;
28. notify: categorical attribute that shows whether notifications were generated for the incident;
29. problem_id: identifier of the problem associated with the incident;
30. rfc: (request for change) identifier of the change request associated with the incident;
31. vendor: identifier of the vendor in charge of the incident;
32. caused_by: identifier of the RFC responsible by the incident;
33. close_code: identifier of the resolution of the incident;
34. resolved_by: identifier of the user who resolved the incident;
35. resolved_at: incident user resolution date and time (dependent variable);
36. closed_at: incident user close date and time (dependent variable).

##### In this notebook, I will perform Data Analysis on Incident management process enriched event log Data Set by using some metrics explained


### Insight

- Ticket numbers significantly decrease in 2017 compare than 2016 and the result also shown more stable and less ticket backlog in 2017, it means company does massive improvement that affecting the amount of reporting ticket

- From total 24918 ticket number, 24905 tickets resolved, that's a sign that the company can handle 99,9% well

- 'Medium' impact has the lowest mean elapsed time, although it has the most ticket number, so companies can focus to find out what causes 'High' and 'Low' impact has higher elapsed time

- Only 1.1% ticket reopen, it is shown that the ticketing agent understand enough when they can close the ticket

- The result shown 45.6% ticket reassign, it could impacting mean elapsed time, companies have to find out what causes this problem (e.g. SOP that not clear enough, agent understanding related this case)

- 36.6% ticket not made SLA, it's a huge amount, 10 most important feature predict incidents handled within agreed response time can help companies to improve ticket that made SLA


### Source
Data Set: Incident management process enriched event log Data Set by UCI Machine Learning Library.<br/>
https://archive.ics.uci.edu/ml/datasets/Incident+management+process+enriched+event+log#

### Reference
Commerce, Office of Government. (2007). The Official Introduction to the ITIL Service Lifecycle. United Kingdom : Office of Government Commerce.
