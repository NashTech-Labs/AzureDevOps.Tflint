# ADO Docker Template

This template uses the open source tflint available in github to lint test terraform modules

## Pipeline Requirements

The template pipeline requires the following parameters to be defined:

### Parameters:


| Name  | Displayname | Comments |
| ------------- | ------------- | ------------- |
| ModuleFolder | Location of Terraform Modules | This helps to identify files to lint test |
-----------------------------------------------------------------------------------------------------------------------
 
### How to Use:

  ```yaml
  # azure-pipeline.yml
  resources:
    repositories:
      - repository: TFlint
        type: github
        name: NashTech-Labs/AzureDevOps.Tflint
        ref: main
        endpoint: 'GitHubServiceConnection'

  steps:
    - template: azure-pipeline.yml@TFlint
        parameters:
            ModuleFolder: '.'
  ```