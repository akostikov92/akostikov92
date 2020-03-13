<!-- @format -->

# Test Server

Create a file at the root of project folder called `db.json`. Add an empty object in order to test it out. The example below is actually creating an `API endpoint` for us at `'/blogposts'`

```json
{
  "blogposts": []
}
```

Install `json-server` and `ngrok`

```shell
yarn add json-server
yarn add ngrok
```

Add the two scripts to `package.json`

```json
  "scripts": {
    "db": "json-server -w db.json",
    "tunnel": "ngrok http 3000"
  },
```

Start both services. Note: `json-server` run on `port 3000` by default, but can be changed using `-p 3005` if necessary. Update ngrok port to match.

```shell
ngrok by inconshreveable

Session Status                online
Session Expires               7 hours, 50 minutes
Version                       2.3.35
Region                        United States (us)
Web Interface                 http://127.0.0.1:4040
Forwarlocalhost:3000
Forwarding                    https://ffad5fd2.ngrok.io -> http://localhost:3000
Connections                   ttl     opn     rt1     rt5     p50     p90
                              0       0       0.00    0.00    0.00    0.00
```

Enter the temporary url `ngrok` created into the browser. You should see a response of the object in `db.json`
