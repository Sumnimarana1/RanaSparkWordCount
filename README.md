# RanaSparkWordCount

## Links
- [Webpage](https://sumnimarana1.github.io/RanaSparkWordCount/ "Rana Spark Word Count")
- [Source](https://github.com/Sumnimarana1/RanaSparkWordCount  "Rana Spark Project Source")

## About Me & Objective
My name is Sumnima Rana and I am a senior student at Northwest Missouri State University with the major in Computer and Information Sciece. This project is for my "Big Data" class on Spark and Scala. The objective of this assignment is to use Spark-shell to find the most frequent words within the text by Shakespeare, HAMLET. 

## Data
I used a .txt file of Hamlet by copying and pasting a entire play from the following website:
- [HAMLET](http://shakespeare.mit.edu/hamlet/full.html "Website for Hamlet")

## Scala Commands
```
Scala> val inputFile = sc.textFile("C:/44564/RanaSparkWordCount/HAMLET.txt")
Scala> val topWordCount = inputFile.
  flatMap(str=>str.split(" ")).
  filter(!_.isEmpty).
  map(word=>(word,1)).
  reduceByKey(_+_).
  map{case (word, count) => (count, word)}.
  sortByKey(false)
Scala> topWordCount.take(10).foreach(x=>println(x))
```

## Results
The 10 results that I got from the commands are as follows:

| Count | Word |
|-------|------|
| 988   | the  |
| 693   | and  |
| 621   | of   |
| 604   | to   |
| 513   | I    |
| 450   | a    |
| 441   | my   |
| 387   | in   |
| 378   |HAMLET|
| 356   | you  |

The result showed that the most frequently used word is 'the' and it has been used 988 times.

I have represented this data into the visuals using the chart representation.
![chart](https://user-images.githubusercontent.com/33071134/48314465-876dbc80-e58f-11e8-892d-efb5ca29f169.png)



