# List top backed Collectives

```graphql
query TopBackedCollectives($slug: String!) {
  account(slug: $slug) {
    memberOf(
      role: BACKER
      orderBy: { field: TOTAL_CONTRIBUTED, direction: DESC }
    ) {
      nodes {
        account {
          slug
        }
        totalDonations {
          value
          currency
        }
      }
    }
  }
}
```

Sample parameters:

```json
{
  "slug":"triplebyte"
}
```
