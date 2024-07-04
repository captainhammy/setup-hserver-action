[![Tests](https://github.com/captainhammy/setup-hserver-action/actions/workflows/tests.yml/badge.svg)](https://github.com/captainhammy/setup-hserver-action/actions/workflows/tests.yml)
# Setup hserver

This GitHub Action will configure `hserver` for Houdini license acquisition.

## Usage

```yaml
  - name: Setup hserver
    uses: captainhammy/setup-hserver-action@v1
    with:
      server: https://www.sidefx.com/license/sesinetd
      client_id: AAA123
      client_secret_key:  BBB456
      extra: --some --extra args
```

This is equivalent to the following command:

`hserver --clientid AAA123 --clientsecret BBB456 --host https://www.sidefx.com/license/sesinetd --some --extra args`

### Inputs

Required Inputs:
- server: The license server value/string. This can be a single server, or [multiple servers](https://www.sidefx.com/docs/houdini/ref/utils/hserver.html#license-server-chaining) 

Optional Inputs:
- client_id, client_secret_key: [Client id and client secret](https://www.sidefx.com/docs/api/credentials/index.html) values can be provided if you are using [Login Licensing](https://www.sidefx.com/docs/houdini/licensing/login_licensing.html). 
- extra: Any extra args which will be appended to the `hserver` command
