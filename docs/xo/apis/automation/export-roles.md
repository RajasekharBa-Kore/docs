# Export Roles API

To export bot or admin roles from an account. This is typically used to export roles from one environment to another.

!!!note
    This API requires JWT generated by an application created only from the Bot Admin Console.


<table>
  <tr>
   <td><strong>Method</strong>
   </td>
   <td>GET
   </td>
  </tr>
  <tr>
   <td><strong>Endpoint</strong>
   </td>
   <td><code>https://{{host}}/api/public/roles/export?roleType=admin</code>
   </td>
  </tr>
  <tr>
   <td><strong>Content Type</strong>
   </td>
   <td><code>application/json</code>
   </td>
  </tr>
  <tr>
   <td><strong>Authorization</strong>
   </td>
   <td><code>auth: {{JWT}}</code>
<p>
See <a href="../api-introduction/#generating-the-jwt-token">How to generate the JWT Token.</a>
   </td>
  </tr>
  <tr>
   <td><strong>API Scope</strong>
   </td>
   <td>
<ul>

<li>Bot Builder: Not Applicable

<li>Admin Console: Profile Management > Role Management
</li>
</ul>
   </td>
  </tr>
</table>


## Path Parameters


<table>
  <tr>
   <td><strong>PARAMETER</strong>
   </td>
   <td><strong>REQUIRED/OPTIONAL</strong>
   </td>
   <td><strong>DESCRIPTION</strong>
   </td>
  </tr>
  <tr>
   <td>host
   </td>
   <td>Required
   </td>
   <td>Environment URL, for example, https://platform.kore.ai
   </td>
  </tr>
  <tr>
   <td>roleType
   </td>
   <td>Required
   </td>
   <td>The role type:
<ul>

<li><strong>admin</strong> or

<li><strong>bot</strong>
</li>
</ul>
   </td>
  </tr>
</table>


## Sample Request


```json
curl -X GET \
  'https://{{host}}/api/public/roles/export?roleType=bot' \
  -H 'Content-Type: application/json' \
  -H 'auth: {{YOUR_JWT_ACCESS_TOKEN}}' \
```


 


## Sample Response


```json
[
    {
        "roleType": "admin",
        "_id": "5bd057cc2515025b2a4da326",
        "role": "admin",
        "rDesc": "Master administration role with full control on account activity",
        "permissions": {
            "Invite": "YES",
            "Import Users / Sync": "YES",
            "Directory Sync": "YES",
            "Manage User Profile Fields": "YES",
            "Manage Groups": "YES",
            "Manage Deployment": "YES",
            "Enterprise Bots": "YES",
            "Password Policies": "YES",
            "Single Sign On": "YES",
            "Domain Management": "YES",
            "Kore.ai Connector": "YES",
            "Manage Built-In Admin Roles": "YES",
            "Manage Custom Admin Roles": "YES",
            "View and Run Audit Reports": "YES",
            "Consumer Bots": "YES",
            "View and Run Bot Chat History": "YES",
            "Manage Bot Roles": "YES",
            "Preferences": "YES",
            "Smart Bots": "YES",
            "API Scopes": "YES",
            "Enterprise Key": "YES"
        },
        "refId": "891ce307-f69f-5b9b-9c92-3945ce299e81"
    },
    {
        "roleType": "admin",
        "_id": "5bd83485d01df415735a3a51",
        "role": "admin check11",
        "permissions": {
            "Invite": "YES",
            "Import Users / Sync": "NO",
            "Directory Sync": "NO",
            "Manage User Profile Fields": "YES",
            "Manage Groups": "YES",
            "Manage Deployment": "YES",
            "Enterprise Bots": "YES",
            "Smart Bots": "YES",
            "Preferences": "YES",
            "Single Sign On": "YES",
            "Kore.ai Connector": "YES",
            "Manage Built-In Admin Roles": "YES",
            "Manage Bot Roles": "YES",
            "Manage Custom Admin Roles": "YES",
            "View and Run Audit Reports": "YES",
            "View and Run Bot Chat History": "YES",
            "Consumer Bots": "YES",
            "API Scopes": "YES",
            "Enterprise Key": "YES"
        },
        "rDesc": "",
        "refId": "41bce522-fed8-5efc-b2b0-3d2376b86657"
    }
]
```