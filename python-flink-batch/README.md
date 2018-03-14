# Example Batch Application

## Overview

[Apache Flink](http://flink.apache.org/) is an open source platform for distributed stream and batch data processing. Flink’s core is a streaming dataflow engine that provides data distribution, communication, and fault tolerance for distributed computations over data streams. Flink builds batch processing on top of the streaming engine, overlaying native iteration support, managed memory, and program optimization.
Apache Flink’s APIs are available in Java, Scala and Python.

## Usage

In PNDA, the existing Python utility is configured to execute flink applications on local as well as on yarn cluster.

For executing applications using pyflink utility to submit on yarn cluster use `./bin/pyflink-yarn.sh ./exmaples/python/Wordcount.py`.

The example python applications packaged along with flink are configured to execute on local cluster. To submit flink applications to yarn cluster, modify the value to `env.execute(local=False)`.
