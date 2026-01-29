#MOBILE POS ARCHITECTURE
platform: Android (Kotlin)
pattern: MVVM + repository

Backend:
- Django + DRF
- baseURL: http://192.168.2.23/api

Principles:
- offline first
- room = local cache
- backend = source of truth
- POS can create Orders, scan barcode
- POS cannot edit product catalog

POS access:
- client role can't access to POS

POS authentication:
- first Auth online
- token store on local (access and refresh)
- local store of roles
- state to manage auth