# Spark-Project

## About Me and the Objective of your Project

I am Anusha Chowdary Kollu pursuing my masters in Northwest missouri state university. I am doing this project as a part of my "BigData" course. The Objective of the project is to find the most commonly used words using the titanic story review. The overall project is done using spark.

## Introduction:

Apache Spark is an open source framework used for running large-scale data analytics applications across clustered computers. It has distributed collection of items called as RDDs.

## Prerequsites:  
1.Spark must be installed in our systems.   
2.Tableau must be installed in our systems.  

## Dataset Story:
I have taken the reviews that are written for a titanic story. From the reviews I just want to find the most repeated words. So with the help of most commonly repeated words and the count of the words, we can represent them pictorially. Now here I considered the wordcount greater than 20, which can be most repeated words. I am representing it in tableau where the data can be analysied clearly in graphs or piecharts or in a different way as the user can modify it as they like and they can even use filters to segregate the data. Here in tableau it considers the case too. In this example you can see that it shows "the" as two different as one is "the" and the other is "The".  
Source : http://www.chasingthefrog.com/reelfaces/titanic.php

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

## Results

Here is the result that is obtained by using the above commands  

| Word    | Count|
|---------|------|
| $8      | 500  |
| the     | 254  |
| of      | 91   |
| to      | 74   |
| in      | 60   |
| a       | 58   |
| and     | 51   |
| was     | 47   |
| that    | 38   |
| on      | 35   |
| Titanic | 29   |
| The     | 28   |
| from    | 25   |
| as      | 21   |
| ship    | 21   |

Here we can see that the most commonly used word is "$8" which is used used 500 times and the next commonly used word is "the", it is used for 254 times. Here is pictorial representation of the above results.  
### This is the result represented in Packed bubbles:  
![spark tableau](https://user-images.githubusercontent.com/31708972/48237752-b4eb1800-e38d-11e8-9f5f-9953e6e3dd66.PNG)  
### Result represented in bar graphs:  
![spark graph](https://user-images.githubusercontent.com/31708972/48239353-2928ba00-e394-11e8-98d7-5002afedf19a.PNG)

## References:

1.https://github.com/S530484/Spark_wordcount/blob/master/README.md
