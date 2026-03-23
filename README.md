# PostBoost Rust SDK

Official Rust client for the [PostBoost API](https://postboost.co/docs/api).

## Install

```toml
[dependencies]
postboost = "1.1.0"
```

Or with cargo:

```bash
cargo add postboost
```

| | |
|---|---|
| **crates.io** | [crates.io/crates/postboost](https://crates.io/crates/postboost) |
| **GitHub** | [postboost-co/postboost-rust](https://github.com/postboost-co/postboost-rust) |
| **Docs** | [postboost.co/docs/api](https://postboost.co/docs/api) |
| **Version** | v1.1.0 |

## Quick start

```rust
use postboost::apis::posts_api;
use postboost::apis::configuration::Configuration;

let config = Configuration {
    bearer_access_token: Some("YOUR_API_TOKEN".to_string()),
    ..Default::default()
};

let posts = posts_api::list_posts(&config, "YOUR_WORKSPACE_UUID").await?;
for post in posts {
    println!("{}", post.uuid.unwrap_or_default());
}
```

## License

MIT
