# Self-hosting an open source Dify alternative

Kortix is open source and self-hosts for free, and this page shows the commands that bring it up on a server you control, next to the commands for Dify's own Community Edition. Both stacks run through Docker Compose. Checked October 2026.

## What Dify's Community Edition needs

[Dify's repository](https://github.com/langgenius/dify) documents the self-hosted Community Edition on a machine with at least 2 CPU cores and 4 GiB of RAM, with Docker and Docker Compose v2.24.0 or later installed. You copy the example environment file and start the stack from the `docker` directory:

```sh
cd dify
cd docker
cp .env.example .env
docker compose up -d
```

The Dify dashboard then opens at `http://localhost/install` for the first setup.

## What a self-hosted Kortix installs

[Kortix's self-hosting docs](https://kortix.com/docs/host) describe a self-hosted instance as the full Kortix platform on a server you control: one Docker Compose stack that the `kortix self-host` CLI installs, configures and updates. You point a domain and its `api` subdomain at the server, open ports 80 and 443, then install the CLI, answer the setup questions, and start the stack:

```sh
curl -fsSL https://kortix.com/install | bash
kortix self-host init --domain kortix.example.com --admin-email you@example.com
kortix self-host configure
kortix self-host start
kortix self-host doctor
```

On a bare Linux server, the same docs list a one-line bootstrap that installs Docker, the Compose plugin and the CLI, then starts the stack with a TLS certificate. You run it with `--domain` and `--email` flags, and re-running it is safe. See [Kortix's self-hosting docs](https://kortix.com/docs/host) for the current script.

## Requirements a self-hosted Kortix adds

Beyond Dify's list, a self-hosted Kortix needs A or AAAA records for the domain and its `api` subdomain before the first start, a wildcard record for sandbox previews, and a sandbox provider key for Platinum or the legacy Daytona fallback. Sessions run on that provider, not on the server, and the sandbox calls back to the instance's public API URL, so the host needs a public address. You add your model provider key in the web app after the first sign-in, and your own keys stay yours. For an evaluation run with no domain, the documented tunnel mode starts the stack behind a Cloudflare tunnel:

```sh
kortix self-host init --tunnel cloudflare
kortix self-host start
```

## What you own after the install

The stack writes `docker-compose.yml`, `.env`, a `Caddyfile` and `updater.sh` into `~/.config/kortix/self-host/<instance>/`, and one Compose project named `kortix-<instance>` holds every service. A daily updater pulls new images, migrates the database and rolls the app services. Your agents, skills, company memory and connectors stay in a git repo you own, not in a vendor's dashboard.
