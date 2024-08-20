# serverless-defaults
Repro of serverless default issue

## Issue:
In v3, serverless's default syntax allowed a fallback value when a parameter passed to the CLI wasn't found.
V4 does not allow the same and will give you a "failed to resolve" error:
```
✖ Failed to resolve variable 'custom.SOME_VARIABLE.option3' with resolver 'config' and provider 'self': Error: Key "custom.SOME_VARIABLE.option3" is not defined in config file
Error: Failed to resolve variable 'custom.SOME_VARIABLE.option3' with resolver 'config' and provider 'self': Error: Key "custom.SOME_VARIABLE.option3" is not defined in config file
```

## Steps to recreate:
See v3 success:
```
cd v3
yarn
yarn deploy --param="arg=option3"
```
See v4 failure:
```
cd v4
yarn
yarn deploy --param="arg=option3"
```
