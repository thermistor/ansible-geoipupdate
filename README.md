![Current tag](https://img.shields.io/github/tag/thermistor/thermistor-ansible-geoipupdate.svg)

# geoipupdate

Install [geoipupdate](https://github.com/maxmind/geoipupdate) from the maxmind repo and configure it with your credentials.

## Vars

Here are the defaults:

    geoipupdate_repo_apt_key_id: '4096R/F44B38CE3DB1BF64B61DBD28DE1997DCDE742AFA'
    geoipupdate_repo: 'ppa:maxmind/ppa'
    geoipupdate_edition_ids:
      - 'GeoLite2-ASN'
      - 'GeoLite2-City'
      - 'GeoLite2-Country'
    geoipupdate_user: geoip
    geoipupdate_user_dir: /usr/share/geoip
    geoipupdate_database_dir: /usr/share/geoip


## Examples

Here is the basic usage:

    - hosts: servers
      roles:
        - role: thermistor.geoipupdate
          geoipupdate_account_id: "{{ your_vault_geoip_account_id }}"
          geoipupdate_license_key: "{{ your_vault_geoipupdate_license_key }}"
          geoipupdate_edition_ids: ['GeoLite2-City']
          geoipupdate_email: you@example.com
