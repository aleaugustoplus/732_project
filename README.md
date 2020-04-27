# Airline Ranker

Airline Ranker is a software that ranks airlines based on customer satisfacrtion this system leverage data from twitter users and sentiment analysis to create a rank of airlines that will enable customers to make better decision when they are bying their tickets

![spark](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f3/Apache_Spark_logo.svg/1200px-Apache_Spark_logo.svg.png)

## Getting Started

Launch the app as job in apache spark and collect the results

### Prerequisites

Apache spark cluster

### Installing

#### Instructions to run Daemon
cd tweet_stream <br/>
nohup python3 tweet_stream2.py >out.txt & <br/>
The command is running and saving the twitters inside the folder 'airlines_tweets'!

#### Copy the files to be processed
hdfs dfs -copyFromLocal  airlines_tweets <br/>
back to the main directory: cd .. <br/>
copying the training file: hdfs dfs -copyFromLocal airline.csv

#### Executing
spark-submit --master=yarn-client --executor-memory 6G --num-executors 15 --packages TargetHolding/pyspark-cassandra:0.3.5,com.databricks:spark-csv_2.11:1.5.0 --py-files svm.zip process_twitter.py airlines_tweets airline.csv vap 

## Running the tests

Automated tests have not been used 

## Built With

* [Spark](https://spark.apache.org/)

## Contributing

Please stay free to submit pull requests at any time

## Authors

* **Alexandre Lopes** - *Initial work* - [Alexandre Lopes](http://alexandre-lopes.com)

## License

This project is licensed under the MIT License - see the [LICENSE](https://en.wikipedia.org/wiki/MIT_License) page for details

## Acknowledgments

* Some third party open source libraries have been used thank you for that


https://aprendizadodemaquina.com


