# api

## Overview

The `api` service is a C# ASP.NET 8 service that provides a GraphQL API for the 3PROJ project.

The service is run using a new unix user. This ensures security. File manipulation is delegated to the [ftp](ftp.md) service.

It is composed of the following dependencies:

<tabs>
<tab title="Entity Framework 8">
An ORM that provides an abstraction over the PostgreSQL database.
This is used to define entities and relationships between them:

<emphasis>
<code-block lang="c#">
class User {
   Guid Id { get; set; }
   ICollection&lt;Group&gt; Groups { get; set; }
}
class Group {
   Guid Id { get; set; }
   ICollection&lt;User&gt; Users { get; set; }
}
</code-block>

This code block will produce the following many-to-many relationship:

<code-block lang="mermaid">
classDiagram
direction BT
class Users {
   uuid Id
}
class Groups {
   uuid 
}
class UserGroups {
   uuid UserId
   uuid GroupId
}
UserGroups --> Users : UserId
UserGroups --> Groups : GroupId
</code-block>
</emphasis>
</tab>
<tab title="HotChocolate 14">
A GraphQL server library for .NET.
This is used to define queries, mutations and subscriptions:

<emphasis>
<code-block lang="c#">
public class Query {
   public IQueryable&lt;User&gt; GetUsers([Service] MyDbContext context) => context.Users;
}
</code-block>

This code block will make the following query available:

<code-block lang="graphql">
query {
   users {
      id
   }
}
</code-block>

Which will return a list of users with their ids.

<code-block lang="json">
{
   "data": {
      "users": [
         {
            "id": "6783b96c-720c-4162-b150-3c812e52ce21"
         },
         {
            "id": "4e481268-926c-4618-aa17-27172319f4f2"
         }
      ]
   }
}
</code-block>

</emphasis>

</tab>
<tab title="FluentFTP 49">
A FTP client library for .NET, used to interact with the <a href="ftp.md">ftp</a> service. Every file type uploaded to the API uses a different user account to limit the attack surface.
</tab>
<tab title="QuestPDF">
The api uses <a href="https://www.questpdf.com/getting-started.html">QuestPDF</a> to generate the various pdf files to be distributed to the clients. This library is open-sourced and is easily mastered.
</tab>
<tab title="PayPal">
The <a href="https://developer.paypal.com/home">paypal API</a> is used to create transactions from user to user. An API key is provided to access the paypal api.
</tab>
</tabs>

## Testing

The `api` can be tested using dotnet [testing tools](https://learn.microsoft.com/en-us/dotnet/core/testing/unit-testing-with-dotnet-test). The testing environment uses Bogus 35.5.0 C# library to generate fake data. At this moment, the dotnet testing is also used to populate the database with fake data. 