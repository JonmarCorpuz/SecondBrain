# Dockerfile 

* Allows you to define all the steps necessary to build your Docker images
* Reduces the risk of human error by automating the build process for your applications
* Provides a clear overview and full control of all the steps involved in building it

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Build Context

The [build context](https://docs.docker.com/build/concepts/context/#what-is-a-build-context) is the set of files that your build can access

## .dockerignore

The [.dockerignore](https://docs.docker.com/build/concepts/context/#dockerignore-files) files allows you define files or directories to exclude from the build context

* Helps avoid sending unwanted files and directories to the builder
* Improves build speed, especially when using a remote builder
* When you run a build command, the build client looks for a file named `.dockerignore` in the root directory of the context and if this file exists, the files and directories that match patterns in the files are removed from the build context before it's sent to the builder
