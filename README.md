# TWiki-Docker
A Dockerized TWiki

## USAGE
All Data will be stored under `/data`. You should attach some
external storage there ` -v /mnt/twiki:/data`

The following environment variables are parsed and used at the moment

|   VAR         |    default            | description            |
|---------------|-----------------------|------------------------|
| ADMIN\_PW     | changeme              | Administrator Password |
| URL\_HOST     | http://localhost:80   | Full URL ( as received by the webserver ) |
| SCRIPT\_PATH  | /bin                  | URI Path to "bin"      |
| PUP\_PATH     | /pub                  | URI Path to "pub"      |


## Example
```bash
docker run --name twiki -dt -p 8080:80 -v /home/data/:/data -e URL_HOST=http://10.11.12.13:8080/ -e ADMIN_PW=pass1234 twiki
```


## debug

```bash
cat /data/data/warn201809.txt
..
| 2018-09-05 - 22:48:43 | Registration failed: RCS: failed to create file /var/www/twiki/data/Main/TWikiUsers.txt: Permission denied at /var/www/twiki/lib/TWiki/Store/RcsFile.pm line 910.
...
# change to right permission
```

