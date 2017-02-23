park SQL
Spark SQL uses a very generic tree data structure which extends Scala's `Product` class. This is a bit tricky - for example
there is a method to get children by just taking any of the items inside the constructor of case classes (the fields of the
product) that are the same type of that tree. You must implement it with a case class. 

## Logical Plan
A plan representing what needs to be accomplished.
## Physical Plan (SparkPlan)
A plan representing how to accomplish it. There could potentially be many of these for a given logical plan and the optimizer
chooses the best one.
## Expression
e.g. Add()
## Strategy
A strategy transforms a logical plan to a Spark plan. If there is a logical plan node in a tree and there is no strategy for
how to deal with it, then things will blow up.
## Rule
A rule transforms a tree of one type into a tree of the same type!

## Structured Streaming
### Incremental Execution
### Stream Execution
### State Store
### Plan Stateful Aggregation
### StateStoreRDD

