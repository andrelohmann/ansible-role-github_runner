github_runner
=============

Install github runner

  * https://docs.github.com/en/free-pro-team@latest/actions/hosting-your-own-runners/about-self-hosted-runners
  * https://docs.github.com/en/free-pro-team@latest/actions/hosting-your-own-runners/adding-self-hosted-runners
  * https://docs.github.com/en/free-pro-team@latest/actions/hosting-your-own-runners/configuring-the-self-hosted-runner-application-as-a-service
  * https://github.com/actions/runner
  * https://medium.com/@gjgd/create-your-self-hosted-github-action-runner-in-5-minutes-a9eff615edc4

To create a new organization runner, you need to visit your organization path (https://github.com/__YOUR_ORGANIZATION__) -> Settings -> Actions -> Self-hosted runners -> Add new

Role Variables
--------------

    github_runner_organization: __YOUR_ORGANIZATION__
    github_runner_token: __YOUR_TOKEN__
    github_runner_name: __RUNNER_NAME__
    github_runner_labels:
    - label1
    - label2

Example Playbook
----------------

    - hosts: github_runner
      roles:
      - github_runner

License
-------

MIT

Author Information
------------------

https://github.com/andrelohmann
