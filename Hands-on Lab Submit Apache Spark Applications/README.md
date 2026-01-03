# Learning objectives
  -- In this lab, you will:
    -- Install a Spark Master and Worker using Docker Compose
    -- Create a Python script containing a Spark job
    -- Submit the job to the cluster directly from python (Note: you'll learn how to submit a job from the command line in the Kubernetes lab)
## Prerequisites
    -- The only prerequisites for this lab are:
        -- The wget command line tool
        -- A Python development environment

# Start the Spark Master
    1. Enter the following commands in the terminal to download the Spark environment:
        wget https://archive.apache.org/dist/spark/spark-3.3.3/spark-3.3.3-bin-hadoop3.tgz && tar xf spark-3.3.3-bin-hadoop3.tgz && rm -rf spark-3.3.3-bin-hadoop3.tgz
     (This process may take some time. It downloads Spark as a zipped archive and then unzips it into the current directory.)
    2. Run the following commands to set up JAVA_HOME (preinstalled in the environment) and SPARK_HOME (which you just downloaded):
        export JAVA_HOME=/usr/lib/jvm/java-1.11.0-openjdk-amd64
        export SPARK_HOME=/home/project/spark-3.3.3-bin-hadoop3 

    3. Run the following command to create a config file for the master:
        touch /home/project/spark-3.3.3-bin-hadoop3/conf/spark-defaults.conf

        In the spark-defaults.conf, insert the following lines:
            spark.executor.memory 4g
            spark.executor.cores 2    
    4. Navigate to the SPARK_HOME directory:
            cd $SPARK_HOME
    5. Run the Spark master by executing the following command:
            ./sbin/start-master.sh
    6. Once it starts up successfully, click the button below to verify that the Master is running as expected.
          Example: URL: spark://theiadocker-sherif425:7077
          