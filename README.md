# Introduction-To-Splunk-SPL
Learning to Query the Splunk



Q1: "Navigate to http://[Target IP]:8000, open the "Search & Reporting" application, and find through an SPL search against all data the account name with the highest amount of Kerberos authentication ticket requests. Enter it as your answer."

Since I dont have any experience with Splunk yet I reviewed this page to get a better understanding. 

https://redhead0ntherun.medium.com/kerberos-anomaly-detection-via-splunk-8fd57ee0d278


"-Let’s focus on a very popular attack technique used by more advanced adversaries — Kerberoasting. Basically an attacker will scan an environment looking for accounts with a Service Principal Name associated with the account. The attacker will then use a tool to request the TGT ticket for that account. With the TGT they can then either impersonate the user OR crack the user’s NTLM password offline."

Through my search on Google I see that Kerboeros Request tickets are logged as Event ID 4768 so I add that to my query. I then checked previous queries and saw that a few other queries are commnonly associated with Event ID 4768 so I added those. 

<img width="921" height="299" alt="image" src="https://github.com/user-attachments/assets/ba340c80-fdfe-4034-bd72-7f4bfa32a1a5" />


I saw that this had 48 hits so honestly I was just shooting in the dark with the answer then found it.


<img width="1048" height="403" alt="image" src="https://github.com/user-attachments/assets/14365db6-6a7b-4a61-97b8-4a1b97b9618f" />


Q2 "Navigate to http://[Target IP]:8000, open the "Search & Reporting" application, and find through an SPL search against all 4624 events the count of distinct computers accessed by the account name SYSTEM. Enter it as your answer."

I searched through initally the number of hits when I simply changed the event id and filtered for the user "SYSTEM" it came back with 6900 hits so I knew there was more to this query. So then I used a hit that the HTB had "stats dc()"


<img width="1233" height="626" alt="image" src="https://github.com/user-attachments/assets/5f6a8ef6-773b-4728-a428-74f7e44f91d3" />


