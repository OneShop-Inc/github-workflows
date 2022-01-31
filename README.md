# github-workflows
Reusable Github Actions workflows

`This repository must be public in order for other builds to access these workflows. Don't add anything secret here!`


## Calling a Reusable Workflow
Call a reusable workflow like this. Be sure to specify a version to guarantee consistent builds. 
```
jobs:
  apply:
    name: Apply
    uses: OneShop-Inc/github-workflows/.gitub/workflows/terraform_apply.yml@v1
...
```

More info [here](https://docs.github.com/en/actions/using-workflows/reusing-workflows#calling-a-reusable-workflow)

## Updating a Resuable Workflow
Create a branch, add your changes, and then test your changes by pointing another repo's github action at your branch. 
For example, after changing the `terraform/apply.yml` workflow in a branch called `updated-workflow`, you would update another repo like this:
```
jobs:
  apply:
    name: Apply
    uses: OneShop-Inc/github-workflows/.gitub/workflows/terraform_apply.yml@@updated-workflow
...
```

Once your change works, merge a PR into main and create a release tag. 
