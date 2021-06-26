Answer the following questions:<br>
<br>
In the last 7 days, how many unique visitors were located in India?<br>
223<br>
In the last 24 hours, of the visitors from China, how many were using Mac OSX?<br>
13<br>
In the last 2 days, what percentage of visitors received 404 errors? How about 503 errors?<br>
404: 0-7%<br>
503: 0-3.8%<br>
In the last 7 days, what country produced the majority of the traffic on the website?<br>
China <br>
Of the traffic that's coming from that country, what time of day had the highest amount of activity?<br>
12pm-1pm<br>
List all the types of downloaded files that have been identified for the last 7 days, along with a short description of each file type (use Google if you aren't sure about a particular file type).<br>
GZ: Compressed files<br>
CSS: HTML elements to find page<br>
ZIP: Archive zip<br>
Deb: files to upgrade Deb commands/install files<br>
RPM: specific to redhat install files<br>
Now that you have a feel for the data, Let's dive a bit deeper. Look at the chart that shows Unique Visitors Vs. Average Bytes.<br>
o	Locate the time frame in the last 7 days with the most amount of bytes (activity).<br>
6/24/2021 3:58pm<br>
In your own words, is there anything that seems potentially strange about this activity? <br>
Nothing was to strange it was a large download gz file from Kibana. <br>
Filter the data by this event.<br>
What is the timestamp for this event?<br>
15:58<br>
What kind of file was downloaded?<br>
GET /kibana/kibana-6.3.2-linux-x86_64.tar.gz<br>
From what country did this activity originate?<br>
China<br>
What HTTP response codes were encountered by this visitor?<br>
HTTP/1.1" 200 16750<br>
Switch to the Kibana Discover page to see more details about this activity.<br>
What is the source IP address of this activity?<br>
1.145.31.121<br>
What are the geo coordinates of this activity?<br>
"lat": 28.28980556, "lon": -81.43708333<br>

What OS was the source machine running?<br>
Win 8<br>
What is the full URL that was accessed?<br>
https://artifacts.elastic.co/downloads/kibana/kibana-6.3.2-linux-x86_64.tar.gz<br>
From what website did the visitor's traffic originate?<br>
http://www.elastic-elastic-elastic.com/success/aleksandr-serebrov<br>
Finish your investigation with a short overview of your insights.<br>
What do you think the user was doing?<br>
Downloading log data from Kibana on web server<br>
Was the file they downloaded malicious? If not, what is the file used for?<br>
It received a 200-status code so I don’t believe it was malicious I think it was a simple request to get information from Kibana on web server data analytics<br>
Is there anything that seems suspicious about this activity?<br>
At first glance it looks like everything is ok and nothing to dig more into.<br>
Is any of the traffic you inspected potentially outside of compliance guidelines?<br>
The fact that a large zip file was downloaded and can be run through Linux could potentially have some compliance issues as we would not want anyone downloading anything typically other then admins. <br>


