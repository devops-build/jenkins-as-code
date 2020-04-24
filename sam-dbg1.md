
```bash
resources/helm/
|-- secret-files
    |-- default-setup-password          # pre-baked setup user password
    |-- default-setup-user              # pre-baked setup user name
    |-- deploy-key-shared-library       # private ssh deploy key
    |-- deploy-key-shared-library.pub   # public ssh deploy key
    |-- github-ci-password              # GitHub Jenkins user password
    |-- github-ci-token                 # GitHub Jenkins user access token
    |-- github-ci-user                  # GitHub Jenkins user name
    |-- github-oauth-client-id
    |-- github-oauth-client-secret
    |-- slack-token
    |-- ssh-agent-access-key            # private ssh key for agent access
    |-- ssh-agent-access-key.pub        # public ssh key for agent access
    `-- terraform-config                # Terraform backend configs and secrets
        |-- aws-agent-network.backend.config
        |-- aws-agent-network.tfvars
        |-- aws-agent-vms.backend.config
        `-- aws-agent-vms.tfvars
```
