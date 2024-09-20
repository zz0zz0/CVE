XSS in SourceCodester Employee Management System 1.0 (add-admin.php)


Affected Locations:

/employee_akpoly/Admin/add-admin.php, txtfullname parameter


Description:

Cross-site scripting (XSS) vulnerabilities occur when:

Data enters a web application through an untrusted source. In the case of persistent (also known as stored) XSS, the untrusted source is typically a database or other back-end data store.


Proof of Concept:

As observed in the screenshot below, when we send a XSS payload query(we use "&lt;/div&gt;" to close &lt;div&gt; tag in HTML) in the "txtfullname" field for the "Add User" portal, the page of "Admin Record" shows an alert, suggesting a persistent XSS vulnerability.

![](Pasted%20image%2020240920170315.png)

![](Pasted%20image%2020240920170408.png)

![](Pasted%20image%2020240920170414.png)

![](Pasted%20image%2020240920170419.png)
