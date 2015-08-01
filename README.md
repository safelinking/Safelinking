Safelinking
===========

Welcome to the official Github account of Safelinking link protection services. You will find here our changelog as well as some documentation about our API, that is available at https://safelinking.net/api

Changelog
---

24-05-2015: 3.0.0
* Launching the new version.

API documentation
---

All parameters may be sent as either GET or POST.

### Check
___

URL:

``` 
https://safelinking.net/check 
```

Input:

| Parameter        | Description           | Value           |
| ------------- |:-------------:|:-------------:|
| link      | Fill with some protected link (MANDATORY). | https://safelinking.net/* |
| output      | Specify the output format.      | Either 'XML' or 'JSON'      |

Example:

```
 https://safelinking.net/check?link=https://safelinking.net/s64aTFQ 
```

Output:

Parameter | Description | Value
--- | --- | ---
Online | Links are online. | Either XML 'link_status' tag or JSON.
Not yet checked | Links have not been checked yet. | Either XML 'link_status' tag or JSON.
Broken | Not all the links are online. | Either XML 'link_status' tag or JSON.
Unknown | The links are unknown to the robot. | Either XML 'link_status' tag or JSON.
Offline | Links are offline. | Either XML 'link_status' tag or JSON.


### Auth
___

URL:

``` 
https://safelinking.net/api 
```

Input: 

| Parameter        | Description           | Value           |
| ------------- |:-------------:|:-------------:|
| mode      | Select the mode to 'get-api-hash'. | get-api-hash |
| username      | Username of the user.      | Input      |
| password      | Password of the user.      | Input      |
| output      | Specify the output format.      | Either 'XML' or 'JSON'      |

Example:

```
 https://safelinking.net/api?mode=get-api-hash&username=YOURUSERNAME&password=YOURPASSWORD 
```

Output:

| Parameter        | Description           | Value           |
| ------------- |:-------------:|:-------------:|
| Confirmation      | You are authenticated.      | Either XML 'api_hash' tag or JSON      |
| Error      | There was a problem.      | Either XML 'api_error' tag JSON      |


### Protect
___

URL:

``` 
https://safelinking.net/api 
```

Input: 

Parameter | Description | Value
--- | --- | ---
links-to-protect | The links you wish to protect, separated by line breaks or "%0A" (MANDATORY). | URL
enable-captcha | Enable or disable CAPTCHA. | 'on' or 'no'
captcha-type | Choose your CAPTCHA alternative technology. | 'recaptcha' or 'fancy+captcha'
link-password | Set a password to your package. | Input
link-description | Set a description to your package. | Input
provider-name | The name of your website or community. | Input
provider-url | The URL of your website or community. | URL
rsdf | Generate a RSDF container file. | on
dlc | Generate a DLC container file. | on
rtc | Generate a CCF container file. | on
cnl2 | Generate a CNL2 container file. | on
individual-links | Create packages for each links submitted. | on
links-per-mirror | Create packages for each mirrors. | on
show-short-links | Display sflk.in links. | on
mirror1 | First set of mirror links. | URL
mirror2 | Second set of mirror links. | URL
mirror3 | Third set of mirror links. | URL
mirror4 | Fourth set of mirror links. | URL
mirror5 | Fifth set of mirror links. | URL
mirror6 | Sixth set of mirror links. | URL
mirror7 | Seventh set of mirror links. | URL
mirror8 | Eighth set of mirror links. | URL
mirror9 | Ninth set of mirror links. | URL
mirror10 | Tenth set of mirror links. | URL
output | Specify the output type. | Either 'XML' or 'JSON' or 'raw'
username | The username of the account. | Input
api_hash | This can be found in API auth results. | Input
use-default-options | Use your account's link presets. | 1

Example:

```
 https://safelinking.net/api?links-to-protect=http://google.com/&enable-captcha=on
```

Parameter | Description | Value
--- | --- | ---
p_links | Protected links. | URL
d_links | Direct links. | URL
r_links | Removal links. | URL
