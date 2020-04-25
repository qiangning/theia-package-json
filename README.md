# theia-package-json
This repo hosts my `package.json` configuration file for using [theia](https://theia-ide.org/docs/composing_applications/) as an IDE on remote servers. The special thing about this configuration is that I spent an entire day figuring out why the official tutorial didn't work when I wanted to have python highlight. It turned out that first, we need to use the `0.15.0` version for everything, and second, we need to have both `@theia/python` and `@theia/textmate-grammars` in `package.json`.
# Install
On your server,
```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.5/install.sh | bash
nvm install 10
npm install -g yarn
mkdir ~/theia
cd ~/theia
```
Put `package.json` into `~/theia`

# Build
On your server,
```
yarn
yarn theia build
```

# Start theia
On your server,
```
yarn start
or,
yarn start /my-workspace --hostname [a.b.c.d] --port [xxxx]
```

# Use theia as an IDE on server
From the local,
```
ssh -L xxxx:a.b.c.d:xxxx [your_user_name]@[your_server_address]
```

Now you can use your chrome and go to the url [a.b.c.d:xxxx].
