# Crypto Please Protocol

## Pre-requisites

1. Wallet applies for registration and provides deep link for app installation. For example, if wallet uses Firebase Deep Links, it will have the following format: `https://example.page.link/?link={{ link }}&apn=com.example.app&ibi=com.example.app&isi=1234567890`. `{{ link }}` is a stub and will be later replaced automatically.
2. We add wallet to the DB and assign `appId`.
3. We add wallet IDs to `assetlinks.json` and `apple-app-site-association`.
4. Wallet can generate both links offline. The first one has the following format: `https://sol.cryptoplease.link?key=KEY_FIRST_PART&token=TOKEN_ID&app=APP_ID`
   
   | Parameter | Required | Description |
   |-----------|----------|-------------|
   | key       | Yes      | First part of base58-encoded private key. |
   | token     | No       | Token mint. If not provided, SOL will be used. |
   | app       | No       | App ID to install if user has no other compatible wallet installed. CryptoPlease app will be used if not provided at all or invalid ID is provided. |

   The second link has the following format: `https://sol2.cryptoplease.link?key=KEY_SECOND_PART`

   | Parameter | Required | Description |
   |-----------|----------|-------------|
   | key       | Yes      | Second part of base58-encoded private key. |

5. User can send the links using any method.

## Processing flow

```mermaid
flowchart TD
    1[/User clicks first link/] --> 2{Is compatible\nwallet\ninstalled?}
    2 --> |Yes| 3{Deep link\nhandled by\napp?}
    3 --> |Yes| 4[App processes link\nhttps://sol.cryptoplease.com?key=FIRST...]
    3 --> |No| 5([Redirects to\nhttps://sol1.cryptoplease.com?key=FIRST...])
    2 --> |No| 6([Redirects to app deep link])
    6 --> 7[/User installs the app/]
    5 --> 8([Launches page with link\ncryptoplease-sol://1?key=FIRST...])
    7 --> 9[App processes link\nhttps://sol.cryptoplease.com?key=FIRST...]
    8 --> 10[/User taps link/]
    10 --> 11[App processes link\ncryptoplease-sol://1?key=FIRST...]
    4 & 9 & 11 --> 12[App suggests to open 2nd link]
    12 --> 13[/User taps 2nd link/]
    13 --> 14{Deep link\nhandled by\napp?}
    14 --> |Yes| 15[App processes link\nhttps://sol2.cryptoplease.com?key=SECOND]
    14 --> |No| 16([Launches page with link\ncryptoplease-sol://2?key=SECOND])
    16 --> 17[/User taps link/]
    17 --> 18[App processes link\ncryptoplease-sol://2?key=SECOND]
    15 & 18 --> 19[App processes payment]
```

### Legend:

```mermaid
flowchart TD
    1[/User action/]
    2([Implemented by cryptoplease])
    3[Should be implemented by app]
```
