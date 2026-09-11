# VCS Design + POC | GitLab Features

## Author Table

| **Author** | **Created on** | **Version** | **Last edited on** | **L0 Reviewer** | **L1 Reviewer** | **L2 Reviewer**        |
| ---------- | -------------- | ----------- | ------------------ | --------------- | --------------- | ---------------------- |
| Yogesh     | 10-09-26       | v1.0        | 10-09-26           | Liyakath/Aniruh | Aman Raj        | Sandeep Rawat/Ravindra |

---

## Table of Contents

1. [Introduction](#1-introduction)
2. [What is GitLab?](#2-what-is-gitlab)
3. [Why GitLab is Required?](#3-why-gitlab-is-required)
4. [GitLab Features](#4-gitlab-features)

   * 4.1 [Repository Management](#41-repository-management)
   * 4.2 [Branching and Merging](#42-branching-and-merging)
   * 4.3 [Merge Requests and Code Review](#43-merge-requests-and-code-review)
   * 4.4 [GitLab CI/CD](#44-gitlab-cicd)
   
5. [GitLab VCS Design](#5-gitlab-vcs-design)
6. [GitLab POC](#6-gitlab-poc)
7. [Advantages and Disadvantages](#7-advantages-and-disadvantages)
8. [Conclusion](#10-conclusion)
9. [Contact Information](#11-contact-information)
10. [References](#12-references)

---

# 1. Introduction

This document explains GitLab and its capabilities for managing source code, development workflows, collaboration, CI/CD, security, and project management.

It also demonstrates a GitLab-based workflow covering repository management, branching, Merge Requests, code review, CI/CD automation, access control, and deployment-related workflows.

---

# 2. What is GitLab?

GitLab is a platform built around Git that provides tools for managing source code and software development workflows.

It provides a centralized workspace where teams can manage:

* Source code
* Branches
* Merge Requests
* Code reviews
* Issues
* CI/CD pipelines
* Security
* Packages and container images
* Project access and permissions

A GitLab **Project** provides the development workspace, while the repository stores source code and its Git history.

GitLab can therefore be used to manage multiple stages of the software development lifecycle from a single platform.

---

# 3. Why GitLab is Required?

GitLab helps teams manage software development in a structured and controlled manner.

Without a centralized development platform, teams may face problems such as:

* Difficult collaboration
* Uncontrolled code changes
* Lack of code review
* Manual build and deployment processes
* Poor visibility of development work
* Improper access management
* Difficulty tracking issues
* Security risks in the development process

GitLab addresses these challenges by providing repository management, Merge Requests, CI/CD, issue tracking, access control, and security capabilities within one platform.

---

# 4. GitLab Features

## 4.1 Repository Management

GitLab provides Git repositories for storing and managing source code and its history.

| **Feature**  | **Description**                              |
| ------------ | -------------------------------------------- |
| Projects     | Central workspace for development activities |
| Repositories | Store source code and Git history            |
| Commits      | Record changes made to files                 |
| Tags         | Mark specific versions                       |
| Branches     | Maintain separate development lines          |
| Forks        | Create an independent copy of a project      |
| Web IDE      | Edit repository files through a browser      |
| Wiki         | Maintain project documentation               |

GitLab combines repository management with features such as Issues, Merge Requests, and CI/CD.

---

## 4.2 Branching and Merging

GitLab supports Git branching and provides controls for protecting important branches.

```text
                     GitLab Repository
                            |
                           main
                            |
              +-------------+-------------+
              |             |             |
        feature/login  feature/api   bugfix/db
              |             |             |
              +-------------+-------------+
                            |
                     Merge Request
                            |
                       Code Review
                            |
                           main
```

Important features include:

* Feature branches
* Protected branches
* Branch permissions
* Merge strategies
* Push restrictions
* Merge controls

Protected branches help prevent unauthorized or accidental changes to important branches.

---

## 4.3 Merge Requests and Code Review

GitLab uses **Merge Requests (MRs)** to review and merge code changes.

A Merge Request provides a central location for:

* Reviewing code
* Discussing changes
* Adding comments
* Tracking commits
* Checking CI/CD results
* Approving changes
* Merging branches

### Typical Workflow

```text
Developer
    |
    v
Feature Branch
    |
    v
Commit Changes
    |
    v
Push to GitLab
    |
    v
Create Merge Request
    |
    v
Code Review
    |
    v
CI/CD Pipeline
    |
    +---- Failed ----> Fix Changes
    |
    v
Approval
    |
    v
Merge
```

---

## 4.4 GitLab CI/CD

GitLab CI/CD automates activities such as:

* Building applications
* Running tests
* Performing checks
* Creating artifacts
* Building container images
* Deploying applications


### Important Components

| **Component** | **Purpose**                                  |
| ------------- | -------------------------------------------- |
| Pipeline      | Complete automation workflow                 |
| Stage         | Logical phase such as build, test, or deploy |
| Job           | Individual task executed by the pipeline     |
| Runner        | System that executes CI/CD jobs              |
| Variables     | Store configuration values                   |
| Artifacts     | Store files generated by jobs                |

---

## 4.5 Issues and Project Management

GitLab provides project-management capabilities for tracking development work.

| **Feature**    | **Purpose**                         |
| -------------- | ----------------------------------- |
| Issues         | Track bugs, tasks, and enhancements |
| Labels         | Categorize issues                   |
| Milestones     | Group work toward a target          |
| Issue Boards   | Visualize and manage work           |
| Epics          | Organize larger pieces of work      |
| Merge Requests | Track implementation and review     |

These features help teams plan, track, and manage development activities.

---

## 4.6 Access Control and Permissions

GitLab provides role-based access control for projects and groups.

Common roles include:

| **Role**   | **Purpose**                                  |
| ---------- | -------------------------------------------- |
| Guest      | Limited project interaction                  |
| Reporter   | View code and reports                        |
| Developer  | Develop code and create Merge Requests       |
| Maintainer | Manage branches, CI/CD, and project settings |
| Owner      | Full control over group/project resources    |

### Recommended Access Model

```text
GitLab Group
     |
     +---- Project A
     |
     +---- Project B
     |
     +---- Project C
     |
   Teams / Roles
     |
     +---- Developer
     +---- Maintainer
     +---- Owner
```

Access should follow the principle of least privilege.

---

## 4.7 Security Features

GitLab provides security capabilities that can be integrated into the software development lifecycle.

Examples include:

* Dependency scanning
* Vulnerability management
* Secret detection
* Security scanning
* Security policies
* Merge Request approval controls
* Protected branches
* Push rules
* Audit capabilities

Security controls can help identify vulnerabilities and prevent unauthorized changes.

---

## 4.8 Package and Container Registry

GitLab provides registries for storing packages, container images, and other build outputs.

A typical workflow is:

```text
Source Code
     |
     v
GitLab Repository
     |
     v
CI/CD Pipeline
     |
     v
Build Application
     |
     v
Build Container Image
     |
     v
GitLab Container Registry
     |
     v
Deploy
```

This allows source code, CI/CD, artifact storage, and deployment workflows to be connected.

---

# 5. GitLab VCS Design

A recommended GitLab-based development design is:

```text
                         GitLab
                            |
                       Organization
                            |
              +-------------+-------------+
              |             |             |
          Project A      Project B      Project C
              |
          Repository
              |
        +-----+-----+
        |           |
      main       develop
                   |
          +--------+--------+
          |        |        |
       feature   feature   bugfix
          |        |        |
          +--------+--------+
                   |
             Merge Request
                   |
              Code Review
                   |
               CI/CD Checks
                   |
                Approval
                   |
                 Merge
                   |
                  main
```

## Recommended Branch Strategy

```text
main
 |
 +---- develop
         |
         +---- feature/<feature-name>
         |
         +---- bugfix/<issue-name>
         |
         +---- hotfix/<issue-name>
```

### Branch Purpose

| **Branch**  | **Purpose**                        |
| ----------- | ---------------------------------- |
| `main`      | Production-ready code              |
| `develop`   | Integration of development changes |
| `feature/*` | New feature development            |
| `bugfix/*`  | Bug fixes                          |
| `hotfix/*`  | Urgent production fixes            |

The exact branching strategy should be selected according to the team's development and release process.

---

# 6. GitLab POC

## 6.1 Objective

The objective of this POC is to demonstrate a basic GitLab development workflow covering:

* GitLab project creation
* Repository cloning
* Branch creation
* Code changes
* Commit
* Push
* Merge Request
* Code review
* CI/CD pipeline
* Merge

---

## 6.2 Create GitLab Project

Create a project in GitLab.

Example:

```text
Project Name: vcs-gitlab-poc
Visibility: Private
```

---

## 6.3 Clone Repository

```bash
git clone <gitlab-repository-url>
cd vcs-gitlab-poc
```

---

## 6.4 Configure Git

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Verify:

```bash
git config --list
```

---

## 6.5 Create Feature Branch

```bash
git checkout -b feature/demo
```

Verify:

```bash
git branch
```

Expected:

```text
* feature/demo
  main
```

---

## 6.6 Create a File

```bash
echo "GitLab VCS POC" > README.md
```

Check the status:

```bash
git status
```

---

## 6.7 Commit Changes

```bash
git add README.md
git commit -m "Add GitLab VCS POC"
```

---

## 6.8 Push Feature Branch

```bash
git push -u origin feature/demo
```

The feature branch should now be available in GitLab.

---

## 6.9 Create Merge Request

Create a Merge Request in GitLab.

```text
Source:
feature/demo

Target:
main
```

Add:

* Title
* Description
* Reviewer
* Assignee

The Merge Request is used for code review and discussion before merging.

---

## 6.10 Add CI/CD Pipeline

Create:

```text
.gitlab-ci.yml
```

Example:

```yaml
stages:
  - test

test:
  stage: test
  script:
    - echo "Running GitLab CI/CD test"
    - echo "Tests passed"
```

Commit and push:

```bash
git add .gitlab-ci.yml
git commit -m "Add GitLab CI pipeline"
git push
```

GitLab should trigger the pipeline automatically.

---

## 6.11 Review and Merge

```text
Code Changes
     |
     v
Merge Request
     |
     v
CI/CD Pipeline
     |
     v
Code Review
     |
     v
Approval
     |
     v
Merge into main
```

After successful review and CI/CD checks, merge the Merge Request into `main`.

---

## 6.12 Verify

After merging:

```bash
git checkout main
git pull origin main
```

Check commit history:

```bash
git log --oneline
```

Check branches:

```bash
git branch -a
```

The merged changes should now be available in the `main` branch.

---

# 7. Advantages and Disadvantages

## Advantages

* **Centralized Development Platform** — Code, issues, Merge Requests, and CI/CD can be managed from one platform.
* **Code Review Workflow** — Merge Requests provide structured review and discussion.
* **Built-in CI/CD** — GitLab CI/CD can automate build, testing, and deployment.
* **Access Control** — Role-based permissions help control access.
* **Security Integration** — Security capabilities can be integrated into development workflows.
* **DevSecOps Support** — Development, security, and operations workflows can be connected.

## Disadvantages

* **Learning Curve** — New users need to understand Git and GitLab concepts.
* **Configuration Complexity** — Large organizations may require detailed configuration for groups, permissions, runners, and CI/CD.
* **Self-Managed Resource Requirements** — Self-managed GitLab requires management of upgrades, storage, backups, and availability.
* **Feature Availability** — Some advanced capabilities depend on the GitLab edition or subscription tier.

---

# 8. Use Cases

### Software Development

GitLab can be used to manage source code, branches, Merge Requests, and releases.

### CI/CD

GitLab CI/CD can automate application build, testing, and deployment.

### DevOps

Development and operations teams can connect source code, automation, infrastructure, and deployment workflows.

### DevSecOps

Security scanning and approval controls can be integrated into the software development lifecycle.

### Open Source Development

GitLab can support collaborative development using repositories, Issues, Merge Requests, and project-management capabilities.

### Enterprise Development

Organizations can use groups, projects, roles, protected branches, and approval workflows to manage large development teams.

---

# 9. Best Practices

* Protect the `main` branch.
* Use feature branches for development.
* Do not directly push unreviewed code to production branches.
* Use Merge Requests for code review.
* Require appropriate approvals before merging.
* Configure CI/CD checks for important branches.
* Use meaningful commit messages.
* Keep Merge Requests small and focused.
* Follow least-privilege access.
* Do not store passwords, API keys, or tokens in source code.
* Use protected CI/CD variables for sensitive configuration.
* Regularly review project and group permissions.
* Maintain repository backups where required.
* Use security scanning as part of the development workflow.

---

# 10. Conclusion

GitLab provides a centralized platform for managing source code, collaboration, code review, CI/CD, security, and project-management workflows.

The GitLab design and POC demonstrated a controlled development workflow where developers create feature branches, commit and push changes, create Merge Requests, perform code reviews, run CI/CD checks, and merge approved changes into the `main` branch.

By combining Git-based source control with GitLab's collaboration, automation, access-control, and security capabilities, teams can establish an efficient and traceable software development workflow.

---

# 11. Contact Information

| **Name** | **Email**                                                                         |
| -------- | --------------------------------------------------------------------------------- |
| Sahil    | [sahil.butola.snaatak@mygurukulam.co](mailto:sahil.butola.snaatak@mygurukulam.co) |

---

# 12. References

| **Topic**                    | **Description**                              |
| ---------------------------- | -------------------------------------------- |
| GitLab Documentation         | Official GitLab documentation                |
| GitLab Manage Code           | Repository and code-management documentation |
| GitLab Merge Requests        | Merge Request and code-review documentation  |
| GitLab Permissions           | GitLab roles and permissions                 |
| GitLab Repository Protection | Protected branches and repository security   |
