Access GA data for a single user via graphQL.

Request must include an ID. This ID is mapped to a fast datastore lookup which will indicate which tenant to send the query to. The tenant will be authenticated using the existing tokens etc for that tenant. A GA request will be made using the service tokens generated when the app was installed.

The GA request will be filtered for only the user ID passed into the GraphQL query.

The schema will match the underlying GA schema, e.g.

```graphql
query UserSegments (UserId!) {
	segments {
		name
	}
}
```

Request can be made using an authentication token, which opens up multi-user routes. It would be expected that this would only be used on the server side.

The graphql server has a few roles:
- authentication -> who can make anonymous queries and who can make administerative queries
- demand management -> ensuring that expensive requests are rate limited unless paying on a higher plan