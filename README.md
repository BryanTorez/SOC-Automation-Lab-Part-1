<h1>SOC Automation (Home Lab) - Part 1</h1>

<p align="center">
<img src="https://snipboard.io/6rb2ue.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<h2>Description</h2>
<br />
<p align="center">
Welcome to part one of five for the series of the SOC automation project.
The goal here is to go from nothing at all, to a full-blown Wasa instance with SOAR integration, along with a fully functional case management using the Hive. You don't want to miss out on these labs because this will allow you to gain those hands-on experience that are needed to get into the field of cyber security, specifically within the domain of security operations. Now I am sure there will be some errors popping up for some when tackling these labs, but that should help you build up your researching skills. 
<br />
<br />
<img src="https://snipboard.io/cLrCtR.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="https://snipboard.io/Nfka0C.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In this part one series, we will be focusing on creating our diagram and mapping out how we want to build out our lab logically. The main thing here is to allow us to build a visual, so then we can start to understand how data might flow and of course, what are the pieces required to make this all work. The reason I am doing it this way is because during some interviews some would provide you with a whiteboard and ask you to draw a diagram of a basic lab and secure it. Now hopefully by participating in this lab, you'll gain a lot more confidence in doing so. 
<br />
<br />
<img src="https://snipboard.io/SKWgji.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
To create our diagram I'll use
Tool a site called draw.io because it is free to use and we love free it is quick to access as well the one thing to keep in mind is that these diagrams do not need to be pretty you just need to do it and build it out now later down the road you can go ahead and make it look pretty especially if you are going to present this to a client but if it's just for us in a lab environment I'd rather you put in the work and focus on doing it versus spending hours on trying to make it look visually appealing we'll start off by
<br />
<br />
This will be a five-part series... 
<br />
<br />
Part 1
I will walk you through how you can draw a logical diagram, as this will help you visualize your lab and make it easier; for not only yourself but also for others to digest. 
<br />
<br />
Part 2
<br />
<br />
I will walk you through on how to install the components and get you set up in the cloud. If you don't want to use the cloud and have the resources to spin up a virtual machine on your host, you can do that as well.
<br />
<br />
Day 3 
<br />
<br />
I will walk you through how to configure the servers and endpoints to talk to one another.
<br />
<br />
Day 4
<br />
<br />
The fourth day will be exciting because we will begin generating telemetry that is related to Mimikatz on our endpoint, which will then trigger an alert on Wasa that you created on purpose.
<br />
<br />
Day 5 
<br />
<br />
The final day will be a long one as we will go through how to set up SOAR step by step and integrate everything. This means our Wasah, The Hive, and Shuffle. We will see how alerts get sent over to the SOAR platform and created in the Hive, while automatically emailing analysts such as yourself about the details of the alert along with automated responsive availabilities. 
<br />
<br />
Now that might sound extremely intimidating but don't worry, I'll walk you through it step by step. Now the reason we want to send these alerts over to the Hive is so we can keep track of who is working on the alerts, similar to what a real SOC environment would do, along with sending emails directly to an inbox to review the details of the set alert. 
<br />
<br />
For example, if an IDS alert was generated for a Cobalt Strike, the analyst would then begin by looking at surrounding events and if they identified the user had accessed, let's say a domain called malware.com, prior to the alert. They could then perform additional analysis on that domain. Analysts can utilize domain reputation tools for passive analysis, and if they have the go-ahead, they can perform dynamic analysis by looking at the domain's behavior by accessing it. Using a platform.
<br />
<br />
You might be asking, Can't you just do everything from Wasa? I mean, kind of, but that's just too simple. I want you to flex your skills, work on your troubleshooting, and get some exposure to SAR and a case management system such as the Hive.

That is it for this intro. I hope you are as excited as I am to get started. If you plan on following along, do set up a GitHub account or a free site if you haven't done so already, because you do want to showcase your work and prove to others that you have built a SOC automation lab.
