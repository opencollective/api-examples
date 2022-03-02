# Creating Collective, applying to a Fiscal Host and inviting Collective admins

All in one step!


1) Creating a Collective

```graphql
mutation CreateCollective($collective: CollectiveCreateInput!) {
  createCollective(
    collective: $collective
  ) {
    id
    name
    slug
    description
    githubHandle
  }
}
```

Sample parameters:

```json
{
  "collective":{
     "name":"Hyperwatch",
     "slug":"hyperwatch",
     "description":"Open Source HTTP Traffic Manager",
     "githubHandle":"hyperwatch"
  }
}
```

2) Creating a Collective and Applying to a Host

```graphql
mutation CreateCollective(
  $collective: CollectiveCreateInput!
  $host: AccountReferenceInput
) {
  createCollective(collective: $collective, host: $host) {
    id
    name
    slug
    description
    githubHandle
  }
}
```

Sample parameters:


```json
{
   "collective":{
      "name":"Hyperwatch",
      "slug":"hyperwatch",
      "description":"Open Source HTTP Traffic Manager",
      "githubHandle":"hyperwatch"
   },
   "host":{
      "slug":"opensource"
   }
}
```

3) Creating a Collective, Applying to a Host and inviting admins

```graphql
mutation CreateCollective(
  $collective: CollectiveCreateInput!
  $host: AccountReferenceInput
  $skipDefaultAdmin: Boolean
  $inviteMembers: [InviteMemberInput]
) {
  createCollective(
    collective: $collective
    host: $host
    skipDefaultAdmin: $skipDefaultAdmin
    inviteMembers: $inviteMembers
  ) {
    id
    name
    slug
    description
    githubHandle
  }
}
```

Sample parameters:


```json
{
   "collective":{
      "name":"Hyperwatch",
      "slug":"hyperwatch",
      "description":"Open Source HTTP Traffic Manager",
      "githubHandle":"hyperwatch"
   },
   "host":{
      "slug":"opensource"
   },
   "inviteMembers":[
      {
         "memberInfo":{
            "email":"jane@hyper.watch",
            "name":"Jane Doe"
         },
         "role":"ADMIN"
      }
   ],
   "skipDefaultAdmin": true
}
```