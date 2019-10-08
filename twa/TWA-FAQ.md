## How does Teamwork Analytics deal with Microsoft Graph Throttling?

Teamwork Analytics pulls data from Microsoft Graph via HTTPS. The Teamwork Analytics windows service has 4 concurrent https clients that can run with request up twice per second. However, Microsoft Graph throttles requests to an appropriate speed for Microsoft which means Teamwork Analytics does not always reach its theoretical maximum speed of data collection.

We follow Microsoft guidance which states "When throttling occurs, Microsoft Graph returns HTTP status code 429 (Too many requests), and the requests fail. A suggested wait time is returned in the response header of the failed request.". We respect this suggested wait time in line with best practice.

Microsoft do not publish what their limits are for Graph for Microsoft Teams. Here is their documentation: https://docs.microsoft.com/en-us/graph/throttling

Customers cannot control this behaviour, it is automatically handled in the Teamwork Analytics application.

