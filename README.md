# PostBoost Rust SDK

Official Rust client for the [PostBoost API](https://postboost.co/docs/api).

## Install

```toml
[dependencies]
postboost = "1.4.0"
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
| **Version** | v1.4.0 |

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

---

## Documentation for API Endpoints

All URIs are relative to *https://postboost.co/app/api*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AiApi* | [**blog_to_social**](docs/AiApi.md#blog_to_social) | **POST** /{workspaceUuid}/ai/blog-to-social | Generate social media captions from a blog post
*AccountsApi* | [**get_account**](docs/AccountsApi.md#get_account) | **GET** /{workspaceUuid}/accounts/{accountUuid} | Get account
*AccountsApi* | [**list_accounts**](docs/AccountsApi.md#list_accounts) | **GET** /{workspaceUuid}/accounts | List accounts
*MediaApi* | [**abort_chunked_upload**](docs/MediaApi.md#abort_chunked_upload) | **DELETE** /{workspaceUuid}/media/chunked/{uploadUuid} | Abort chunked upload
*MediaApi* | [**complete_chunked_upload**](docs/MediaApi.md#complete_chunked_upload) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/complete | Complete chunked upload
*MediaApi* | [**delete_media_bulk**](docs/MediaApi.md#delete_media_bulk) | **DELETE** /{workspaceUuid}/media | Delete media (bulk)
*MediaApi* | [**get_media**](docs/MediaApi.md#get_media) | **GET** /{workspaceUuid}/media/{mediaUuid} | Get media
*MediaApi* | [**get_remote_upload_status**](docs/MediaApi.md#get_remote_upload_status) | **GET** /{workspaceUuid}/media/remote/{downloadId}/status | Get remote upload status
*MediaApi* | [**initiate_chunked_upload**](docs/MediaApi.md#initiate_chunked_upload) | **POST** /{workspaceUuid}/media/chunked/initiate | Initiate chunked upload
*MediaApi* | [**initiate_remote_upload**](docs/MediaApi.md#initiate_remote_upload) | **POST** /{workspaceUuid}/media/remote/initiate | Initiate remote upload
*MediaApi* | [**list_media**](docs/MediaApi.md#list_media) | **GET** /{workspaceUuid}/media | List media
*MediaApi* | [**update_media**](docs/MediaApi.md#update_media) | **PUT** /{workspaceUuid}/media/{mediaUuid} | Update media
*MediaApi* | [**upload_chunk**](docs/MediaApi.md#upload_chunk) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/upload | Upload a chunk
*MediaApi* | [**upload_media**](docs/MediaApi.md#upload_media) | **POST** /{workspaceUuid}/media | Upload media (binary)
*PostsApi* | [**add_post_to_queue**](docs/PostsApi.md#add_post_to_queue) | **POST** /{workspaceUuid}/posts/add-to-queue/{postUuid} | Add post to queue
*PostsApi* | [**approve_post**](docs/PostsApi.md#approve_post) | **POST** /{workspaceUuid}/posts/approve/{postUuid} | Approve post
*PostsApi* | [**create_post**](docs/PostsApi.md#create_post) | **POST** /{workspaceUuid}/posts | Create post
*PostsApi* | [**delete_post**](docs/PostsApi.md#delete_post) | **DELETE** /{workspaceUuid}/posts/{postUuid} | Delete post
*PostsApi* | [**delete_posts_bulk**](docs/PostsApi.md#delete_posts_bulk) | **DELETE** /{workspaceUuid}/posts | Delete posts (bulk)
*PostsApi* | [**get_post**](docs/PostsApi.md#get_post) | **GET** /{workspaceUuid}/posts/{postUuid} | Get post
*PostsApi* | [**list_posts**](docs/PostsApi.md#list_posts) | **GET** /{workspaceUuid}/posts | List posts
*PostsApi* | [**schedule_post**](docs/PostsApi.md#schedule_post) | **POST** /{workspaceUuid}/posts/schedule/{postUuid} | Schedule post
*PostsApi* | [**update_post**](docs/PostsApi.md#update_post) | **PUT** /{workspaceUuid}/posts/{postUuid} | Update post
*ReceiptsApi* | [**create_receipt**](docs/ReceiptsApi.md#create_receipt) | **POST** /panel/receipts | Create receipt
*ReceiptsApi* | [**delete_receipt**](docs/ReceiptsApi.md#delete_receipt) | **DELETE** /panel/receipts/{receiptUuid} | Delete receipt
*ReceiptsApi* | [**delete_receipts_bulk**](docs/ReceiptsApi.md#delete_receipts_bulk) | **DELETE** /panel/receipts | Delete receipts (bulk)
*ReceiptsApi* | [**get_receipt**](docs/ReceiptsApi.md#get_receipt) | **GET** /panel/receipts/{receiptUuid} | Get receipt
*ReceiptsApi* | [**list_receipts**](docs/ReceiptsApi.md#list_receipts) | **GET** /panel/receipts | List receipts
*ReceiptsApi* | [**update_receipt**](docs/ReceiptsApi.md#update_receipt) | **PUT** /panel/receipts/{receiptUuid} | Update receipt
*SubscriptionsApi* | [**add_generic_subscription**](docs/SubscriptionsApi.md#add_generic_subscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/generic | Add generic subscription
*SubscriptionsApi* | [**cancel_subscription**](docs/SubscriptionsApi.md#cancel_subscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/cancel | Cancel subscription
*SubscriptionsApi* | [**change_subscription_plan**](docs/SubscriptionsApi.md#change_subscription_plan) | **PUT** /panel/workspaces/{workspaceUuid}/subscription/change-plan | Change subscription plan
*SubscriptionsApi* | [**checkout_subscription**](docs/SubscriptionsApi.md#checkout_subscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/new | New subscription checkout
*SubscriptionsApi* | [**create_subscription**](docs/SubscriptionsApi.md#create_subscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription | Create subscription
*SubscriptionsApi* | [**delete_subscription**](docs/SubscriptionsApi.md#delete_subscription) | **DELETE** /panel/workspaces/{workspaceUuid}/subscription | Delete subscription
*SubscriptionsApi* | [**get_subscription**](docs/SubscriptionsApi.md#get_subscription) | **GET** /panel/workspaces/{workspaceUuid}/subscription | Get subscription
*SubscriptionsApi* | [**remove_generic_subscription**](docs/SubscriptionsApi.md#remove_generic_subscription) | **DELETE** /panel/workspaces/{workspaceUuid}/subscription/generic | Remove generic subscription
*SubscriptionsApi* | [**resume_subscription**](docs/SubscriptionsApi.md#resume_subscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/resume | Resume subscription
*SubscriptionsApi* | [**update_subscription**](docs/SubscriptionsApi.md#update_subscription) | **PUT** /panel/workspaces/{workspaceUuid}/subscription | Update subscription
*TagsApi* | [**create_tag**](docs/TagsApi.md#create_tag) | **POST** /{workspaceUuid}/tags | Create tag
*TagsApi* | [**delete_tag**](docs/TagsApi.md#delete_tag) | **DELETE** /{workspaceUuid}/tags/{tagUuid} | Delete tag
*TagsApi* | [**get_tag**](docs/TagsApi.md#get_tag) | **GET** /{workspaceUuid}/tags/{tagUuid} | Get tag
*TagsApi* | [**list_tags**](docs/TagsApi.md#list_tags) | **GET** /{workspaceUuid}/tags | List tags
*TagsApi* | [**update_tag**](docs/TagsApi.md#update_tag) | **PUT** /{workspaceUuid}/tags/{tagUuid} | Update tag
*UsersApi* | [**create_user**](docs/UsersApi.md#create_user) | **POST** /panel/users | Create user
*UsersApi* | [**delete_user**](docs/UsersApi.md#delete_user) | **DELETE** /panel/users/{userId} | Delete user
*UsersApi* | [**delete_users_bulk**](docs/UsersApi.md#delete_users_bulk) | **DELETE** /panel/users | Delete users (bulk)
*UsersApi* | [**get_user**](docs/UsersApi.md#get_user) | **GET** /panel/users/{userId} | Get user
*UsersApi* | [**list_users**](docs/UsersApi.md#list_users) | **GET** /panel/users | List users
*UsersApi* | [**update_user**](docs/UsersApi.md#update_user) | **PUT** /panel/users/{userId} | Update user
*WorkspacesApi* | [**add_user_to_workspace**](docs/WorkspacesApi.md#add_user_to_workspace) | **POST** /panel/workspaces/{workspaceUuid}/users | Add user to workspace
*WorkspacesApi* | [**create_workspace**](docs/WorkspacesApi.md#create_workspace) | **POST** /panel/workspaces | Create workspace
*WorkspacesApi* | [**delete_workspace**](docs/WorkspacesApi.md#delete_workspace) | **DELETE** /panel/workspaces/{workspaceUuid} | Delete workspace
*WorkspacesApi* | [**delete_workspaces_bulk**](docs/WorkspacesApi.md#delete_workspaces_bulk) | **DELETE** /panel/workspaces | Delete workspaces (bulk)
*WorkspacesApi* | [**get_workspace**](docs/WorkspacesApi.md#get_workspace) | **GET** /panel/workspaces/{workspaceUuid} | Get workspace
*WorkspacesApi* | [**list_workspaces**](docs/WorkspacesApi.md#list_workspaces) | **GET** /panel/workspaces | List workspaces
*WorkspacesApi* | [**remove_user_from_workspace**](docs/WorkspacesApi.md#remove_user_from_workspace) | **DELETE** /panel/workspaces/{workspaceUuid}/users | Remove user from workspace
*WorkspacesApi* | [**update_workspace**](docs/WorkspacesApi.md#update_workspace) | **PUT** /panel/workspaces/{workspaceUuid} | Update workspace
*WorkspacesApi* | [**update_workspace_user**](docs/WorkspacesApi.md#update_workspace_user) | **PUT** /panel/workspaces/{workspaceUuid}/users | Update user role in workspace
