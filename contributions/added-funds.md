# Registering "Added Funds" Contributions as Host admin

We're using this query to allocate Funds in the [GitHub Sponsors CSV import](https://github.com/opencollective/opencollective-tools/blob/main/github-sponsors/csv-import.js) script.

Warning: this mutation can only be run by Admins of the Fiscal Host

```graphql
mutation AddFunds(
  $fromAccount: AccountReferenceInput!
  $account: AccountReferenceInput!
  $amount: AmountInput!
  $description: String!
) {
  addFunds(
    account: $account
    fromAccount: $fromAccount
    amount: $amount
    description: $description
  ) {
    id
  }
}
```

Sample parameters:

```
{
   "fromAccount":{
      "slug":"github-sponsors"
   },
   "account":{
      "slug":"Hyperwatch"
   },
   "amount":{
      "value":"1044",
      "currency":"USD"
   },
   "description":"GitHub Sponsors payment"
}
```
