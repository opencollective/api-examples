# List Gift Card transactions from Organization

```graphql
query GiftCardTransactions($account: AccountReferenceInput!) {
  transactions(
    account: $account
    includeRegularTransactions: false
    includeGiftCardTransactions: true
  ) {
    totalCount
    limit
    nodes {
      netAmount {
        value
        currency
      }
      toAccount {
        slug
      }
      createdAt
    }
  }
}
```


Sample parameters:

```json
{
   "account":{
      "slug":"triplebyte"
   }
}
```

