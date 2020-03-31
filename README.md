[![CircleCI Build Status](https://img.shields.io/circleci/project/TheBause/docker-atlassian-jira-software/master.svg?label=CircleCI)](https://circleci.com/gh/TheBause/docker-atlassian-jira-software)[![Stars on Docker Hub](https://img.shields.io/docker/stars/craigbow777/atlassian-jira.svg)](https://hub.docker.com/r/cptactionhank/atlassian-jira-software/) [![Pulls on Docker Hub](https://img.shields.io/docker/pulls/craigbow777/atlassian-jira.svg)](https://hub.docker.com/r/cptactionhank/atlassian-jira-software/)

> HEADS UP! The `latest` tag and versions above 7.7.1 will be switching to use Alpine versions of OpenJDK as the base image.

# Atlassian JIRA Software in a Docker container

This is a containerized installation of Atlassian JIRA Software with Docker, and it's a match made in heaven for us all to enjoy. The aim of this image is to keep the installation as straight forward as possible, but with a few Docker related twists. You can get started by clicking the appropriate link below and reading the documentation.

* [Atlassian JIRA Core](https://cptactionhank.github.io/docker-atlassian-jira)
* [Atlassian JIRA Software](https://cptactionhank.github.io/docker-atlassian-jira-software)
* [Atlassian JIRA Service Desk](https://cptactionhank.github.io/docker-atlassian-jira-service-desk)
* [Atlassian Confluence](https://cptactionhank.github.io/docker-atlassian-confluence)

If you want to help out, you can check out the contribution section further down.

## I'm in the fast lane! Get me started

To quickly get started running a JIRA Software instance, use the following command:
```bash
docker run --detach --publish 8080:8080 cptactionhank/atlassian-jira-software:latest
```

Then simply navigate your preferred browser to `http://[dockerhost]:8080` and finish the configuration.

## Configuration

You can configure a small set of things by supplying the following environment variables

| Environment Variable   | Description |
| ---------------------- | ----------- |
| X_PROXY_NAME           | Sets the Tomcat Connectors `ProxyName` attribute |
| X_PROXY_PORT           | Sets the Tomcat Connectors `ProxyPort` attribute |
| X_PROXY_SCHEME         | If set to `https` the Tomcat Connectors `secure=true` and `redirectPort` equal to `X_PROXY_PORT`   |
| X_PATH                 | Sets the Tomcat connectors `path` attribute |

## Contributions

This image has been created with the best intentions and an expert understanding of docker, but it should not be expected to be flawless. Should you be in the position to do so, I request that you help support this repository with best-practices and other additions.

Travis CI and CircleCI has been configured to build the Dockerfile and run acceptance tests on the Atlassian JIRA Software image to ensure it is working.

Travis CI has additionally been configured to automatically deploy new version branches when successfully building a new version of Atlassian JIRA Software in the `master` branch and serves as the base. Furthermore an `eap` branch has been setup to automatically build and commit updates to ensure this branch contains the latest version of Atlassian JIRA Software Early Access Preview.

If you see out of date documentation, lack of tests, etc., you can help out by either
- creating an issue and opening a discussion, or
- sending a pull request with modifications (remember to read [contributing guide](https://github.com/cptactionhank/docker-atlassian-jira-software/blob/master/CONTRIBUTING.md) before.)

Continuous Integration and Continuous Delivery is made possible with the great services from [GitHub](https://github.com), [Travis CI](https://travis-ci.org/), and [CircleCI](https://circleci.com/) written in [Ruby](https://www.ruby-lang.org/), using [RSpec](http://rspec.info/), [Capybara](http://teamcapybara.github.io/capybara/), and [PhantomJS](http://phantomjs.org/) frameworks.
