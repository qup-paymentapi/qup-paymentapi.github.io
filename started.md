# QUp Payment System

> **About QUp Payment Platform**

## Server info

| Server address | Domain                              |
|----------------|-------------------------------------|
| `Local`          | http://192.168.2.81:8080/qupservice |
| `Lab`            | https://gw.lab.qup.vn               |
| `Beta`           | https://gw.beta.qup.vn              |
| `AWS US`         | https://gw.qupworld.com             |
| `AWS SEA`        | https://gw-sea.qupworld.com         |
| `AWS AVIS`       | https://gw-avis.qupworld.com        |


## Authentication

Authentication keys are used to authenticate all of your api calls via [HTTP Basic Auth](https://en.wikipedia.org/wiki/Basic_access_authentication)

| Server address | Role       | Credentials         |
|----------------|------------|---------------------|
| `Local`          | dispatcher | dispatcher/password |
|                | cc         | cc/password         |
| `Lab`            | dispatcher | dispatcher/password |
|                | cc         | cc/password         |
| `Beta`           | dispatcher | dispatcher/password |
|                | cc         | cc/password         |
| `AWS US`         | dispatcher | N/A                 |
|                | cc         | N/A                 |
| `AWS SEA`        | dispatcher | N/A                 |
|                | cc         | N/A                 |
| `AWS AVIS`       | dispatcher | N/A                 |
|                | cc         | N/A                 |


## Request Header

| Key            | Type   | Value                                    | Description                                                |
|----------------|--------|------------------------------------------|------------------------------------------------------------|
| `Content-Type` | String | application/json; charset=UTF-8          | Indicate the media type of the resource                    |
| `x-request-id` | UUID   | Ex: d6c4bb35-5716-47d6-a02e-c017830d63ce | Used to trace the request on the [ELK system](https://elk.qupworld.com/) for commercial servers |

&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
