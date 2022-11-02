<p align="center">
<img src="images/sre_checklist.png"/>
</p>

:dart: **Repository Purpose**: Provide teams and individuals an idea on what to aspire for or what to take into consideration in the SRE field and work

**Note**: these checklists are **opinionated**. They are based on my own opinion and experience and are not universal truth (duh! :smile:).
So you should definitely doubt anything you read here and you are more than welcome to add your own opinion on the matter, by starting a discussion or proposing a change to the project

:construction: You may say this repository is still in progress. I wouldn't treat it as complete source at this point or anything close to that

- [Team :couple:](#team-couple)
  - [Responsibilities](#responsibilities)
  - [Skills](#skills)
    - [Must](#must)
    - [Optional](#optional)
  - [Processes](#processes)
  - [SRE Team Goals](#sre-team-goals)
  - [SRE Lead](#sre-lead)
  - [New SRE Team Member](#new-sre-team-member)
- [Technologies :computer:](#technologies-computer)
  - [Git Repositories](#git-repositories)
    - [CI](#ci)
    - [Security](#security)
    - [Automation](#automation)
  - [Cloud](#cloud)
    - [Provisioning](#provisioning)
    - [Tracking and Monitoring](#tracking-and-monitoring)
    - [Management](#management)
    - [Reliability](#reliability)
  - [Kubernetes](#kubernetes)
    - [Resource Management](#resource-management)
    - [CI/CD](#cicd)
    - [Cluster Management](#cluster-management)
  - [GitOps - ArgoCD](#gitops---argocd)
    - [Git Repositories](#git-repositories-1)
    - [GitOps Management](#gitops-management)
    - [Sync Strategy](#sync-strategy)
  - [Monitoring](#monitoring)
  - [Chaos Engineering](#chaos-engineering)
  - [IaC](#iac)
    - [The Chosen One](#the-chosen-one)
    - [Implementation](#implementation)
  - [Terraform](#terraform)
    - [Development and CI/CD](#development-and-cicd)
    - [State](#state)
    - [Terraform Projects File Structure](#terraform-projects-file-structure)
    - [Terraform Code](#terraform-code)
      - [Modules](#modules)
    - [Git](#git)

## Team :couple:

### Responsibilities

- [ ] **Decide on responsibilities**
  - Common
    - [ ] Infrastructure management
    - [ ] Monitoring
    - [ ] Incident Management
    - [ ] Infra and Reliability related automation
  - [ ] Arguable
    - [ ] App Performance - Arguable because some organizations treat it as dev responsibility
- [ ] **Documented/Written**
  - Make sure to write down the responsibilities of the team somewhere. That will be useful for many things like new members joining, recruiting, clarity for the organization and more.

### Skills

#### Must

- [ ] Coding
  - It doesn't matter what language! it seems market right now leaning towards Go mostly, for SRE and Devops, but Python is also quite common and eventually whatever works best for the team is what matters
- [ ] Monitoring
  - To achieve good reliability and improve it, monitoring should be performed continuously. This makes it to quite critical skill to own
- [ ] CI/CD
  - CI/CD today is integrated in every development process, whether it's of the application itself or the automation and infra managed by SRE and DevOps teams
- [ ] IaC, CM
  - IaC and CM is how you manage infra and operations through code. If you do your work as SRE manually and using ad-hoc commands or UI, you probably want to reconsider your approach and obtain some IaC (Infrastructure as Code) and CM (configuration management) skills and knowledge


#### Optional

These very much depends on your environment, technology stack, etc.

- [ ] Containers
- [ ] Kubernetes
- [ ] Cloud
- [ ] Virtualization

### Processes

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
    - In this step you focus on building the mindset of automating fixes, documenting what the team and others parties in the organization should be aware of
    - This step is probably the most long one. Don't expect to achieve it in short time, just make sure you have consistent progress towards next step
  - [ ] Step 3: Product: SRE is focused on improving the product itself - reliability, performances, etc.
    - Congratulations. Processes are automated, you respond quickly to issue, .., you are living the dream. Now you can go deeper and focus on the product itself
    - This not for everyone but definitely a feasible step and one to aspire for
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

## Technologies :computer:

### Git Repositories

#### CI

  - [ ] Is there CI for every project?
    - [ ] Linting and Styling
    - [ ] Unit tests
    - [ ] E2E testing

#### Security

- [ ] Least Privilege and Zero Trust
  - [ ] Make sure only people from team/company have access to the repositories

#### Automation

  - [ ] This is quite advanced but still, you may want to consider automating repositories creation and access control (using technologies like Terraform or programming languages, you can automate fully the process of repositories management)

### Cloud

#### Provisioning

- [ ] Resources managed through IaC technologies such as Terrform, Pulumti, etc.

#### Tracking and Monitoring

  - [ ] Resources are tagged, labeled
    - [ ] Env (staging, prod, dev)

#### Management

- [ ] Resources Quotas are set (no one wants to hit high bills)
- [ ] Environment for Dev/Staging and a separate one for production

#### Reliability

- [ ] No single point of failure
  - [ ] Resources deployed across availability zones, regions, etc.

### Kubernetes

#### Resource Management

- [ ] Apply/Add labels for every type of resources. You may use this [page](https://kubernetes.io/docs/concepts/overview/working-with-objects/common-labels) as a suggestion to which labels you should be adding

#### CI/CD
  - [ ] CI/CD for Cluster bootstraping
  - [ ] CD process for manifests/configurations (using something like Flux, ArgoCD)
    - [ ] Make sure cluster bootstraping (the process of preparing the cluster) is managed fully using GitOps

#### Cluster Management

- [ ] Cluster for each environment? Dev, QA, Staging, Production
  - [ ] Per region? Per cloud? How distributed your environment should be?
- [ ] Cluster Policy Management
  - [ ] Networking Policies
  - [ ] Storage Policies

### GitOps - ArgoCD

#### Git Repositories

- [ ] Infra code (Manifests, Configurations, etc.) is in a separate repository (and not in application repository)

#### GitOps Management

- [ ] **GitOps adopted for GitOps agents themselves and not only for app related code and infra**
  
- [ ] DON'T install ArgoCD with kubectl commands
- [ ] Helm chart not recommended as it lags behind official releases of new ArgoCD releases
- [ ] Consider:
  - [ ] Hosted Argo CD instance (pros: maintenance is on others. cons: make sure you have some money in the wallet)
  - [ ] ArgoCD for managing ArgoCD (pros: easy DR, rollbacks, ... and full audit and changelog. cons: maintenance)
    - [ ] Consider using [Argo CD Pilot](https://argocd-autopilot.readthedocs.io/en/stable) for that which is "opinionated way of installing Argo-CD and managing GitOps repositories"
- [ ] Think about:
  - [ ] One ArgoCD to control multiple clusters (why not: single point of failure)
  - [ ] Argo CD per cluster (why not: a lot of maintenance and basically over complexity)

#### Sync Strategy

- [ ] Auto Prune (resources deleted when files/content deleted)
- [ ] Self-heal (cluster state corrected based on Git state and when manual changes done to the cluster)

### Monitoring

- [ ] Choose monitoring solution
  - If you can afford it, go for ready monitoring solutions like DataDog, NewRelic, ...
  - Be aware of maintenance and how much time you are willing to invest in maintaining monitoring solution

### Chaos Engineering

The interesting topic of ensuring your environment can withstand unexpected disruptions

TODO: insert a list of steps to go towards the process of establishing and integrating chaos engineering in your environments

### IaC

#### The Chosen One

- Things to consider when choosing IaC technology:
  - Maturity (new vs. well established and known)
  - Community and support
  - Number of integrations, plugins, providers, modules, ...

#### Implementation

- [ ] Follow DRY (Don't Repeat Yourself) principle as in make sure there are no code duplication so when you change parameter's value for example, you don't need to change it in two different place
- [ ] Readable code - use naming conventions, formatting, ... make sure anyone can read the code and doesn't suffer much in doing so :)

### Terraform

#### Development and CI/CD

  - [ ] CI pipeline to test Terraform changes (syntax, lint, ...)
    - Consider inserting cost considerations (e.g. test whether a change will raise the bill significantly if you are using a public cloud)
  - [ ] CD pipeline to deploy/apply Terraform changes after the change is merged
  - To apply changes as part of a pull request (without merging a change) you can use something like [Atlantis](https://www.runatlantis.io)
    - This way you can avoid using local configurations and credentials

#### State

- [ ] Stored in a private secured location
  - [ ] Encrypted
  - [ ] Public access blocked
- [ ] Stored in a shared location as it may be updated by different team members
- [ ] Backed up (e.g. by having versioning)
- [ ] Never edited directly/manually (as it should be managed and updated by Terraform itself as part of the Terraform lifecycle)

#### Terraform Projects File Structure

- [ ] Separate directory for each environment (staging, production, ...)
- [ ] Separate backend for each environment (as you don't want share the same authentication and access controls for all environments)
- [ ] Separate directory in each environment for each component and application

  ```
  staging/
    networking/
    applications/
    databases/

  production/
    networking/
    applications/
      web-app-1/
      web-app-2/
    databases/
      mongo/
      mysql/

  global/
    user_access_management/

  modules/
    applications/
      web-app-1/...
  ```

- [ ] You don't put everything in main.tf
  -  Terraform configuration files themselves can be organized in many ways
  - Possible files:
    - main.tf
    - outputs.tf
    - variables.tf
    - providers.tf
    - dependencies.tf
  - Files can be further divided (avoid managing very long files)



#### Terraform Code

- [ ] Variables have description (to document what they are used for)
- [ ] Set lifecycle "prevent_destroy" on resources that should never be deleted (e.g. Terraform state source like S3 bucket)
- [ ] Try not including shell scripts inline (some tend to grow quite a lot over time). Use instead templatefile function to render a script from a file
- [ ] No hardcoded repeated values (common examples are ports, CIDR blocks, etc.). Instead use the concept of `locals`
- [ ] Prefer using `for_each` instead of `count`. `count` is very limited in modifying lists as it uses list position/index to rely on while `for_each` is map, set based so it based on specific keys
- [ ] Consistent naming, code style conventions and formatting
- [ ] Set tagging standards
  - [ ] Decide on which tags to use. Some ideas:
    - owner (team, department, ...)
    - generted_by/managed_by/... = "terraform"
  - [ ] Rather than specifying tags for each resources, consider setting them at provder level with `default_tags`. This will help you manage tags at scale

##### Modules

- [ ] Avoid duplication of Terraform code/configuration by using modules
- [ ] Tend to make modules reusable by for example not including provider code in reusable module
- [ ] Avoid hardcoding values, especially in the case reusable modules. To make them reusable, values will have to come from input variables
- [ ] Consider using only separate resources in a module and not inline blocks as they may limit you at some point or another when reusing the module
- [ ] Don't use relative paths! use `path references` (e.g. `path.module`, `path.root`)
- [ ] Try avoiding using latest version of a module. Instead stick for example to tags.
  - [ ] Branches can be also used, but since anyone can introduce a change to them, they considered less stable than tags

#### Git

- Recommended repositories:
  - [ ] Repository for modules
  - [ ] Repository for environments (this repository makes use of the modles repository mentioned above)
- [ ] Consider using tags
  - [ ] They can be used for specifying specific version of modules 