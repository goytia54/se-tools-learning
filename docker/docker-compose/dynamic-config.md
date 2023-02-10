# Dynamic Config

## Named Subsets of Services
* Service profiles to target just certain services

```
    profiles:
     - storefront_profiles: 
```
`--profile <profile-name>` flag

## Multiple Compose Files
* Distinct desired behaviors that do not coincide
* Different environments
* `docker-compose.yaml docker-compose.override.yml`
* `docker-compose.local.yml
* Override can just contain snippets
* `docker compose -f docker-compose.yaml -f docker-compose.local-yaml up`

## Env Variables
* tags, versions or ports
* `${TAG}`, defaults to empty string
* Make it in line, or pass it in or a `.env` file or pass in `--env-file [path]`
* Any env set in shell will override
* Require env file :?opps tag is required
