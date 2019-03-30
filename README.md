<h1 align="center">
  <img src="https://raw.githubusercontent.com/ITISEnricoFermi/archivio-digitale-client/81041b2932b032ead156777a6927efe1925b52ca/static/shortcut/safari-pinned-tab.svg?sanitize=true" height="100"><br/>
  📚 Archivio Digitale 📚
</h1>
<p align="center">
  Progetto Archivio Digitale sviluppato per l'ITIS Enrico Fermi.
</p>

## Prerequisiti

- Docker
- Docker swarm

## Come avviare

- Generare i segreti

```shell
$ echo jwtsecret | docker secret create archivio_server_jwt_secret -
$ echo mail-user | docker secret create archivio_mailer_user -
$ echo mail-password | docker secret create archivio_mailer_password -
$ echo minio-sk | docker secret create archivio_minio_secret_key -
$ echo minio-ak | docker secret create archivio_minio_access_key -
```

- Avvio dello stack

```shell
$ git clone https://github.com/ITISEnricoFermi/archivio-digitale-nginx.git
$ cd archivio-digitale-nginx
$ docker stack deploy -c docker-compose.yml archivio
```

## TODO

- Non esporre minio alla rete esterna (rimuovere sezione `ports` in `docker-compose.yml/minio`)

## Authors

- **Ernesto Montada** - [n4y0n](https://github.com/n4y0n)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
