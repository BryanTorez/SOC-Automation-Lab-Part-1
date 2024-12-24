<h1>SOC Automation (Home Lab) - Part 1</h1>

<p align="center">
<img src="https://snipboard.io/6rb2ue.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<h2>Description</h2>
<br />
<p align="center">
Welcome to part one of five for the series of the SOC automation project.
The goal here is to go from nothing at all, to a full-blown Wasa instance with SOAR integration, along with a fully functional case management using the Hive. You don't want to miss out on these labs because this will allow you to gain the hands-on experience that are needed to get into the field of cyber security, specifically within the domain of security operations. Now I am sure there will be some errors popping up for some when tackling these labs, but that should help you build up your research skills. 
<br />
<br />
<img src="https://snipboard.io/cLrCtR.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="https://snipboard.io/Nfka0C.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
In this part one series, we will be focusing on creating our diagram and mapping out how we want to build out our lab logically. The main thing here is to allow us to build a visual, so then we can start to understand how data might flow and of course, what are the pieces required to make this all work. The reason I am doing it this way is because during some interviews some would provide you with a whiteboard and ask you to draw a diagram of a basic lab and secure it. Now hopefully by participating in this lab, you'll gain a lot more confidence in doing so. 
<br />
<br />
<img src="https://snipboard.io/TEnY3O.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
To create our diagram, I'll use a site called draw.io because it is free to use and quick to access. The one thing to keep in mind is that these diagrams do not need to be pretty. You just need to do it and build it out. Now later down the road you can go ahead and make it look pretty, especially if you are going to present this to a client, but if it's just for us in a lab environment. I'd rather you put in the work and focus on doing it, versus spending hours trying to make it look visually appealing.
<br />
<br />
<p align="center">
We'll start off by heading over to their site at draw.io.
<br />
<br />
<img src="https://snipboard.io/ldmF1R.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Under the search shapes, we can search for "PC" and hit enter. Now we can select any icon that you like in my case I'm going to select this PC over here. Now again, do keep in mind this does not need to be pretty, just as long as you create it and work out the workflow, you should be okay. 
<br />
<br />
<img src="https://snipboard.io/Sdpij9.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://snipboard.io/m9yMcp.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next, I will search for "router" and hit enter. Then let's take this icon. 
<br />
<br />
<img src="https://snipboard.io/bkQRZE.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://snipboard.io/yulB7v.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
I will double-click the PC icon and type "Windows 10 client". We do know for a fact, that this will have the Wazuh agent installed.
<br />
<br />
<img src="https://snipboard.io/FWc2Ay.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next, I will search for "internet" and I'll just take the first icon that's the cloud. I'll double-click it and then I'll type internet that way I just know what that is and rotor as well 
<br />
<br />
<img src="https://snipboard.io/zDlCpx.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://snipboard.io/WeChSL.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
Now because Wazuh, The Hive, and Shuffle is going to live on the internet. I'm going to click on the internet icon, right-click and click "Duplicate". I'll duplicate this three times and I'll rename these as "Wazuh Manager", "The Hive", and lastly, I'll name this as "Shuffle".
<br />
<br />
<img src="https://snipboard.io/eYFzw4.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
The next thing is the SOC analyst. I'm going to duplicate this PC and I'll just leave this over here and type in "SOC Analyst". 
<br />
<br />
<img src="https://snipboard.io/8zejAV.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
Now here's the fun part. We need to draw fancy lines to connect everything together. That way we know logically, how data will flow. We can include lines by clicking and dragging on the icon itself. 
<br />
<br />
<img src="https://snipboard.io/8zejAV.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
<br />
<br />
So if you noticed my computer currently doesn't have an arrow pointing towards it we can just change this by clicking on "None" and one of these arrows. Now we can see that there's an arrow icon pointing to my computer icon.
<br />
<br />
<img src="https://snipboard.io/GnIKw1.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://snipboard.io/Ju3IiQ.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://snipboard.io/VNxKsC.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
However, for this example, I am going to select the arrow type. Which is the first option and then select the second one. This will change the arrow icon into what essentially is a link, and I will change the color to let's say gray for now. 
<br />
<br />
<img src="https://snipboard.io/xLipG6.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://snipboard.io/KChZgv.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br /> 
<br />
<br />
The gray link is going to indicate the sending of events over to the Wazuh manager. Now I will double-click on the link and then type in "Send Events". Let's create another link from the router over to the internet, and again to do that we can click on the arrow, drag it over to the internet and then I will change the arrow type to link and then change the color to gray.
<br />
<br />
<img src="https://snipboard.io/q7XglG.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://snipboard.io/o6xvOk.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
<br />
<br />
Now I'm not going to enter in a text because I know for a fact that that the gray link is sending events. I'm going to move the Wazuh manager icon over just a little bit that way we have a little bit of room to play around with. Same with the Hive and Shuffle.
<br />
<br />
<img src="https://snipboard.io/rzdBiv.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
<br />
<br />
Perfect. Now I will connect the link from the internet to the Wazuh manager. Change the line to link. Change my color. And in this case, I will type in "Receive Events". I'm also going to put in the steps. So step number one, send events. Step number two, receive events. And then from the Wazuh manager, we are going to be sending it over to shuffle.
<br />
<br />
<img src="https://snipboard.io/pwtdNa.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://snipboard.io/Yg620m.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br /> 
<br />
<br />
Now I will change this to a link because I don't like how the line is not straight. You can select the option called "Waypoints" and then you just select the first one and now it is straight.
<br />
<br />
<img src="https://snipboard.io/ECQqVR.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://snipboard.io/ce2XRb.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://snipboard.io/eE4AYc.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
Now if we think logically about how our workflow will work, is that the computer will be sending events over to the Wazuh manager. Wazuh's manager will then create an alert and send that over to Shuffle. In the instance of that, I want to make sure that the link color is not gray that way we can identify a different action. I'll just select it as blue. I'll then type in "Send Alerts".
<br />
<br />
<img src="https://snipboard.io/cgn0qR.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
When Shuffle receives the alert, what will Shuffle do? Well, I want Shuffle to perform some open-source intelligence gathering to enrich our IOCs, our indicators of compromise. And to do this I am going to just click on the icon. Click on the arrow and connect it to the internet. Change my line over to a link. And because we're performing another action separate from sending alerts or send/ receive events. I'm going to change the link color to something else. The next one will be green, so I select green. 
<br />
<br />
<img src="https://snipboard.io/XE3NOw.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
And because we're performing another action separate from sending alerts or send/ receive events. I'm going to change the link color to something else. The next one will be green, so I select green. I will type in, "4. Enrich IOCs".
<br />
<br />
<img src="https://snipboard.io/Vuqc0P.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
Once it's done enriching the IOC, it will send it back to Shuffle. Once that happens, Shuffle will also send an alert over to the Hive. So we will connect Shuffle over to the Hive. Change the link and again we are sending alerts so our send alert action will be blue. I'll change the color to blue. 
<br />
<br />
<img src="https://snipboard.io/glTNvU.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
Change the waypoint. Select the first option to straight, and now it looks a lot nicer. So I'll type in this as "5. Send Alerts".
<br />
<br />
<img src="https://snipboard.io/HFPzsL.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
What is the next step after Shuffle sends an alert over to the Hive? Well, we also want Shuffle to send an email to the SOC analyst. What we can do is click on the icon again. Connect it over to the internet and then change our arrow to link. 
<br />
<br />
<img src="https://snipboard.io/fA8sp9.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
Then I'll select orange for sending an email. We can change the waypoint as well to make it straight from here. I'll just move it over and now it's a little bit easier to see. I'll then double-click and type, "6. Send Email".
<br />
<br />
<img src="https://snipboard.io/PGHh5C.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
Once Shuffle sends the email, the SOC analyst will then receive that email. So go to the SOC analyst and we'll connect it over to the internet. Change it to straight, link, and orange. Now this will say, "7. Send and Receive Email".
<br />
<br />
<img src="https://snipboard.io/PCqcdt.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
When the analyst receives the email. The email itself should contain details about the alert, and it should also ask the question of, "Do you want to contain? Or do you want to perform a certain action? Yes or No." Depending on the response to the action, should then be sent over to Shuffle. Which will be sent over to Wazuh, and then eventually, to the Windows 10 client to perform that action. So let's draw that out.
<br />
<br />
<br />
<br />
I'll click on the SOC analyst workstation. Connect it over to the internet. Change it to straight. Change my link. Let's just do red that way it's a lot easier to see. And I'll type, "8. Send Response Action".
<br />
<br />
<img src="https://snipboard.io/w0ls48.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
That goes over to the internet. The internet then goes over to Shuffle. Change it to Red. I'll move it over a little bit. Change the waypoint to straight. And then I'll move the link over. 
<br />
<br />
<img src="https://snipboard.io/2Yat6j.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
Once Shuffle receives the responsive action, Shuffle should then send it over to the Wazuh manager. I'll type, "8. Send Responsive Action. 
<br />
<br />
<img src="https://snipboard.io/l9rnEd.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
Once the Wazuh manager receives the responsive action, the Wazuh manager's next step is to instruct the agent to perform that responsive action. I'll create a link over from the Wazuh manager to the Windows 10 client. I'll change it to red again. and then I'll type, "8. Perform Responsive Action".
<br />
<br />
<img src="https://snipboard.io/QPr9UE.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
Another way of doing this, is instead of using icons, we can just use text. So, for example, I'll scroll down just a little bit and then I'll double-click anywhere. This will open up a box. Then I'll click on "text". I can just type in "Windows 10".
<br />
<br />
<img src="https://snipboard.io/ZpkcYM.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://snipboard.io/EclNLr.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://snipboard.io/5eAiX9.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
  
What is the purpose of this machine? It is to send events. So type "Send Events". I'll click on the "text" again and the arrow. Now we will say "Wazuh manager". 
<br />
<br />
<img src="https://snipboard.io/4oiVn6.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
What is the purpose of Wazuh? Well, trigger alerts and perform response actions. So type that in.
<br />
<br />
<img src="https://snipboard.io/Mdhi7N.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
So far so good. The next one is, Shuffle so we'll type in Shuffle and the purpose of Shuffle is to receive Wasa alert and send responsive actions from Shuffle we want to also enrich ioc's send an email as well as create an alert on the hive click on the up Arrow we'll start with open source intelligence we will type in enrich ioc's click on the down arrow click on text and now we'll say The Hive the hive's purpose is to create an alert in their case management system and finally Shuffle also we'll send an email so I'll type in email the purpose of the email is to send email and responsive actions now without using icons we can kind of see the flow here right so we'll begin with Windows 10 sends an event over to Wasa manager Wasa manager will then look at those events and Trigger alerts or perform responsive actions if required third Wasa will then send an alert over to shuffle Shuffle will receive the Wasa alert and send
<br />
<br />
<img src="https://snipboard.io/ZpkcYM.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://snipboard.io/EclNLr.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
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
