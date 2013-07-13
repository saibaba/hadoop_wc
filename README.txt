1) javac -classpath ../../hadoop-1.0.4/hadoop-core-1.0.4.jar:. WordDriver.java WordMapper.java WordReducer.java
2) jar -cvf word.jar *.class
3) Copy input file to HDFS:
$ ../../hadoop-1.0.4/bin/hadoop dfs -put /home/ubuntu/AdventuresSherlockHomes.txt /input/AdventuresSherlockHomes.txt

(get input file from www.gutenberg.org/cache/epub/1661/pg1661.txt)

4) Run hadoop job

$ ../../hadoop-1.0.4/bin/hadoop jar word.jar  WordDriver -conf conf/core-site.xml  /input/AdventuresSherlockHomes.txt word

5) see output in run.out

6) See results:

$ ../../hadoop-1.0.4/bin/hadoop dfs -cat word/part-r-00000

Watson	81

References:
1) http://www.petrikainulainen.net/programming/apache-hadoop/creating-hadoop-mapreduce-job-with-spring-data-apache-hadoop/
2) Others
