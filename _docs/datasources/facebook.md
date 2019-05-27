---
layout: page
section: datasources
title: "Facebook"
order: 1
---

> Attention! The [Google BigQuery](/integrations/google-bigquery) integration has to be enabled to use this feature.

### Importing data from Facebook

Connecting this data source allows you to import advertising costs information for the past 7 days into Google BigQuery once every 24 hours.

### Connecting and configuring

The process of connecting data sources is described in detail in the [overview](https://docs.segmentstream.com/datasources/index).

![](/img/fb.2.png)

After authorization you need to set the data source parameters.

(1) The name of the data source. It is displayed in the interface in the list of sources.

For a full picture of advertising costs, you need to add all your active advertising accounts (2) (see the "How to Find Your Facebook Ad Account ID" section to find out where to find the advertising account ID).

(3) The currency in which you want to export the costs from the advertising accounts.

To save and enable the data source, click "Save" (4).

The "Disconnect" button (5) is used to revoke the authorization data. The settings are saved.

You can enable or disable the data source at any time (6).

### How to Find Your Facebook Ad Account ID

Log in to Facebook with an account that has access to the required company. On the [https://business.facebook.com/select/](http://business.facebook.com/select/) page, select your company. In the window that opens, you will see all your advertising accounts. In order to quickly copy the ID - click on it.

![](/img/facebook_get_id.png)

### Where to get data on advertising costs

The data for this data source will be written to a table named **facebookCosts_{ACCOUNT_ID}_{YYYYMMDD}**

### Table structure

Field name|Type|Mode
--- | --- | ---
cost | FLOAT | REQUIRED
clicks | INTEGER | NULLABLE
impressions | INTEGER | NULLABLE
utmTerm | STRING | NULLABLE
utmCampaign | STRING | NULLABLE
utmContent | STRING | NULLABLE
utmMedium | STRING | REQUIRED
utmSource | STRING | REQUIRED
currency | STRING | NULLABLE