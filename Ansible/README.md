# Ansible Mini Project

# What it does?
- Install Apache2 on EC2
- Start and enabled service

# What is apt
- apt is used for ubuntu to manage packages

## Idempotent 
- Runinnig same playbook multiple times won't break anything. Ansible checks for state

## Notify
- if this task makes a changes eg. if file content is new or updated then triggers the handler name
- if file is same as before then no handler triggers

## Handlers
- handlers do respond when another task notify them
- run at end of the playbook not immediately		
