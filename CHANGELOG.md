# v6.0.0:

- added the ability to create worker only and web-only deployments using `web.enabled` and `worker.enabled`
- **[breaking]** worker and web secrets are now separated into 2 different templates, `worker-secrets.yaml` and `web-secrets.yaml`. Users bringing their own secrets will have to split them into 2 different k8s objects.

# v7.0.0:

- upgraded the PostgreSQL Chart (direct dependency of this Chart) from `0.13.1` to `5.3.8`. As various values (like `postgresUser`) changed (to, for instance, `postgresqlUsername`), a major bump was needed.

# v8.0.0:

- changed the format for worker-only deployments from `concourse.worker.tsa.host` and `concourse.worker.tsa.port` to `concourse.worker.tsa.hosts` to take in an array of parameters.

# v9.0.0:

- changed the input format for `concourse.web.auth.mainTeam.config`. Previously you would pass the path to a YAML file that contained the team config. This variable now expects the contents of a YAML file. The chart will then create a `ConfigMap` and store the contents of the `mainTeam.config` key in `main-team.yml`.

# v10.0.0:

- remove `concourse.web.enableLidar`: `lidar` is now the only way of find and check resources
- remove `concourse.web.noop`: with the introduction of component tracking, there's no need for `noop` anymore
- remove `concourse.web.maxConns`: in favor of `concourse.web.apiMaxConns` and `concourse.web.backendMaxConns`

