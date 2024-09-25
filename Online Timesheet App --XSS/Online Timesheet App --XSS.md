***XSS in SourceCodester Online Timesheet App 1.0 (index.php)***

**summary:** 
****A vulnerability classified as problematic was found in SourceCodester Online Timesheet App 1.0. This vulnerability affects unknown code of the file index.php. The manipulation of the argument day/task leads to cross site scripting.****

***Affected Locations:***

online-timesheet/index.php, day/task parameter

***Description:***

Cross-site scripting (XSS) vulnerabilities occur when:

Data enters a web application through an untrusted source. In the case of persistent (also known as stored) XSS, the untrusted source is typically a database or other back-end data store.

***Proof of Concept:***

As observed in the screenshot below, when we send a XSS payload query in the "day" or "task" field for the "Add Timesheet" portal, the home page shows an alert, suggesting a persistent XSS vulnerability.
![](Pasted%20image%2020240925135425.png)

![](Pasted%20image%2020240925135433.png)
![](Pasted%20image%2020240925135509.png)
![](Pasted%20image%2020240925135515.png)
![](Pasted%20image%2020240925135521.png)
