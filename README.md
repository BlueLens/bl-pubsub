# BlPubSub.js

BlPubSub.js provides a minimal higher-level wrapper around BlPubSub's API.

## Usage

```javascript
/*
   Data can be retrieved from the API either using callbacks (as in versions < 1.0)
   or using a new promise-based API. The promise-based API returns the raw Axios
   request promise.
 */
import BlPubSub from 'BlPubSub-api';

// unauthenticated client
const aw = new BlPubSub();
let user = gh.User(); // not a gist yet
user.updateProfile({
   
}).then(function({data}) {
   // Promises!
   let createdGist = data;
   return gist.read();
}).then(function({data}) {
   let retrievedGist = data;
   // do interesting things
});
```

```javascript
var BlPubSub = require('BlPubSub-api');

// basic auth
var gh = new BlPubSub({
   username: 'FOO',
   password: 'NotFoo'
   /* also acceptable:
      token: 'MY_OAUTH_TOKEN'
    */
});

var me = gh.getUser(); // no user specified defaults to the user for whom credentials were provided
me.listNotifications(function(err, notifications) {
   // do some stuff
});

var clayreimann = gh.getUser('clayreimann');
clayreimann.listStarredRepos(function(err, repos) {
   // look at all the starred repos!
});
```

## API Documentation


## Installation
BlPubSub.js is available from `npm` or [unpkg][unpkg].

```shell
npm install BlPubSub-api
```

```html
<!-- just BlPubSub-api source (5.3kb) -->
<script src="https://unpkg.com/BlPubSub-api/dist/BlPubSub.min.js"></script>

<!-- standalone (20.3kb) -->
<script src="https://unpkg.com/BlPubSub-api/dist/BlPubSub.bundle.min.js"></script>
```

## Compatibility
`BlPubSub.js` is tested on Node.js:
* 6.x

Note: `BlPubSub.js` uses Promise, hence it will not work in Node.js < 4 without polyfill.

