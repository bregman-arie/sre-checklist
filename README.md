# SRE Checklist

Purpose: Provide teams and individuals an idea on what to aspire for or what to take into consideration in the SRE field and work

Clarification: these checklists are **opinionated**. They are based on my own opinion and experience and are not universal truth. So you should definitely doubt whatever you read here and more than welcome to add your own opinion on the matter

## Team

### SRE Team

- [ ] Team responsibilities are clear for everyone
  - [ ] Managing infra (one can argue whether it's SRE or DevOps, but it depends on what functions the org has)
  - [ ] Monitoring

### SRE Goals 

- [ ] Set goals
  - [ ] Define SLO (Service Level Objective)
  - 100% reliability is not a good goal (not sustainable + not feasible since perhaps you can drive 100% reliability for the service you own but most of the time not for its dependencies)

### SRE Lead 

- [ ] Is there an onboarding page for SREs joining the team?
- [ ] Schedule 1:1 meeting with team (probably...manager or lead? TBD)
- [ ] Learn how others are doing it!
    - [ ] https://github.com/upgundecha/howtheysre - so many examples!
    - [ ] Personal favorite examples
      - [  ] [Enter the Abattoir](https://achievers.engineering/enter-the-abattoir-ee5e2019f0b3) - very cool idea of the SRE team to provide tooling around creation of "namespaces" - spaces with the all the components the dev team needs
- [ ] Identify Possible Gaps. Few things to watch our for:
  - [ ] Does development team waits on SRE for infra related operations?
  - [ ] Basically going over other check lists in this page :)
- [ ] Identify SRE team maturity and work on improving it
  - [ ] Operations: SRE is focused on resolving issues, dealing with request
  - [ ] Automation: SRE is moving towards automation and self-service. Providing tooling, documentation, etc.
  - [ ] Product: SRE is focused on improving the product itself - reliability, performances, etc.

## Technologies

### Git Repositories

- [ ] Is there CI for every project?
  - [ ] Linting and Styling
  - [ ] Unit tests
  - [ ] E2E testing
- [ ] Infra is managed from code
  - [ ] IaC technology chosen and in use (Terraform, Ansible, Pulumi, etc.)

### Cloud

- [ ] Resources managed through IaC technologies such as Terrform, Pulumti, etc.
- [ ] Resources are tagged, labeled
- [ ] Resources Quotas are set

### Kubernetes

- [ ] Apply/Add labels for every type of resources. You may use this [page](https://kubernetes.io/docs/concepts/overview/working-with-objects/common-labels) as a suggestion to which labels you should be adding
- [ ] CI/CD for Cluster bootstraping 
- [ ] CD process for manifests/configurations (using something like Flux, ArgoCD)
  - [ ] Make sure cluster bootstraping (the process of preparing the cluster) is managed fully using GitOps
- [ ] Cluster for each environment? Dev, QA, Staging, Production
- 
- [ ] Cluster Policy Management
  - [ ] Networking Policies
  - [ ] Storage Policies

### GitOps (e.g. ArgoCD)

- [ ] Infra code (Manifests, Configurations, etc.) is in a separate repository (and not in application repo)
- [ ] GitOps adopted
  - [ ] GitOps adopted also for GitOps agents themselves and not only for app related code
- [ ] Sync Strategy
  - [ ] Auto Prune (resources deleted when files/content deleted)
  - [ ] Self-heal (cluster state corrected based on Git state and when manual changes done to the cluster)
- [ ] How do you manage multiple clusters?
  - [ ] One ArgoCD to rule them all or ArgoCD on each cluster?

## Monitoring

TODO

## Chaos Engineering

TODO
