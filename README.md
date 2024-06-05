# rustdesk-server

Rustdesk server deployment docker-compose.

It requires a data folder with the private an public key files. This keys are generated automatically at the first run of the server. This key can be used to ensure which clients can connect to the server. It is recommended to save the keys in a safe place in case the server data is lost, otherwise a new key pair will be generated and all the clients will have to be reconfigured.

Deploy a Rustdesk server with docker-compose.

```bash
docker-compose up -d
```

The key can be generated manually if desired. It just have to be saved in the data folder before the first run of the server.

The keys can be generated with the following command:

```bash
docker run --rm --entrypoint /usr/bin/rustdesk-utils  rustdesk/rustdesk-server-s6:latest genkeypair
```

Wich will show the keys in the console, copy them and save them in the data folder.

```bash
Public Key:  ...
Secret Key:  ...
```

Which have to be saved in the data folder as `id_ed25519.pub` and `id_ed25519` respectively.
