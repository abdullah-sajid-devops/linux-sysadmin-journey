# Day 22 of Cisco Linux Essentials Course

Today I learned 4 really important concepts that go into DevOps — static vs dynamic websites, and Apache vs NGINX web servers.

## Static Website
When the browser sends a request for a web page, the web server just sends back the exact same page as it's stored in memory — no changes, nothing generated, just served as-is.

## Dynamic Website
This is a bit different. The browser's request first goes to a backend application (something like Node.js), and that application generates new content based on what the user actually requested, then sends it back to the browser to display.

## Apache Web Server
Apache is one of the most widely used web servers in the world. At its core, it's the program that serves incoming requests from users.

## NGINX Web Server
NGINX is also an excellent web server, originally started in Russia. It's built almost entirely around performance and speed — it handles fewer features compared to Apache, but runs what it does handle extremely fast. In DevOps, we mainly use NGINX for load balancing and as a reverse proxy.

## Interesting Fact
Today, over 65% of websites in the world run on either Apache or NGINX — and NGINX came out of Russia.

#Linux #DevOps #CiscoNetworkingAcademy #LearningInPublic #WebServers
