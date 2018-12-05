### Investigating google.com in order to determine the URLs that are used for certain actions

Complete these 3 tasks:
- Using Burp or Developer tools, determine the url and the request made when searching on Google.
- Take a look at the cookies in the /search GET request and determine all the cookies that can only be accessed via http. 
- Take a look at the header called "Accept-Encoding". What does it mean? Explain what gzip, deflate is?

Use the functions inside of each other to get the user's name.

Sample Result:
```
1. https://www.google.com/
An easy way to do this would be inspecting search button on Google's homepage and looking for a form tag. Once you find it, you should get similar tag: 

<form class="tsf nj" action="/search" style="overflow:visible" id="tsf" method="GET" name="f" onsubmit="return q.value!=''" role="search"><div id="tophf">

You can see that it's making a GET request on /search url and passing parameters. In order to see all the parameters /search takes, go to Burp and inspect the request that was made:

https://www.google.com/search?source=hp&ei=f8kCXJH5IaXOjwSljZ_oAw&q=ss&btnK=%D2%B6%D1%83%D1%81%D1%82%D1%83%D2%B7%D3%AF+%D0%B4%D0%B0%D1%80+Google&oq=ss&gs_l=psy-ab.3..0i10i1i67i42j0i67j0l8.144547.144728..146695...3.0..0.698.1705.4-1j2......0....1..gws-wiz.....6..35i39j0i131j0i131i10i1.KyFRuIZ0KYs

2. After inspecting cookie for Google search request, we get a total of 12 cookies: CONSENT, _gcl_au, OTZ, SID, HSID,SSID, APISID, SAPISID, NID,1P_JAR, DV, SIDCC

CONSENT=YES+US.en+20161120-18-0; 
_gcl_au=1.1.754074972.1541798449;
 OTZ=4665445_76_76_104100_72_446760; 
SID=tgaQJ5WjVvVZGCauT-MuKP0QbTifn8EJ1-5XkXl82X8OAKoa_c5N8Sj37ebsFaSxmsYK-g.; 
HSID=AeibYJggtnWW5eIIX;
 SSID=AciIw-axxLegi4YOe; 
APISID=Agsyeg1mNjVsoYhU/A6VguIm5NJWzFeRmM;
SAPISID=XPW5YkLhx-_9Nzhq/Aa7-bCLsBtPtgifVx; NID=148=FfV9qXfUGNh_T5OSFhLhIOGMExY_5J4vIExnOQ9moXlfMAr2QGu1tpxumul6muT-0CAiigNebcZhwKUafgqm5tU1TBM4cBkhITde1AIPpBMxmTSh9U41lF5N9tn7q4wqfcLfTz-CHMaRlZba_TBecnHLiixhjaEMTTmim1N
1P_JAR=2018-12-01-17; 
DV=U6KOYKw8-g1QANEH2apbUwbRps-udhaFx1nBXyYtCwEAABBru-FDkGnwqgAAAEiyrB5UTa7lLAAAADcbMdsdVdcYFwAAAA; 
SIDCC=ABtHo-FTg4kqMd8IOdpF5hhQb_Vmaersnat3npJVBWMpkM7Gsgn8scdzhdo_RSgxr0r9rmAe6gVF

In order to determine which of these cookies cannot be accessed by Javascript console, we go to Settings/Content settings/Cookies/See all Cookies and Site Data/Search gor Google.com and click on a cookie to get more information. Look at "Accessible to script" metadata. If it says HttpOnly that means, the cookie cannot be accessed via JS.

3. Mozilla has a good documentation on Content-Encoding:

The Accept-Encoding request HTTP header advertises which content encoding, usually a compression algorithm, the client is able to understand. Using content negotiation, the server selects one of the proposals, uses it and informs the client of its choice with the Content-Encoding response header.
-gzip is a file format and a software application used for file compression and decompression. 
-Deflate is a lossless data compression algorithm and associated file format
```


#### Investigating google.com in order to determine the URLs that are used for certain actions

Questions that came up:
* How do you filter BURP so it only shows Google's request/responses?
* How do you determine the right /search GET request if there are many redirect requests in Burp at the same time?

#### Code-along Script: Filtering in Burp Topic Overview

[Facilitator codes] Filtering - 1m
```
You can go to Target->Scope and filter to only view google.com. Google makes other requests at the same time, and you can further define certain patterns to "Exclude from scope".

```

[Facilitator speaks]: Open up Burp and click on Target -> Scope - and include google.com into a scope in the next 60 seconds. Make sure in your Proxy -> Http history, you check "show only in-scope items box".

[Facilitator codes] Review if Burp filters requeusts correctly - 1m

[Facilitator speaks]: Everyone check to see if your neighbor got their filtering to work and give me a thumbs up when both of your neighbors got it working.
[Pause 1min]

[Facilitator codes and speaks:] As you have already noticed, you can see that Google has already made a lot of requests when you clicked on Search button. Now how do you determine the first request that was made when you clicked on Search. - 1m
```
Now, open up Developer tools, and inspect search button. Look for the form tag in the top of a button. Once you find the form tag, you can see the correct url in the actions attribute.
```
[Pause 1min]
[Facilitator speaks]: Once you have that working, go to Burp and look for that particular request.


Total time: 5-6 minutes
