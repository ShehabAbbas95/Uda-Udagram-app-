
# Overview
usbing CircliCi version: 2.1 in Our deployment process
orbs:
  # orbs contain basic recipes and reproducible actions (install node, aws, etc.)
  node: circleci/node@5.0.0
  # different jobs are calles later in the workflows sections
jobs:
  build:
    docker:
      # the base image can run most needed actions with orbs
      - image: "cimg/base:stable"
    steps:
    # Install node 
      - node/install
    # Install aws cli
      - aws-cli/setup
      - checkout
    # install dependencies in both apps
      - run:
          name: Install Front-End Dependencies
          command: |
              npm run frontend_dep:install
      - run:
          name: Front-End Lint
          command: |
              npm run frontend:lint
    # Script for test
        - run:
        name: Front-End Test
        command: |
            npm run frontend:test
    # Build the App
      - run:
          name: Front-End Build
          command: |
              npm run frontend:build
    # Install dependencies and Build the backend api
      - run:
          name: Install Back-End Dependencies
          command: |
             npm run backend_dep:install
      - run:
          name: Back-End Build
          command: |
             npm run backend:build
    # Deploy the Frontend 
      - run:
          name: Front-End Deploy
          command: |
             npm run frontend:deploy
      
workflow:
  - Install Node, AWS and NPM. 
  - Test and Build the code.
  - Deploy
  - Run Server