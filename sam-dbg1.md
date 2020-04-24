# sam-dbg1

- mv _ex: aws-terraform, helm
- dcp
- Dockerfile-sam: v204.6-openj9 ##from: k-spe/dvp-jenkins:v204.6
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

- pre-install-plugins

```log
377
378Installed plugins:
379ace-editor:1.1
380ansicolor:0.6.3
381antisamy-markup-formatter:2.0
382apache-httpcomponents-client-4-api:4.5.10-2.0
383authentication-tokens:1.3
384authorize-project:1.3.0
385bouncycastle-api:2.18
386branch-api:2.5.6
387build-name-setter:2.0.4
388build-user-vars-plugin:1.5
389cloudbees-folder:6.12
390collapsing-console-sections:1.8.0
391command-launcher:1.4
392conditional-buildstep:1.3.6
393configuration-as-code-support:1.18
394configuration-as-code:1.39
395credentials-binding:1.22
396credentials:2.3.7
397dashboard-view:2.12
398delivery-pipeline-plugin:1.4.2
399display-console-output:1.0.5
400display-url-api:2.3.2
401docker-commons:1.16
402docker-workflow:1.23
403durable-task:1.34
404email-ext:2.69
405emailext-template:1.1
406embeddable-build-status:2.0.3
407external-monitor-job:1.7
408git-client:3.2.1
409git-parameter:0.9.12
410git-server:1.9
411git:4.2.2
412github-api:1.111
413github-branch-source:2.6.0
414github:1.29.5
415google-oauth-plugin:1.0.0
416handlebars:1.1.1
417icon-shim:2.0.3
418jackson2-api:2.10.3
419javadoc:1.5
420jdk-tool:1.4
421job-dsl:1.77
422jquery-detached:1.2.1
423jquery:1.12.4-1
424jsch:0.1.55.2
425junit:1.28
426kubernetes-client-api:4.9.1-1
427kubernetes-credentials:0.6.2
428kubernetes:1.25.3
429localization-support:1.1
430localization-zh-cn:1.0.14
431lockable-resources:2.7
432mailer:1.32
433mask-passwords:2.13
434matrix-auth:2.5
435matrix-project:1.14
436maven-plugin:3.6
437momentjs:1.1.1
438oauth-credentials:0.4
439pam-auth:1.6
440parameterized-trigger:2.36
441pipeline-build-step:2.12
442pipeline-github-lib:1.0
443pipeline-graph-analysis:1.10
444pipeline-input-step:2.11
445pipeline-milestone-step:1.3.1
446pipeline-model-api:1.6.0
447pipeline-model-declarative-agent:1.1.1
448pipeline-model-definition:1.6.0
449pipeline-model-extensions:1.6.0
450pipeline-rest-api:2.13
451pipeline-stage-step:2.3
452pipeline-stage-tags-metadata:1.6.0
453pipeline-stage-view:2.13
454pipeline-utility-steps:2.5.0
455plain-credentials:1.7
456resource-disposer:0.14
457role-strategy:2.16
458run-condition:1.3
459scm-api:2.6.3
460script-security:1.71
461simple-theme-plugin:0.6
462slave-setup:1.10
463snakeyaml-api:1.26.4
464ssh-credentials:1.18.1
465ssh-slaves:1.31.2
466ssh:2.6.1
467structs:1.20
468throttle-concurrents:2.0.2
469timestamper:1.11.3
470token-macro:2.12
471trilead-api:1.0.6
472uno-choice:2.2.2
473variant:1.3
474workflow-aggregator:2.6
475workflow-api:2.40
476workflow-basic-steps:2.20
477workflow-cps-global-lib:2.16
478workflow-cps:2.80
479workflow-durable-task-step:2.35
480workflow-job:2.38
481workflow-multibranch:2.21
482workflow-scm-step:2.11
483workflow-step-api:2.22
484workflow-support:3.4
485ws-cleanup:0.38
486Cleaning up locks
```