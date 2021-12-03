## Installing PostgreSQL in Arch

- Install postgresql using pacman package manager.
  
```console
sudo pacman -S postgresql
```

- Switch to postgres user
  
```console
sudo -u postgres -i
```

```console
initdb --locale $LANG -E UTF8 -D '/var/lib/postgres/data'
```
- Exit the postgres user

```console
exit
```

- Enable and Start postgresql.service

```console
sudo systemctl enable postgresql.service
sudo systemctl start postgresql.service
```

