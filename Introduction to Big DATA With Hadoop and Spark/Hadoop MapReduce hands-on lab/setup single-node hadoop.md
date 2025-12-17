The steps outlined in this lab use the single-node Hadoop Version 3.3.6 Hadoop is most useful when deployed in a fully distributed mode on a large cluster of networked servers sharing a large volume of data. However, for basic understanding, we will configure Hadoop on a single node.

    In this lab, we will run the WordCount example with an input text and see how the content of the input file is processed by WordCount.

    1. Start a new terminal

    2. Download hadoop-3.2.3.tar.gz to your theia environment by running the following command.

        curl https://dlcdn.apache.org/hadoop/common/hadoop-3.3.6/hadoop-3.3.6.tar.gz --output hadoop-3.3.6.tar.gz

    3. Extract the tar file in the currently directory.

        tar -xvf hadoop-3.3.6.tar.gz

    4. Navigate to the hadoop-3.3.6 directory.

    5. Check the hadoop command to see if it is setup. This will display the usage documentation for the hadoop script.

        bin/hadoop

    6. Run the following command to download data.txt to your current directory.

        curl https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-BD0225EN-SkillsNetwork/labs/data/data.txt --output data.txt

    7. Run the Map reduce application for wordcount on data.txt and store the output in /user/root/output

        bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-3.3.6.jar wordcount data.txt output
    
    8. This may take some time.

Once the word count runs successfully, you can run the following command to see the output file it has generated.
1
ls output

Copied!

Wrap Toggled!

Executed!
You should see part-r-00000 with _SUCCESS indicating that the wordcount has been done.

While it is still processing, you may only see ‘_temporary’ listed in the output directory. Wait for a couple of minutes and run the command again till you see output as shown above.

Run the following command to see the word count output.
1
cat  output/part-r-00000

Copied!

Wrap Toggled!

Executed!
Local wordcount output
The image below shows how the MapReduce wordcount happens.

