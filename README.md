# SRE Checklist

## SRE Team

- [ ] Having a team meeting

## SRE Lead 

- [ ] Is there is an onboarding page for SREs joining the team?
- [ ] Schedule 1:1 meeting with team (manager or lead?)
- [ ] Learn how others are doing it!
    - [ ] https://github.com/upgundecha/howtheysre - so many examples!

## Technologies

## Git Repositories

- [ ] Is there CI for every project?
  - [ ] Linting and Styling
  - [ ] Unit tests
  - [ ] E2E testing
- [ ] Infra is managed from code
  - [ ] IaC technology chosen and in use (Terraform, Ansible, Pulumi, etc.)

## Kubernetes 101

- [ ] Infra code (e.g. Manifests) is in a separate repository
- [ ] Apply/Add labels for every type of resources. Use this [page](https://kubernetes.io/docs/concepts/overview/working-with-objects/common-labels) as a suggestion to which labels you should be adding

## Migration from VM to Kubernetes

- [ ] Choose strategy
    - Deploy a new application on Kubernetes, in addition to the existing application on the VM and eventually route traffic to Kubernetes
