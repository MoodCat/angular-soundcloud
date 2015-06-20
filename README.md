Angular Soundcloud API
------------

Because we could not get the Soundcloud SDK to work properly with Angular and ui-router, we decided to build a new Soundcloud API wrapper for Angular.

## Usage 

Include the module like this:
```js
angular.module('SoundCloud').constant('soundCloudKey', 'YOUR-SOUNDCLOUD-APP-ID');
var module = angular.module('yourApp', ['SoundCloud']);
```

Then you can use it in your module
```js
module.controller('MycController', ['SoundCloudLogin', function(SoundCloudLogin) {
	
	this.loginUsingSoundCloud = function() {
		SoundCloudLogin.connect().then(function() {
			// Connected!
		});
	}

}]
```

You can also initialize the login session from an existing token (for example stored using ngCookie or ngStorage)
```js
     SoundCloudSessionManager.init($cookieStore.get('scAuth'));
```

And to check authentication, you can use the following method:

```js
     $rootScope.loggedIn = SoundCloudSessionManager.isConnected();
```

## Features
Besides logging in to Soundcloud, you can fetch the details for the current user and song metadata.

We would love to see a pull request if you want to see another API call featured in this libary!

