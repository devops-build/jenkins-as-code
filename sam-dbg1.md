# sam-dbg1

- mv _ex: aws-terraform, helm
- dcp
- Dockerfile-sam: k-spe/dvp-jenkins:v204.6
- plugins: zh, kube, delivery-pipeline_task, display-console, collapsing-console

- scriptapproval.xml

```xml
<approvedSignatures>
    <string>method hudson.model.Computer countBusy</string>
    <string>method hudson.model.Computer getNode</string>
    <string>method hudson.model.Node getLabelString</string>
    <string>method jenkins.model.Jenkins getComputers</string>
    <string>staticMethod jenkins.model.Jenkins getInstance</string> <!-- exist -->
</approvedSignatures>
```

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
