# Spark-Project

## Introduction:

Apache Spark is an open source framework used for running large-scale data analytics applications across clustered computers. It has distributed collection of items called as RDDs.

## Prerequsites:
1.Spark must be installed in our systems.

## Dataset Story:
I have taken the reviews that are written for a titanic story. From the reviews I just want to find the most repeated words. So with the help of most commonly repeated words and the count of the words, we can represent them pictorially. Now here I considered the wordcount greater than 20, which can be most repeated words. I am representing it in tableau where the data can be analysied clearly in graphs or piecharts or in a different way as the user can modify it as they like and they can even use filters to segregate the data. Here in tableau it considers the case too. In this example you can see that it shows "the" as two different as one is "the" and the other is "The".


## Wordcount:

The following command is used to get the total word count in a text file.

```
> val inputFile = sc.textFile("C:/44517/titanic_sample/titanic.txt")
```

The following command is used to find the word count of each word in a text file.

```
>val counts = inputFile.flatMap(line => line.split(" ")).map(word => (word,1)).reduceByKey(_ + _);
```

These command is used to store the dataset in a text format. It is stored in the show-spark directory as I have mentioned path as c:/tmp/show-spark/output. It stores the values as a partitions. 

```
> counts.saveAsTextFile("c:/tmp/show-spark/output")
```



## Data Chart for the obtained partitions

## References:

1.https://github.com/S530484/Spark_wordcount/blob/master/README.md