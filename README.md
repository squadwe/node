# @squadwe/node

A node.js client for Squadwe APIs

Note: This is a work in progress. Interface can change before a stable release.

### How to use

1. Install the library

```
yarn add @squadwe/node
```

or

```
npm install --save @squadwe/node
```

2. Create a Squadwe Client by providing the host URL and API Access Token

```js
const SquadweClient = require('@squadwe/node')

const config = { host: 'https://app.squadwe.com', apiAccessToken: 'your-access-token' }
const Squadwe = new SquadweClient({ config })
```

Supported config params are shown below.

| Key | Default Value | Required | Description |
| -- | -- | -- | -- |
| apiVersion | api/v1 | False | The version of the API, at the moment v1 is only available |
| apiAccessToken | | True | API access token to authenticate with the APIs. You can get the token from your Profile Settings |


1. Fire an API request

```js
// ...

const getContacts = async (accountId) => {
  try {
    const { data } = await Squadwe.contacts(accountId).get()
    console.log(data);
  } catch (error) {
    console.log(error);
  }
}

getContacts(1);
```
