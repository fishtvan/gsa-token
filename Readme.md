# Google Service Account Token Generator

This package uses the service account key and settings to:
1. generate a self signed JWT
2. call the token endpoint for that account
3. returns a *gsa.AccessToken* 

## Usage

1. Load the service.json ***UseJson*** or ***UseStruct*** with a *ServiceAccountConfig*. \
Specifiy the scope for what the token will be used

2. Get the token 

### Example
```
import "github.com/fishtvan/gsa-token"

generator, err := gsa.UseJson("path-to-setting.json", "scope")
token, err := generator.GetServiceToken()
```

*token.Token* is the token Bearer string,\
*token.ExpiresIn* are the seconds for the token to be expire

\
More info on google service accounts:
https://developers.google.com/identity/protocols/oauth2/service-account