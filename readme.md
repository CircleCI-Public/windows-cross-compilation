# Windows Cross Compilation Sample Application

This simple project demonstrates how to build a project on Windows, persist artifacts to a workspace, and then make available those artifacts to be used and/or tested on other executors.

If you take a look at the [config.yml](./.circleci/config.yml) you will see the following:

- The sample application (written in Go) is compiled for Windows, Mac, and Linux on a Windows executor.
- Using Powershell, the compiled binaries are persisted to a workspace.
- We run a job on the Mac executor and one on the Docker executor that perform the following steps:
  - Re-attach to a workspace
  - Make the binaries for their respective architecture executable
  - Run a small shell command to test that the binaries are returning the expected string.


