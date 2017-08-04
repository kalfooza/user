---
title: 'Create Group'
---

## Overview

## Request

### **[POST] /group/create**

### Headers

[ui-tabs]
[ui-tab title="Definition"]
|  Name  |  Type  |  Required
|  :-----          |  :-----          |  :-----          |
|  Content-Type |  "application/json"  |  true
|  Authorization |  String |  true
[/ui-tab]
[ui-tab title="Sample"]
    Content-Type: "application/json"
	Authorization: “<token-value>”
[/ui-tab]
[/ui-tabs]

### Body
[ui-tabs]
[ui-tab title="Root Definition"]
|  Name  |  Type  |  Required
|  :-----          |  :-----          |  :-----          |
| productId | Guid String | true
| name |  String |  true 
| description | String | true
| image | URL String | true
| message | String | true
| sendInvitations | bool | false
| members | Array | true
[/ui-tab]
[ui-tab title="Member Definition"]
|  Name  |  Type  |  Required
|  :-----          |  :-----          |  :-----          |
| nickName | String | true
| contact | Object | true
[/ui-tab]
[ui-tab title="Contact Definition"]
|  Name  |  Type  |  Required
|  :-----          |  :-----          |  :-----          |
| type | ContactType String | true
| vaule | String | true
[/ui-tab]
[ui-tab title="Sample"]
    {
    	"productId": "00000000-0000-0000-000000000000",
        "name": “Pletnev Super Fans”,
        "description": "Pletnev in Amsterdam, Feb 2017",
        "image": "https://amazon.s3.com/groupimages/piano.jpg",
        "message": "Hi guys, this is just the invitation to join me at the concert, lets all go through it so that we can book together",
        "members": [
         {
           "nickName" : "Stephen SA", 
           "contact" : {
             "type" : "MOBILE",
             "value" : "+27701231234"
           }
         },
         { 
           "nickName" : "Barnaby G",
           "contact": { 
             "type" : "EMAIL",
             "value" : "barnaby@g.com"
           }
         }
    }
[/ui-tab]
[/ui-tabs]

## Response

[ui-tabs]
[ui-tab title="JSON"]

```javascript
{
  error: {
    code: 0,
    message: “”
  },
    
  group: {
    id: “”,
    name: “”,
    image: “”,
    createdAt: “”,
    status: “”,

   product: {
      id: “”
    },

   members: [
      {
        name: “”,
        profilePicture: “”,
        isLeader: true
      },
      {
        name: “”,
        profilePicture: “”
      }
    ]
  }
}
```

[/ui-tab]
[/ui-tabs]

[ui-tabs]
[ui-tab title="Root object"]
|  Name  |  Type  |  Always
|  :-----          |  :-----          |  :-----         |
|  error |  object |  true
|  group |  object |  true
[/ui-tab]
[ui-tab title="Error object"]
|  Type  |  Name  |  Always  |
|  :-----          |  :-----          |  :-----          |
|  code |  integer |  true 
|  message |  String |  true 
[/ui-tab]
[ui-tab title="Group object"]
|  Name  |  Type  |  Always  
|  :-----          |  :-----          |  :-----          |
|  id |  GUID String |  true 
|  name |  String |  true 
|  image |  URL String |  true 
|  createdAt |  ISO Date String |  true 
|  status |  GroupStatus String |  true 
|  product |  object |  true 
|  members |  object array |  true 
[/ui-tab]
[ui-tab title="Product object"]
|  Name  |  Type  |  Always
|  :-----          |  :-----          |  :-----          |
|  ID |  String |  true 
[/ui-tab]
[ui-tab title="Member object"]
|  Name  |  Type  |  Always | Notes
|  :-----          |  :-----          |  :-----          | :----- |
|  name |  String |  true | | 
|  profile picture |  URL |  true | will be empty on creation as we cannot match a nick name to a picture yet
|  isLeader |  boolean |  false | |
[/ui-tab]
[/ui-tabs]

## Notes

[ui-tabs]
[ui-tab title="ContactType"]
|  Value  |  Notes 
|  :-----          |  :-----          |
|  "MOBILE" |  object |  
|  "EMAIL" |  object |  
[/ui-tab]
[/ui-tabs]

The value sent herein is used to send the member an email containing their invitation together with the message provided in the body parameters. <br/>
If the "MOBILE" contact type is provided, then a SMS will be sent to the user containing a link that they can use to view the invitation and decide whether or not to join the group. <br/><br/>
When verification of the provided value can occur immediately, the call to /group/create will fail, and the appropriate validation related error message will be displayed. In the case that verification cannot be immediately provided, this will be ammended to the member details as soon as it is available; for example, a valid but disconnected phone number will returned a SMS status of failed after some time.


## Common Error Messages




