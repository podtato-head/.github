# Contributing to podtato-head

The purpose of podtato-head is to enable infrastructure and platform architects
and engineers to try, compare, and contrast many options for delivering apps and
their components to a Kubernetes cluster.

Please keep this in mind as you develop new contributions! To make it easy for
architects to try, compare and contrast, make sure the docs and tests for your
delivery tool are similar to existing ones.

## Contribute a new delivery tool or service

To add a delivery tool or service to the repo, please create an issue to discuss
and a PR with proposed changes. Each tool should get its own directory in the [podtato-head-delivery](https://github.com/podtato-head/podtato-head-delivery) repo with a README.md; look at existing tools and write something
similar. Please also add a test for your tool as a `test` Makefile target in your folder.

### README details

Include details in README.md to help architects and engineers trying the tool,
such as the following:

* Describe to which version of the podtato-head app the tool or service is
  compatible. If you make modifications from the base manifests and charts
  describe them.
* Describe how to set up or deploy the tools or services. Please provide
  something compatible with "local" clusters provided by kind, minikube, etc. Use an `install` Makefile target to do this.
* Describe how to set up the tool or service to deliver the podtato-head
  application. If you make modifications from the base manifests and charts
  describe them. Try to use the provided manifests and charts from the `podtato-head-app` repo as far as possible instead of duplicating them in your tool's folder.
* Describe how to actually deliver the podtato-head application.
* Describe how to verify the delivery and verify functionality of the delivered app.
* Describe how to upgrade to a new version using the tool, and/or how to
  rollback.
* Describe how to completely purge the podtato-head app and the delivery tools and services from the cluster. Some folks need to return their cluster to a pristine state! Describe this in an `uninstall` Makefile target.

### Other suggestions

* Provide a command line script or Makefile target to run all the example steps which users can copy and paste. You may use this as part of your test too. The following bash commands work as they echo then execute a command:
  ```bash
  if [ $command -eq onboard ] 
      echo command_to_execute
      command to execute
  fi
  ```
* Provide links to the tool's home page, issues page, and source repo. Help people find resources for their questions.
* If you have a video walkthrough of the example - great!

## Contribute to the podtato-head app

If you have a new use cases in mind (e.g. adding an additional service, ....)
please create an issue in the [podtato-head-app](https://github.com/podtato-head/podtato-head-app) repository and describe how the use case should work. As we want to keep the ``` main ``` branch as a working version we will create a dedicated branch for new use cases.

## General discussion

For general discussions please join the CNCF podtato-head
[Slack channel](https://cloud-native.slack.com/channels/project-podtato-head).