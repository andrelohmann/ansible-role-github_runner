andrelohmann.github_runner
==========================

Install github runner

  * https://docs.github.com/en/free-pro-team@latest/actions/hosting-your-own-runners/about-self-hosted-runners
  * https://docs.github.com/en/free-pro-team@latest/actions/hosting-your-own-runners/adding-self-hosted-runners
  * https://docs.github.com/en/free-pro-team@latest/actions/hosting-your-own-runners/configuring-the-self-hosted-runner-application-as-a-service
  * https://github.com/actions/runner
  * https://medium.com/@gjgd/create-your-self-hosted-github-action-runner-in-5-minutes-a9eff615edc4

This role installs a new private github runner for your organization.

This role can be used in two ways, either use a registration token (valid for one hour) or use a personal access token and fetch the registration token at runtime.

1)

To receive a registration token for your organization, got to Settings -> Actions -> Self-hosted runners -> Add new. Select your OS and architecture and copy the token. Be aware, that the token is only valid for one hour.

2)

To fetch a github runner registration token at runtime from the api, the authentication with a personal access token with "admin:org" permissions is neccessary. Generate this personal access token at Settings -> Developer settings -> Personal access tokens -> Generate new token. Select scopes __admin:org__.

Role Variables
--------------

    # 1) Use either the registration token
    github_runner_registration_token: __YOUR_ORGANIZATION_REGISTRATION_TOKEN__
    # 2) Or use a personal access token
    github_runner_pat: __YOUR_PERSONAL_ACCESS_TOKEN__
    # necessary variables
    github_runner_organization: __YOUR_ORGANIZATION__
    github_runner_name: __RUNNER_NAME__
    github_runner_labels:
    - label1
    - label2

Optionsl Variables
------------------

    github_runner_delete_existing: True

If an equally named runner already exists on the organization, it will be delted first, based on the github_runner_delete_existing variable setting (defaults to True).

Example Playbook
----------------

    - hosts: github_runner
      roles:
      - andrelohmann.github_runner

License
-------

MIT

Author Information
------------------

https://github.com/andrelohmann
