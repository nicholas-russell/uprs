# uprs

## Up Bank API wrapper
This crate is an API wrapper for the [Up Bank API](https://developer.up.com.au/).
### Example Usage
```rust
use uprs::api_endpoints::ListAccounts;
use uprs::models::Account;
use uprs::request_sender::ApiRequest;

#[tokio::main]
async fn main() {
    let api_key: String = "$your_access_token".parse().unwrap();

    let list_accounts: Vec<Account> = ListAccounts::new(&api_key).send().await.unwrap();

    for account in list_accounts {
        println!("{}: ${}", account.attributes.display_name, account.attributes.balance.value)
    }
}
```
