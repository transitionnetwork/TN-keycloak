# TN-keycloak

In the Realm settings -> "HTML Display name", add:
```
<img src="https://raw.githubusercontent.com/transitionnetwork/TN-keycloak/main/logo-transition-network.png"> &nbsp; <strong>Transition ID</strong>
```


## TODO

- The logo should be in the theme
- In the JS file, `$('#kc-page-title').text('Welcome! Please register if you don\'t have an account yet.');` should be removed and replaced with a translation file


## If something is changed in the CSS or JS file

Rename the file with a new version and update the new name in `theme.properties`, otherwise Keycloak still use the old version because of the cache, even after restarting the container on Cloudron.
