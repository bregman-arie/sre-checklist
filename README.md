# SRE Checklist

## SRE Team

- [ ] Team responsibilities are clear for everyone
  - [  ] Managing infra (one can argue whether it's SRE or DevOps, but it depends on what functions the org has)

## SRE Lead 

- [ ] Is there is an onboarding page for SREs joining the team?
- [ ] Schedule 1:1 meeting with team (manager or lead?)
- [ ] Learn how others are doing it!
    - [ ] https://github.com/upgundecha/howtheysre - so many examples!
    - [ ] Personal favorite examples
      - [  ] [Enter the Abattoir](https://achievers.engineering/enter-the-abattoir-ee5e2019f0b3) - very cool idea of the SRE team to provide tooling around creation of "namespaces" - spaces with the all the components the dev team needs
- [ ] Identify Gaps. Few ideas:
  - [ ] Does development team waits on SRE for infra related operations?

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

### Migration from VM to Kubernetes

- [ ] Choose strategy
    - Deploy a new application on Kubernetes, in addition to the existing application on the VM and eventually route traffic to Kubernetes

## Microservices

- [ ] Ease development of microservices with [tilt.dev](https://tilt.dev)
