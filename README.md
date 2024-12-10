# 🚀 Elastic SIEM Project: Threat Detection in Action! 🛡️
This video is a clip from my most recent Home Lab, where I configure a SIEM and test out the rules and alerts via nmap on Kali Linux

Project Completed by: Josh Lindsey
Blog Written by: Josh Lindsey
 ### [See it in Action (Video)](https://youtu.be/LpZ0KIMPMbU)

<h2>📝 Project Overview</h2>
Welcome to my latest cybersecurity adventure! 🌐 This project focuses on setting up an affordable and fully functional SIEM (Security Information and Event Management) solution using Elastic Stack and Kali Linux.

Here’s what I accomplished:

- ✅ Configured Elastic Stack as a SIEM on Elastic Cloud.
- ✅ Deployed and monitored telemetry data using Kali Linux VM.
- ✅ Created custom alert rules and tested them in real-time.
- ✅ Designed dashboards for visualizing security events.

<h2>🌟 Key Achievements</h2>

<h3>📊 Custom Dashboards</h3>
Real-time visualization of security events.
Tailored to track and display telemetry data.
<h3>🚨 Alert Rules</h3>
Detect activities like nmap scans.
Send email notifications for triggered events.
<h3>🔍 Troubleshooting Success</h3>
Resolved issues with field mapping by adapting queries to the process.args field, ensuring accurate alerts.

<h2>🔨 Step 1: Setting the Stage</h2>
<h3>Choosing the Tools</h3>
To get started, I needed a solid tech stack:

- Elastic Stack: For monitoring and visualization.
- Elastic Cloud: A hassle-free hosting solution.
- Kali Linux VM: A powerful playground for generating data and testing attacks.

<p align="center">
<h2>Downloading & Installing Kali Linux</h2>

<a href="https://imgur.com/szPqev8"><img src="https://i.imgur.com/szPqev8.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/PP9Cck3"><img src="https://i.imgur.com/PP9Cck3.png" title="source: imgur.com" /></a></p>



<h2>Configuring Elastic Cloud & Installing on Kali</h2>
<p align="center">
<a href="https://imgur.com/7W9ftHO"><img src="https://i.imgur.com/7W9ftHO.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/LiVcWXm"><img src="https://i.imgur.com/LiVcWXm.png" title="source: imgur.com" /></a></p>


<h2>🖥️ Step 2: Generating the Noise</h2>
To test the SIEM's capabilities, I deployed Kali Linux in VirtualBox. This machine became my “attacker,” simulating reconnaissance activities. Using tools like nmap, I created network traffic to be monitored by Elastic.


<p align="center">
<a href="https://imgur.com/qokcE5Z"><img src="https://i.imgur.com/qokcE5Z.png?1" title="source: imgur.com" /></a></p>



<h2>⚙️ Step 3: Crafting Alert Rules</h2>
Here’s where things got interesting. I designed a custom alert rule to detect nmap scans. At first, I used the query event.action: "nmap_scan", expecting instant alerts. But… nothing happened. 🤔

<h3>Creating the Rule: When Triggered, it's Supposed to Send an Email</h3>
<p align="center">
<a href="https://imgur.com/y1rzYGL"><img src="https://i.imgur.com/y1rzYGL.png" title="source: imgur.com" /></a>
  <b>3️⃣ Entering Custom Query to Help System Determine What Logs will Trigger the Alert</b>
<a href="https://imgur.com/a75Pst5"><img src="https://i.imgur.com/a75Pst5.png" title="source: imgur.com" /></a>
 <b>4️⃣ Selecting Email as a Rule Option:</b>
<a href="https://imgur.com/ZwDfTYO"><img src="https://i.imgur.com/ZwDfTYO.png" title="source: imgur.com" /></a></p>

<h3>Troubleshooting the Alert Rule:</h3>

- I checked the logs in the Elastic Stack UI to verify data ingestion.
- The logs were being generated, but the field I was querying didn’t match the actual log data.
- After exploring, I found the relevant field was process.args, not event.action.
- Updating the query to process.args: "nmap" fixed the issue! The alerts started firing as intended. 🎉

<h3>Logs Appearing via Observability Showing Same Command Run in Kali</h3>
<p align="center">
<a href="https://imgur.com/byWkFBp"><img src="https://i.imgur.com/byWkFBp.png?2" title="source: imgur.com" /></a>

<h2>🚨 Step 4: Alerts in Action</h2>
With the rules in place, the alerts started to come alive—both visually and via email notifications. Here's how it worked:

- Email Alerts: Every time an nmap scan was detected, I received an email notification with details about the activity. This was crucial for real-time monitoring.
- Dashboard Alerts: The Elastic dashboard showed a list of triggered alerts, providing a clear overview of suspicious activities.
- Screenshots of Alerts in Action:
  
- 1️⃣ Email Notification Example:
<p align="center">
<a href="https://imgur.com/cX0wMqT"><img src="https://i.imgur.com/cX0wMqT.png" title="source: imgur.com" /></a>

- 2️⃣ Dashboard Showing Triggered Alerts:
<p align="center">
<a href="https://imgur.com/BDKXO5d"><img src="https://i.imgur.com/BDKXO5d.png" title="source: imgur.com" /></a></p>

This dual-alert system ensured no suspicious activity went unnoticed. 📩📊


<h2>📊 Step 5: Building the Dashboards</h2>
With the alerts working, it was time to visualize the data. I created:

- Real-time Dashboards: To monitor activities and alert triggers.
- Custom Visualizations: Highlighting key security metrics.
- These dashboards provided a clear picture of network activity, making it easier to identify suspicious behavior at a glance.
<p align="center">
<a href="https://imgur.com/O5MOGK4"><img src="https://i.imgur.com/O5MOGK4.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/NODCSBO"><img src="https://i.imgur.com/NODCSBO.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/Mr2KF9H"><img src="https://i.imgur.com/Mr2KF9H.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/TU7RtQF"><img src="https://i.imgur.com/TU7RtQF.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/puiaJ9o"><img src="https://i.imgur.com/puiaJ9o.png" title="source: imgur.com" /></a>

</p>

<h2>🎯 Why This Matters</h2>
This project showcases how anyone with determination and the right tools can build a professional-grade SIEM lab. It’s a fantastic way to learn and practice skills.

<h2>📸 Highlights from the Project</h2>
Here are some snapshots of the project in action:

1️⃣ Elastic Cloud Deployment

2️⃣ Testing Alert Rules

3️⃣ Triggered Alerts

4️⃣ Custom Dashboards
