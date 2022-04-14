# Ponicode Documentation


## Prerequisites 

- Install Ruby (https://www.ruby-lang.org/en/documentation/installation/)
- Install Jekyll (https://jekyllrb.com/docs/installation/)

## Install

```
npm run install-local
```

## Run locally 

```
npm start
```

## Deployment


> Deployment is managed by Netlify, using [@BeFunes](mailto:benedetta@circleci.com)'s personal account (in order to keep the plan free).
### Preprod

Deployment on [ponicode-docs-dev.netlify.app](https://ponicode-docs-dev.netlify.app/) is triggered by any push on `dev` in the repository [OTHER_docs](https://github.com/ponicode/OTHER_docs).

The Github Action Workflow `deploy_preprod` copies the content of this repo into [OTHER_docs](https://github.com/ponicode/OTHER_docs) (`dev` branch), thus triggering deployment.
### Prod

Deployment on [docs.ponicode.com](https://docs.ponicode.com) is triggered by any push on `master` in the repository [OTHER_docs](https://github.com/ponicode/OTHER_docs).

The Github Action Workflow `deploy_prod` copies the content of this repo into [OTHER_docs](https://github.com/ponicode/OTHER_docs) (`master` branch), thus triggering deployment.