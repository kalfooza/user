---
title: 'Load Group'
---

## Information
The load group API call is used to load the group details. It may be used by both authenticated and unauthenticated users, the latter for whom a subset of data will be returned.

## Request

### **[POST] /group/load**

### Headers

[ui-tabs]
[ui-tab title="Definition"]
|  Name  |  Type  |  Required
|  :-----          |  :-----          |  :-----          |
|  Content-Type |  "application/json"  |  true
|  Authorization |  String |  false
[/ui-tab]
[ui-tab title="Sample"]
    Content-Type: "application/json"
	Authorization: “<token-value>”
[/ui-tab]
[/ui-tabs]

### Body
[ui-tabs]
[ui-tab title="Definition"]
|  Name  |  Type  |  Required
|  :-----          |  :-----          |  :-----          |
|  groupId |  GUID string |  true 
[/ui-tab]
[ui-tab title="Sample"]
    {
        groupId: “00000000-0000-0000-000000000000”
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
### Error object
|  Type  |  Name  |  Always  |
|  :-----          |  :-----          |  :-----          |
|  code |  integer |  true 
|  message |  string |  true 
[/ui-tab]
[ui-tab title="Group object"]
### Group object
|  Name  |  Type  |  Always  
|  :-----          |  :-----          |  :-----          |
|  id |  GUID string |  true 
|  name |  string |  true 
|  image |  URL string |  true 
|  created at |  ISO date string |  true 
|  status |  GroupStatus string |  true 
|  product |  object |  true 
|  members |  object array |  true 
[/ui-tab]
[ui-tab title="Product object"]
### Product object
|  Name  |  Type  |  Always
|  :-----          |  :-----          |  :-----          |
|  id |  string |  true 
[/ui-tab]
[ui-tab title="Member object"]
### Member object
|  Name  |  Type  |  Always
|  :-----          |  :-----          |  :-----          |
|  name |  string |  true 
|  profile picture |  URL |  true 
|  isLeader |  boolean |  false 
[/ui-tab]
[/ui-tabs]