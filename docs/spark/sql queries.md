# SQL queries on dataframe 

## schema 

show inbuilt schema

```scala
spark.read.format("json").load("/file location").schema

```

explicit schema 
```scala
import org.apache.spark.sql.types.{StructTypes,StructFields, StringType, LongType}
import org.apache.spark.sql.types.Metadata

val myschema = StructType(Array(StructField("column1",StringType,true),
							StructField("column2",StringType,false,Metadata.fromJson("{\"hello\":\"world\"}"))))
val df = spark.read.format("json").schema(myschema).load("file/location")
```

## creating dataframes and inserting row

```scala
import org.apache.spark.sql.types.{StructType,StructField,StringType,LongType}
import o.apache.spark.sql.Row
%%create schema%%
val mySchema = new StructType(Array(
StructField("col1",StringType,true),
StructField("col2",StringType,false)
))
%%insert row%%
val myRow = seq(Row("hello","world"))
val RDD = spark.sparkContext.parallelize(myRow)
val mydf = spark.createDataFrame(RDD,mySchema)
mydf.show()
```

## add column (withColumn)

```scala
df.withColumn("withinContry",expr("column1=column2")).show(2)

```

## remove column (drop)

```scala
df.drop("column").columns
```
## rename column

```scala
df.withColumnRenamed("column","dest").columns
```
## selectExpr

```scala
import org.apache.spark.sql.function{expr}

df.selectExpr("column1").show(2)
df.selectExpr("column1","column2").show(2)
df.selectExpr("*","column1= column2").show(2)

```

## aggregation 

```scala
df.selectExpr("avg(column1)","count(distinct(column2))").show(2)
```

## filtering Rows(where/filter)

```scala
df.filter(col("column")<2).show(2)

df.where("column <2").show(2)
```

## multiple filters (where ,and )
```scala
df.where(col("column") >2).where(col("columnm2")=="abs").show(2)
```

## unique rows( distinct)

```scala
df.select("column1","column2").distinct().count()
```

## sorting row (sort or orderBy)
```
df.sort("count").show(5)
df.orderby("coun1","column2").show(5)
```

```scala
import org.apache.spark.sql.functions.{desc, asc}
df.orderBy(expr("count desc")).show(2)
df.orderBy(desc("count"), asc("DEST_COUNTRY_NAME")).show(2)
```

## types of join

```
val person = Seq(
(0, "Bill Chambers", 0, Seq(100)),
(1, "Matei Zaharia", 1, Seq(500, 250, 100)),
(2, "Michael Armbrust", 1, Seq(250, 100)))
.toDF("id", "name", "graduate_program", "spark_status"

person.createOrReplaceTempView("person")
```
### inner 

- the keys in both of the DataFrames or tables and include (and join together)
- only the rows that evaluate to true.
```  scala
val joinExpression = person.col("graduate_program") === graduateProgram.col("id")
var joinType = "inner"
person.join(graduateProgram, joinExpression, joinType).show()
```


outer
left outer join
```scala
graduateProgram.join(person, joinExpression, joinType).show()
%%graduate program appers on left %% 


```
right outer join
```scala
joinType = "right_outer"
person.join(graduateProgram, joinExpression, joinType).show()
```
left semi join

```scala
joinType = "left_semi"
graduateProgram.join(person, joinExpression, joinType).show()
```
left anti 
natural 
cross
