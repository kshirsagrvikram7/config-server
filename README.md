# Config Server

Centralized configuration service backed by a Git repository.

## Responsibilities
- Serves shared and service-specific configuration.
- Supports versioned configuration through Git branches/tags.
- Keeps environment-specific properties out of application repositories.

## Local setup
The default URI points to `../configuration-repo`.

Start the config repository first:
```bash
cd ../configuration-repo
git init -b main
git add .
git commit -m "feat: initial configuration"
```

Then:
```bash
mvn spring-boot:run
```

Test:
`http://localhost:8888/customer-service/default`

## GitHub
Set:
```text
CONFIG_GIT_URI=https://github.com/<your-org>/configuration-repo.git
```

Never store GitHub tokens/passwords in this repository.
