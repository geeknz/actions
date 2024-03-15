# GitHub Actions Repository

This repository contains a collection of GitHub Actions designed to automate various tasks and workflows. Below is a description of the currently available actions and how to use them.

## Actions

### 1. AWS SSM Send Command

Send a command to an AWS EC2 instance using AWS Systems Manager (SSM).

#### Inputs

- `aws-region`: The AWS region of the EC2 instance (required).
- `instance-id`: The ID of the target EC2 instance (required).
- `document-name`: The name of the SSM document to use (required).
- `command`: The command to execute on the EC2 instance (required).

#### Outputs

- `command-id`: The ID of the executed command.
- `result`: The result of the command execution.

#### Example Usage

```yaml
- name: AWS SSM Send Command
  uses: geeknz/actions/aws-ssm-send-command@v1.0.0
  with:
    aws-region: 'us-east-1'
    instance-id: 'i-1234567890abcdef0'
    document-name: 'AWS-RunShellScript'
    command: 'echo Hello, World!'
```

### 2. AWS SSM Send Command (PowerShell)

Send a PowerShell script to an AWS EC2 instance using AWS Systems Manager (SSM).

#### Inputs

- `aws-region`: The AWS region of the EC2 instance (required).
- `instance-id`: The ID of the target EC2 instance (required).
- `script`:  The PowerShell script to execute (required).
- `disable-error-handling`: Optionally disable error handling in the script (default: false).

#### Outputs

- `command-id`: The ID of the executed command.
- `result`: The result of the command execution.

#### Example Usage

```yaml
- name: AWS SSM Send Command (PowerShell)
  uses: geeknz/actions/aws-ssm-send-command-powershell@v1.0.0
  with:
    aws-region: 'us-east-1'
    instance-id: 'i-1234567890abcdef0'
    disable-error-handling: 'false'
    script: |
      Write-Output "Hello, PowerShell!"
```
