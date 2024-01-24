# TN-keycloak

In the Realm settings -> "HTML Display name", add:
```
<img src="https://raw.githubusercontent.com/transitionnetwork/TN-keycloak/main/logo-transition-network.png"> &nbsp; <strong>Transition ID</strong>
```
# V2 is based on
[https://github.com/lukin/keywind](https://github.com/lukin/keywind)


## If something is changed in the CSS or JS file

Rename the file with a new version and update the new name in `theme.properties`, otherwise Keycloak still use the old version because of the cache, even after restarting the container on Cloudron.
