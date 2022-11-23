# mm.aoirint.com

## Backup DB

```shell
docker compose exec postgres pg_dump -Fc -U mmuser mattermost > "backups/postgres_$(date '+%Y-%m-%d_%H-%M-%S').dump"
```

## Restore DB

```
cat backups/postgres.dump | docker compose exec -T postgres pg_restore -U mmuser -d mattermost
```

