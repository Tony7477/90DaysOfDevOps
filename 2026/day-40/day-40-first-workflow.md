## First workflow.yaml

## Anatomy of what each step does in the yaml file

```yaml
name: ci-cd-pipeline
on:
  workflow_dispatch:

jobs:
  code:
    runs-on: ubuntu-latest
    steps:
      - name: Clone the code
        run: echo "cloning the code"
  build:
    needs: [code]
    runs-on: ubuntu-latest
    steps:
      - name: Build using the docker
        run: echo "build using the docker"
  test:
    needs: [build]
    runs-on: ubuntu-latest
    steps:
      - name: Running the test cases
        run: echo "Testing the app"

  deploy:
    needs: [build, test]
    runs-on: ubuntu-latest
    steps:
      - name: Deploying on the machine
        run: echo "Deploying the code"
```


## dissection of above yml

on : tells on which condition (push , pull request, workflow-dispatch) I need to trigger .
under jobs : code --> build --> test --> deploy
- build depend upon code.
- test depend upon build.
- deploy depend upon build and test.
- in each job code runs on ubuntu-latest
- whatever the build created in one job dissapers here in next job.(better to do in steps )
- run : runs the following cmd
- steps are in sequential in order .