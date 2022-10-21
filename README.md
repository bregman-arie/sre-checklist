# SRE Checklist

## SRE Team

- [ ] Team responsibilities are clear for everyone
  - [  ] Managing infra (one can argue whether it's SRE or DevOps, but it depends on what functions the org has)

## SRE Goals 

- [ ] Set goals
  - [ ] Define SLO (Service Level Objective)
  - 100% reliability is not a good goal (not sustainable + you can't drive for 100% reliability also for application/system dependencies)

## SRE Lead 

- [ ] Is there an onboarding page for SREs joining the team?
- [ ] Schedule 1:1 meeting with team (manager or lead?)
- [ ] Learn how others are doing it!
    - [ ] https://github.com/upgundecha/howtheysre - so many examples!
    - [ ] Personal favorite examples
      - [  ] [Enter the Abattoir](https://achievers.engineering/enter-the-abattoir-ee5e2019f0b3) - very cool idea of the SRE team to provide tooling around creation of "namespaces" - spaces with the all the components the dev team needs
- [ ] Identify Possible Gaps. Few ideas:
  - [ ] Does development team waits on SRE for infra related operations?
  - [ ] Basically going over other check lists in this page :)
- [ ] Identify SRE team maturity and work on improving it
  - [ ] Operations: SRE is focused on resolving issues, dealing with request
  - [ ] Automation: SRE is moving towards automation and self-service. Providing tooling, documentation, etc.
  - [ ] Product: SRE is focused on improving the product itself - reliability, performances, etc.

## Technologies

## Git Repositories

- [ ] Is there CI for every project?
  - [ ] Linting and Styling
  - [ ] Unit tests
  - [ ] E2E testing
- [ ] Infra is managed from code
  - [ ] IaC technology chosen and in use (Terraform, Ansible, Pulumi, etc.)

## Kubernetes

- [ ] Infra code (e.g. Manifests) is in a separate repository (and not in app repo)
- [ ] Apply/Add labels for every type of resources. Use this [page](https://kubernetes.io/docs/concepts/overview/working-with-objects/common-labels) as a suggestion to which labels you should be adding
- [ ] CD process for manifests/configurations (using something like Flux, ArgoCD)

## Microservices

- [ ] Ease development of microservices with [tilt.dev](https://tilt.dev) - Optional
