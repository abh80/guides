# Spotify-api.js

Spotify-api.js is a promise based quick wrapper for spotify web api which covers the all the api endpoints!<br/>
If you do not know about this package and much then we will suggest you to check out its [Npm Page](https://npmjs.com/package/spotify-api.js), [GitHub](https://github.com/spotify-api/spotify-api.js) and [Documentation](https://spotify-api.js.org)

> The problem here comes is spotify api resets its token every 5 minutes. The problem here comes is spotify api resets its token every 5 minutes.<br/>And thats what spotify-api.js package helps to. It helps to connect with the api with less codes!

# Getting Started

## Version

Most of them use v4 of spotify-api.js which is not so useful and there is no doumentation for it. But currently v5 beta version exists. The v4 version does not has a good userlient and base and the v5 might be slow because of the extended fetch. In overall conclusion v5 has lot of methods but is slow whereas v4 is opposite. You can use the below code to know the version which you use...

```js
spotify.version
```

## Types of tokens

Before enetering to the spotify-api.js part, lets be clear with types of token. There are 2 types of bearer token. The first one is the api token and the second one user token(scoped token);

| Content    | Api Token        | User Token              |
|------------|------------------|-------------------------|
| Search, get, fetch playlists, track, etc | yes     | yes     |
| Fetch current user information | no   | based on scopes  |
| Access to player  | no     | based on scopes  |

## Api Client

If you have read the above table, then you can know that the api client can only access the search data of spotify which is useful for analysis of data. You can access the api client through [Client](https://spotify-api.js.org/#/docs/class/Client).<br/>
First of all you need to make a spotify developer app [here](https://developer.spotify.com/dashboard/) then get your client secret and client id.

You can use the following code to get your api access token

```js
const Spotify = require("spotify-api.js");
const Auth = new Spotify.Auth();

const token = await Auth.get({
    client_id: "client id",
    client_secret: "client secret",
}); // Will return a promise of token 

console.log(token); // Spotify resets its token each every 1 to 5 minutes to prevent api spam...
```

## Current User Client

User client can access the current user information and can be used for personalization. You can access this client directly through [Client.user](https://spotify-api.js.org/#/docs/class/Client?scrollTo=user) or [UserClient](https://spotify-api.js.org/#/docs/class/UserClient)<br/>
The Spotify-api.js community has made a guide to authorize with scoped token in their documentation site itself, you can read it from [here](https://spotify-api.js.org/#/docs/guide/spotify-auth)

> Some features like [UserClient.player](https://spotify-api.js.org/#/docs/class/UserClient?scrollTo=UserClient,player) is only available for spotify premium users only!

# Conclusion

This guide ends here where you understand the basics of the spotify-api.js package. In the next part of the guide we will be discussing some tricks of spotify-api.js<br/>
Thanks for viewing this guide, you can try to edit this page and extend this guide :)