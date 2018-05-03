# Lomadee API

[![npm package](https://nodei.co/npm/lomadee-api.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/lomadee-api/)

API integration with Lomadee

## Install

```bash
$ npm install lomadee-api
```

## Get Token and SourceID

* SourceID - http://developer.buscape.com.br/portal/developer/tutoriais/gerando-seu-source-id.html
* API Token - http://developer.buscape.com.br/portal/developer/tutoriais/criando-seu-app-token.html

## Usage

```js
"use strict";

let Lomadee = require("lomadee-api"),
    lomadee = new Lomadee("token", "sourceid");

lomadee.categories({}, (err, results) => {
    console.log(results);
});

lomadee.programs((err, results) => {
    console.log(results);
});

lomadee.offers({}, (err, results) => {
    console.log(results);
});

lomadee.product({}, (err, results) => {
    console.log(results);
});

lomadee.coupons({results: 100}, (err, results) => {
    console.log(results);
});

lomadee.report("user", "pass", {startDate: '27052016', endDate: '16072016', eventStatus: 0, publisherId: 'your publisher id'}, (err, results) => {
    if(err)
        console.log(err);
    else
        console.log(results);
});

lomadee.deeplink("http://www.submarino.com.br/", (err, url) => {
    console.log(url); //http://links.lomadee.com/ls/T1k5YTtyR0hYZWxPTDszNTcwMTM4ODswOzk1MjswOzU3NjY7QlI7MztodHRwJTNBJTJGJTJGd3d3LnN1Ym1hcmluby5jb20uYnIlMkY7MDsw.html
});
```
