# Example Batch Application

## Overview

The example batch application shows an example of an application that can be deployed using the PNDA Deployment Manager. (See the `platform-deployment-manager` project for details.)

The application is a tar file containing binaries and configuration files required to perform batch processing.

This example application reads the data as input from a file in HDFS and writes output to the file in HDFS.

There are two versions of the application:

- workflow, designed to run once
- coordinator, designed to run regularly on a schedule


## Requirements

* [Maven](https://maven.apache.org/docs/3.0.5/release-notes.html) 3.0.5
* [Java JDK](https://docs.oracle.com/javase/8/docs/technotes/guides/install/install_overview.html) 1.8

## Build

To build the example applications use:

````
mvn clean package
````

This command should be run at the root of the repository and will build the application binary, and both application packages. Both application packages do the same job but the "-c" package runs on a regular schedule as an oozie coordintor application, and "-wf" runs once as an oozie workflow application.  It will create package files in the app-package-c/target and app-package-wf/target directories. They will be called spark-batch-example-app-c-{version}.tar.gz and spark-batch-example-app-wf-{version}.tar.gz respectively.

## Spark Job

Both versions of the application run the same Flink code.

This is a very basic job that reads data and writes to the output file.

## Files in the package

- `log4j-cli.properties`: defines the log level and behaviour for the application.

## Deploying the package and creating an application

The PNDA console can be used to deploy the application package to a cluster and then to create an application instance. The console is available on port 80 on the edge node.

To make the package available for deployment it must be uploaded to a package repository. The default implementation is an OpenStack Swift container. The package may be uploaded via the PNDA repository manager which abstracts the container used, or by manually uploading the package to the container.
