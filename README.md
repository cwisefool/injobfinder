# injobfinder
Find jobs on indeed.com (no affiliation) matching specifications. Completely unofficial. Not endorsed by Intuit. This project may be removed if it is determined during the feasibility study that Indeed's API does not provide adequate search parameters. 

Basic usage: injobfinder spec.json

Spec.json should be a keyed mapping of matching specifications. Jobs will be returned that match any of the specifications. Results for each key be the raw JSON returned from Indeed's API for those search parameters.

Spec.json example: 
```
{
  "goodAndClose": {
    "location": {"zip": "78701"},
    "distance": {"miles": {"max": 25}},
    "annaulSalary": {"min": 
    "keywords": ["programming", "software development"] 
 }
}
```

Example result (see Indeed's documentation, we're using their example here):
```
{  
    "version":2,
    "query":"java",
    "location":"austin, tx",
    "dupefilter":true,
    "highlight":false,
    "radius":25,
    "start":1,
    "end":10,
    "totalResults":547,
    "pageNumber":0,
    "results":[  
        {  
            "jobtitle":"Java Developer",
            "company":"XYZ Corp.,",
            "city":"Austin",
            "state":"TX",
            "country":"US",
            "formattedLocation":"Austin, TX",
            "source":"Dice",
            "date":"Mon, 02 Aug 2017 16:21:00 GMT",
            "snippet":"looking for an object-oriented Java Developer... Java Servlets,
              HTML, JavaScript, AJAX, Struts, Struts2, JSF) desirable. Familiarity with
              Tomcat and the Java...",
            "url":"http://www.indeed.com/viewjob?jk=12345&indpubnum=8343699265155203",
            "onmousedown":"indeed_clk(this, '0000');",
            "latitude":30.27127,
            "longitude":-97.74103,
            "jobkey":"12345",
            "sponsored":false,
            "expired":false,
            "indeedApply":true,
            "formattedLocationFull":"Austin, TX",
            "formattedRelativeTime":"11 hours ago"
        }
    ]
}
```
