## Architecture ##

WeHostVoIP is organized in a layered architecture. The main components of the system are:

1. Cluster of SIP Proxies
2. Session and Media Border Controllers

The cluster of SIP proxies are responsible for high availability and the centralization of signaling. The Session and Media Border Controllers are the workhorses of the system. They process all calls and the media relay between them. The SMBC may be installed on premises for maximum privacy and the lowest latency possible. The architecture of the system may be viewed below:

![WeHostVoIP_Arquitecture](https://user-images.githubusercontent.com/4958202/147883266-19256a68-8730-4d33-aaba-678e07e7c512.png)

The advantage for customers is to avoid all the work required to load balance servers. It is very hard to combine software development with services. By using WeHostVoIP you can start selling tomorrow, not in two years. 

### Minimalism

We have restricted features such as Presence, Conferencing and Queuing. We are positioning the system for small to medium businesses, not Contact Centers or Large Enterprises. The objective is to allow high scalability on sales avoiding duplication of features with Microsoft Teams and Google Apps. We know that most companies are using email with one of these two companies. There is no purpose in duplicating presence, conference and chat features. What we are providing is a phone system companion for Google and Microsoft users. 
