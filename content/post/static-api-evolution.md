+++
author = "Jay Landro"
title = "Flat file APIs are a Speed and Complexity win!"
date = "2019-10-07"
description = "Static APIs are an excellent tool to leverage for slow changing data. Reduce security concerns, scale bigger & reduce complexity with this well paved path to success"
tags = [
    "JAMstack",
    "architecture",
    "json",
    "security",
    "performance",
]
+++

<svg class="canon" xmlns="http://www.w3.org/2000/svg" overflow="visible" viewBox="0 0 496 373" height="373" width="496"><g fill="none"><path stroke="#000" stroke-width=".75" d="M.599 372.348L495.263 1.206M.312.633l494.95 370.853M.312 372.633L247.643.92M248.502.92l246.76 370.566M330.828 123.869V1.134M330.396 1.134L165.104 124.515"></path><path stroke="#ED1C24" stroke-width=".75" d="M275.73 41.616h166.224v249.05H275.73zM54.478 41.616h166.225v249.052H54.478z"></path><path stroke="#000" stroke-width=".75" d="M.479.375h495v372h-495zM247.979.875v372"></path><ellipse cx="498.729" cy="177.625" rx=".75" ry="1.25"></ellipse><ellipse cx="247.229" cy="377.375" rx=".75" ry="1.25"></ellipse></g></svg>

## Reduce security concerns, **increase developer productivity** & leverage core business domain knowledge by moving slow-changing data to a **flat file API**.
<br>
[The Van de Graaf Canon](https://en.wikipedia.org/wiki/Canons_of_page_construction#Van_de_Graaf_canon)

## What is a _static_ API?

A static API is any data stored in a flat file that is consumed and processed by a front end or back end application. The most common combination, with the ubiquity of JSON in restful APIs, is JSON files consumed via http and parsed the same as a standard API response in the consuming application. These could also be XML, CSV, TXT or even Excel files :P

### Let's look at an example

```
// industries.json

{
    data: [
        "Aerospace",
        "Medical",
        "Manufacturing",
        "Service"
    ]
}
```

This totally simplistic example actually serces a very real issue in most companies. A single source of truth for simple business logic. What verticals do we work with? 

By storing this data in **Source Control** (git) members of different teams consuming this data can review the proposed change (Pull Request) and make any changes necessary in the consuming apllication.

Let's consume our sweet new static API via **fetch**
[ TODO: insert netlify url in future]
```
fetch('https://static-api-revolution.netlify.com/industries.json')
.then(res => {
    if (!res.ok)
        throw Error('Fetch failed', err)
    return res.json();
})
.then(data => alert(data.data))
.catch(err => cosnole.error(`Sad trombone:${err}`))
```


<style>
.canon { background: white; width: 100%; height: auto;}
</style>