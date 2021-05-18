# Getting Started with Redis Streams & Java

This project shows how to use [Lettuce Java client](https://lettuce.io) to publish and consume messages using consumer groups.

This is a first basic example that use a single consumer.

### Build

```
> cd redis-streams-101-java

> mvn clean verify

```

### Run

Run the producer

```
> cd redis-streams-101-java

> mvn exec:java -Dexec.mainClass="com.kanibl.redis.streams.simple.RedisStreams101Producer" -Dexec.args="5"
```

```
Downloaded from central: https://repo.maven.apache.org/maven2/org/sonatype/sisu/sisu-guice/2.1.7/sisu-guice-2.1.7-noaop.jar (472 kB at 450 kB/s)
Downloaded from central: https://repo.maven.apache.org/maven2/org/slf4j/slf4j-api/1.7.5/slf4j-api-1.7.5.jar (26 kB at 25 kB/s)
Downloaded from central: https://repo.maven.apache.org/maven2/commons-codec/commons-codec/1.11/commons-codec-1.11.jar (335 kB at 313 kB/s)

 Sending 5 message(s)
May 18, 2021 1:07:00 PM io.lettuce.core.EpollProvider <clinit>
INFO: Starting without optional epoll library
May 18, 2021 1:07:00 PM io.lettuce.core.KqueueProvider <clinit>
INFO: Starting without optional kqueue library
        Message 1621343220998-0 : {sensor_ts=1621343220975, loop_info=0, speed=15, direction=270} posted
        Message 1621343221009-0 : {sensor_ts=1621343221007, loop_info=1, speed=15, direction=270} posted
        Message 1621343221016-0 : {sensor_ts=1621343221011, loop_info=2, speed=15, direction=270} posted
        Message 1621343221019-0 : {sensor_ts=1621343221017, loop_info=3, speed=15, direction=270} posted
        Message 1621343221023-0 : {sensor_ts=1621343221021, loop_info=4, speed=15, direction=270} posted


[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  9.102 s
[INFO] Finished at: 2021-05-18T13:07:01Z
[INFO] ------------------------------------------------------------------------
[node1] (local) root@192.168.0.18 ~/redis-streams-101-java
$ 
```



Run the consumer

```
> cd redis-streams-101-java

> mvn exec:java -Dexec.mainClass="com.kanibl.redis.streams.simple.RedisStreams101Consumer"
```
