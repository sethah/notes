# Summary
A [summary paper](http://dsc.soic.indiana.edu/publications/DLFrameworks.pdf) of some of the major frameworks.

# DL4J
DL4J is a deep learning framework for the JVM (duh). It supports Java as a first class citizen, supposedly Scala too but not sure how seamlessly it integrates.

## Declarative or imperative?
Declarative - need to learn more about this.

## Computation

DL4J is built on top of ND4J which is "numpy for the jvm". ND4J can use native (i.e. C, GPU code) code for linear algebra operations and the like, and uses off-heap storage. Note that this is significantly better than how Spark uses netlib-java, since Spark will call native code, but is forced to copy the data through JNI, perform the operations, then copy it back. ND4J avoids this by storing the data off-heap, and using [JavaCPP](https://github.com/bytedeco/javacpp) to access it and run the native code. 

## Data ingestion

They have made their own custom data vectorization/etl library called [DataVec](https://github.com/deeplearning4j/datavec) which, presumably, converts many different types of data into binary record formats that integrate nicely with nd4j/dl4j.

## Hardware

Supports CPU and GPU.

## Multi-machine

DL4J can use Spark to distribute training across several machines. Data parallelism is supported and described in the docs, not sure about model parallelism. Basically, they distribute the model across the cluster, train on shards of data (one partition per executor) and then average the model parameters. I have not read much about doing this for deep nets, but presumably it works alright. How does this compare to model parallelism?

# MXNET (Amazon)

From Alex Smola (Amazon), Mu Li (CMU). Boasts better performance than Tensorflow, but perhaps a smaller community.

## Declarative or imperative?
Declarative
# BigDL

DL on Spark, made by Intel for Intel hardware.

# Tensorflow (Google)
Huge open source community.
## Declarative or imperative?
Declarative

# Theano
## Declarative or imperative?
Declarative

# Torch (Facebook)
## Declarative or imperative?
Imperative

# H2O


