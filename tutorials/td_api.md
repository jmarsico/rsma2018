---
layout: subpage
title: "TouchDesigner + API"
---

<img 
src="{{site.baseurl}}/assets/td_json_overview.png" 
style="max-width: 600px;" 
/>

> Download the [td_json.toe](https://drive.google.com/open?id=1OYK9JBgt5Nd63GDUMgWWvh1FdVMk9w3f) file from the [TouchDesigner Examples](https://drive.google.com/drive/folders/144ml7hfzFDR0Y7ZKa4WMo_aPQbVOkqTP?usp=sharing) folder on Google Drive.


## What is an API?



## TouchDesigner + APIs
TD's `web` DAT allows us to send `GET` requests to any website and store the response in a text DAT. 


<img 
src="{{site.baseurl}}/assets/td_json_web.png" 
style="max-width: 600px;" 
/>

You can change the URI that you want to retrieve in the parameters window of the `web` DAT. Clicking the `Fetch` button sends the request and retreives the response. 

<img 
src="{{site.baseurl}}/assets/td_json_pythong.png" 
style="max-width: 600px;" 
/>

TouchDesigner doesn't have any built-in JSON parsing, so we'll need to write some custom python go get the JSON data into a format that TouchDesigner can use.

You'll need to select the python DAT and type `ctrl + r` to get the python script to run.