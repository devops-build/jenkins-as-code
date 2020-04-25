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

- full

```log
457
458Installed plugins:
459Parameterized-Remote-Trigger:3.1.2
460ace-editor:1.1
461analysis-core:1.96
462android-lint:2.6
463ansible:1.0
464ansicolor:0.6.3
465ant:1.11
466antisamy-markup-formatter:2.0
467apache-httpcomponents-client-4-api:4.5.10-2.0
468authentication-tokens:1.3
469authorize-project:1.3.0
470bouncycastle-api:2.18
471branch-api:2.5.6
472build-cause-run-condition:0.1
473build-monitor-plugin:1.12+build.201809061734
474build-name-setter:2.0.4
475build-pipeline-plugin:1.5.8
476build-timeout:1.19.1
477build-timestamp:1.0.3
478build-user-vars-plugin:1.5
479built-on-column:1.1
480cloudbees-folder:6.12
481collapsing-console-sections:1.8.0
482command-launcher:1.4
483conditional-buildstep:1.3.6
484config-file-provider:3.6.3
485configuration-as-code-support:1.18
486configuration-as-code:1.36
487copyartifact:1.43.1
488credentials-binding:1.22
489credentials:2.3.7
490dashboard-view:2.12
491database-mysql:1.3
492database-postgresql:1.0
493database-sqlite:1.0
494database:1.5
495delivery-pipeline-plugin:1.4.2
496deploy:1.15
497deployment-notification:1.4
498description-setter:1.10
499display-console-output:1.0.5
500display-url-api:2.3.2
501docker-commons:1.16
502docker-workflow:1.23
503durable-task:1.34
504dynamic_extended_choice_parameter:1.0.1
505dynamicparameter:0.2.0
506email-ext:2.69
507emailext-template:1.1
508embeddable-build-status:2.0.3
509envinject-api:1.7
510envinject:2.3.0
511external-monitor-job:1.7
512extreme-feedback:1.7
513ftppublisher:1.2
514git-client:3.2.1
515git-parameter:0.9.12
516git-server:1.9
517git:4.2.2
518github-api:1.111
519github-branch-source:2.7.1
520github:1.29.5
521gitlab-hook:1.4.2
522google-oauth-plugin:1.0.0
523gradle:1.36
524handlebars:1.1.1
525htmlpublisher:1.22
526icon-shim:2.0.3
527jackson2-api:2.10.3
528javadoc:1.5
529jdk-tool:1.4
530jenkins-multijob-plugin:1.33
531jenkinswalldisplay:0.6.34
532job-dsl:1.77
533jobConfigHistory:2.25
534join:1.21
535jquery-detached:1.2.1
536jquery:1.12.4-1
537jsch:0.1.55.2
538junit:1.28
539kubernetes-client-api:4.9.1-1
540kubernetes-credentials:0.6.2
541kubernetes:1.24.1
542localization-support:1.1
543localization-zh-cn:1.0.14
544lockable-resources:2.7
545mailer:1.32
546managed-scripts:1.4
547mapdb-api:1.0.9.0
548mask-passwords:2.13
549matrix-auth:2.5
550matrix-groovy-execution-strategy:1.0.7
551matrix-project:1.14
552maven-plugin:3.6
553momentjs:1.1.1
554msbuild:1.29
555multiple-scms:0.6
556nodejs:1.3.5
557nuget:1.0
558oauth-credentials:0.4
559pam-auth:1.6
560parameterized-trigger:2.36
561pipeline-build-step:2.12
562pipeline-github-lib:1.0
563pipeline-graph-analysis:1.10
564pipeline-input-step:2.11
565pipeline-milestone-step:1.3.1
566pipeline-model-api:1.6.0
567pipeline-model-declarative-agent:1.1.1
568pipeline-model-definition:1.6.0
569pipeline-model-extensions:1.6.0
570pipeline-rest-api:2.13
571pipeline-stage-step:2.3
572pipeline-stage-tags-metadata:1.6.0
573pipeline-stage-view:2.13
574pipeline-utility-steps:2.5.0
575plain-credentials:1.7
576publish-over-cifs:0.13
577publish-over-ftp:1.15
578publish-over-ssh:1.20.1
579publish-over:0.22
580python-wrapper:1.0.3
581python:1.3
582resource-disposer:0.14
583robot:2.1.1
584role-strategy:2.16
585ruby-runtime:0.12
586run-condition:1.3
587scm-api:2.6.3
588script-security:1.71
589scriptler:3.1
590selenium-aes:0.5
591selenium-axis:0.0.6
592selenium-builder:1.14
593selenium:3.141.59
594seleniumhq:0.4
595seleniumhtmlreport:1.0
596seleniumrc-plugin:1.0
597shiningpanda:0.24
598simple-theme-plugin:0.6
599slave-proxy:1.1
600slave-setup:1.10
601sqlplus-script-runner:2.0.9
602ssh-credentials:1.18.1
603ssh-slaves:1.31.2
604ssh:2.6.1
605structs:1.20
606subversion:2.13.1
607svn-tag:1.18
608svnpublisher:0.1
609text-finder-run-condition:0.1
610throttle-concurrents:2.0.2
611timestamper:1.11.3
612token-macro:2.12
613trilead-api:1.0.6
614uno-choice:2.2.2
615utplsql:0.6.1
616variant:1.3
617versionnumber:1.9
618weblogic-deployer-plugin:4.1
619websphere-deployer:1.6.1
620workflow-aggregator:2.6
621workflow-api:2.40
622workflow-basic-steps:2.20
623workflow-cps-global-lib:2.16
624workflow-cps:2.80
625workflow-durable-task-step:2.35
626workflow-job:2.38
627workflow-multibranch:2.21
628workflow-scm-step:2.11
629workflow-step-api:2.22
630workflow-support:3.4
631ws-cleanup:0.38
632xcode-plugin:2.0.14
633xshell:0.10
```
