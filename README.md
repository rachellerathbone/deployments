# This is a basic workflow to help you get started with Actions

name: My Deployment flow

# Controls when the action will run.
on: [push]

# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
  deploy-to-dev1:
    runs-on: ubuntu-latest
    environment: trunk
    steps:
      - uses: actions/checkout@v3
        name: Create develop deployment
        id: deploy-to-dev1
        with:
          token: "${{ github.token }}"
          target_url: http://my-cool-app.com

  deploy-to-dev2:
    runs-on: ubuntu-latest
    environment: develop
    steps:
      - uses: actions/checkout@v3
        name: Create develop deployment
        id: deploy-to-dev2
        with:
          token: "${{ github.token }}"
          target_url: http://my-cool-app.com
