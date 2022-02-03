# CyberSécurité

## Premiers exercices ..
### Retrouver la page admin

- Se rendre sur `http://37.187.125.224:8081/`
- On lance un `dirb http://37.187.125.224:8081/`
- Voici le retour : 
    ```
    START_TIME: Thu Feb  3 17:09:29 2022
    URL_BASE: http://37.187.125.224:8081/
    WORDLIST_FILES: /usr/share/dirb/wordlists/common.txt

    -----------------

    GENERATED WORDS: 4612

    ---- Scanning URL: http://37.187.125.224:8081/ ----
    --> Testing: http://37.187.125.224:8081/crs
    + http://37.187.125.224:8081/index.php (CODE:200|SIZE:77)
    + http://37.187.125.224:8081/robots.txt (CODE:200|SIZE:48)
    + http://37.187.125.224:8081/server-status (CODE:403|SIZE:281)

    -----------------
    END_TIME: Thu Feb  3 17:18:35 2022
    DOWNLOADED: 4612 - FOUND: 3
    ```
- Nous n'avons pas l'accès à la page `server-status` mais on peut se rendre sur `http://37.187.125.224:8081/robots.txt`
- Sur cette page se trouve cette info : `Disallow: /secret_admin_page_.php`
- On se rend sur `http://37.187.125.224:8081/secret_admin_page_.php` et on peut voir le flag affiché qui est : `robots_qkrfmoyAmDa5_W5N4MRmYBBC4p2j3B9d7ai45KhUh4yhDML1N`