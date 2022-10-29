# SRE Checklist

Purpose: Provide teams and individuals an idea on what to aspire for or what to take into consideration in the SRE field and work

Clarification: these checklists are **opinionated**. They are based on my own opinion and experience and are not universal truth (duh! :)).
So you should definitely doubt whatever you read here and more than welcome to add your own opinion on the matter by starting a discussion or proposing a change to the project

- [SRE Checklist](#sre-checklist)
  - [Team](#team)
    - [SRE Team](#sre-team)
      - [Skills](#skills)
      - [Responsibilities](#responsibilities)
      - [Processes](#processes)
    - [SRE Team Goals](#sre-team-goals)
    - [SRE Lead](#sre-lead)
    - [New SRE Team Member](#new-sre-team-member)
  - [Technologies](#technologies)
    - [Git Repositories](#git-repositories)
    - [Cloud](#cloud)
    - [Kubernetes](#kubernetes)
    - [GitOps - ArgoCD](#gitops---argocd)
    - [Monitoring](#monitoring)
    - [Chaos Engineering](#chaos-engineering)
    - [IaC](#iac)
    - [Terraform](#terraform)

## Team

### SRE Team

#### Skills

- [ ] **Must**
    - [ ] Coding
      - It doesn't matter what language! it seems market right now leaning towards Go mostly, for SRE and Devops, but Python is also quite common and eventually whatever works best for the team is what matters
- [ ] **Optional** (depends on your environment, technology stack, etc.)
    - [ ] Containers
    - [ ] Kubernetes
    - [ ] Cloud
    - [ ] CI/CD

#### Responsibilities

- [ ] **Decide on responsibilities**
  - Common
    - [ ] Infrastructure management
    - [ ] Monitoring
    - [ ] Incident Management
    - [ ] Infra and Reliability related automation
  - [ ] Arguable
    - [ ] App Performance - Arguable because some organizations treat it as dev responsibility
- [ ] **Documented/Written**
  - Make sure to write down the responsibilities of the team somewhere. That will be useful for many things like new members joining, recuriting, clarity for the organization and more

#### Processes

- [ ] Incident Management
  - There must be a well defined process to how incidents are managed. Some thoughts:
    - Where incidents are reported/raised?
    - Who monitors the alerts at any given point of time?
    - Do you need 100% time coverage?
    - Is there any team that gets the alerts before the SRE team and tries to handle the issue?
  - Is the process automated?
    - [ ] Do you need to manually open a ticket?
    - [ ] Do you need to go to incidents platform/page or do you get an alert?
    - [ ] Do you schedule a meeting to talk about 

### SRE Team Goals 

- [ ] Set goals
  - [ ] Define SLO (Service Level Objective)
  - 100% reliability is not a good goal! (not sustainable + not feasible. One example: maybe you can drive 100% reliability for the service you own, but most of the time not for its dependencies)

### SRE Lead 

- [ ] Is there an onboarding page for SREs joining the team?
- [ ] Schedule 1:1 meeting with team (probably...manager or lead? TBD)
- [ ] Identify Possible Gaps. Few things to watch our for:
  - Does development team waits on SRE for infra related operations?
  - Basically going over other check lists in this page :)
- [ ] Identify SRE team maturity and work on improving it
  - [ ] Step 1: Operations: SRE is focused on resolving issues, dealing with requests
    - At this step you'll be mainly focused on making sure you and the team are able to respond to any issue raised
    - Slowly you'll automated processes, fixes and move towards step 2
  - [ ] Step 2: Automation: SRE is moving towards automation and self-service. Providing tooling, documentation, etc.
  - [ ] Step 3: Product: SRE is focused on improving the product itself - reliability, performances, etc.
- [ ] Keep learning ALL THE TIME
  - [ ] Learn how others are doing it!
    - https://github.com/upgundecha/howtheysre - so many good examples!

### New SRE Team Member

- Welcome :)
- Have a mentor? Great. If not, ask for one
- [ ] Do the onboarding
    -  No onboarding? maybe you can be the first to add one
- [ ] Learn about the product
  - What it does?
  - Is it SaaS? On-Premise? ...
  - How it's delivered and deployed?
- [ ] Time to deep dive into operations
  - TODO: add some items :)

## Technologies

### Git Repositories

- [ ] Is there CI for every project?
  - [ ] Linting and Styling
  - [ ] Unit tests
  - [ ] E2E testing
- [ ] Least Privilge and Zero Trust
  - [ ] Make sure only people from team/company have access to the repositories

### Cloud

- [ ] Resources managed through IaC technologies such as Terrform, Pulumti, etc.
- [ ] Resources are tagged, labeled
  - [ ] Env (staging, prod, dev)
- [ ] Resources Quotas are set (no one wants to hit high bills)
- [ ] No single point of failure
  - [ ] Resources deployed across availability zones, regions, etc.
- [ ] Environment for Dev/Staging and a separate one for production

### Kubernetes

- [ ] Apply/Add labels for every type of resources. You may use this [page](https://kubernetes.io/docs/concepts/overview/working-with-objects/common-labels) as a suggestion to which labels you should be adding
- [ ] CI/CD for Cluster bootstraping 
- [ ] CD process for manifests/configurations (using something like Flux, ArgoCD)
  - [ ] Make sure cluster bootstraping (the process of preparing the cluster) is managed fully using GitOps
- [ ] Cluster for each environment? Dev, QA, Staging, Production
  - [ ] Per region? Per cloud? How distributed your environment should be? 
- [ ] Cluster Policy Management
  - [ ] Networking Policies
  - [ ] Storage Policies

### GitOps - ArgoCD

- [ ] GitOps adopted for application deployments and rollouts
  - [ ] Infra code (Manifests, Configurations, etc.) is in a separate repository (and not in application repository)
- [ ] GitOps adopted for GitOps agents themselves and not only for app related code
  - [ ] DON'T install ArgoCD with kubectl commands
  - [ ] Helm chart not recommended as it lags behind official releases of new ArgoCD releases
  - [ ] Consider:
    - [ ] Hosted Argo CD instance (pros: maintenance is on others. cons: make sure you have some money in the wallet)
    - [ ] ArgoCD for managing ArgoCD (pros: easy DR, rollbacks, ... and full audit and changelog. cons: maintenance)
      - [ ] Consider using [Argo CD Pilot](https://argocd-autopilot.readthedocs.io/en/stable) for that which is "opinionated way of installing Argo-CD and managing GitOps repositories"
  - [ ] Think about:
    - [ ] One ArgoCD to control multiple clusters (why not: single point of failure)
    - [ ] Argo CD per cluster (why not: a lot of maintenance and basically over complexity)
- [ ] Sync Strategy
  - [ ] Auto Prune (resources deleted when files/content deleted)
  - [ ] Self-heal (cluster state corrected based on Git state and when manual changes done to the cluster)

### Monitoring

TODO

### Chaos Engineering

The interesting topic of ensuring your environment can withstand unexpected disruptions

TODO: insert a list of steps to go towards the process of establishing and integrating chaos engineering in your environment

### IaC

  - [ ] Follow DRY (Don't Repeat Yourself) principle as in make sure there are no code duplication so when you change parameter's value for example, you don't need to change it in two different place

### Terraform

  - **Terraform Code**
    - [ ] Variables have description (to document what they are used for)
    - [ ] Set lifecycle "prevent_destroy" on resources that should never be deleted (e.g. Terraform state source like S3 bucket)
  - **CI/CD**
    - [ ] CI to test Terraform changes (syntax, lint, ...)
      - Consider inserting cost considerations (e.g. test whether a change will raise the bill significantly if you are using a public cloud)
    - [ ] CD to deploy apply Terraform changes
  - **State**
    - [ ] Stored in a private secured location
      - [ ] Encrypted
      - [ ] Public access blocked
    - [ ] Stored in a shared location as it may be updated by different team members
    - [ ] Backed up (e.g. by having versioning)
    - [ ] Never edited directly/manually (as it should be managed and updated by Terraform itself as part of the Terraform lifecycle)