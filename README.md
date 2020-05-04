# e2guardian-conf

# Cronjob to update lists
0 5 * * * curl -o - ftp://ftp.ut-capitole.fr/pub/reseau/cache/squidguard_contrib/blacklists.tar.gz | tar -C /etc/e2guardian/lists/ -zxf - && chown -R e2guardian /etc/e2guardian/lists/ && echo -e "goo.gl\n" | tee -a /etc/e2guardian/lists/blacklists/liste_bu/domains && systemctl restart e2guardian
