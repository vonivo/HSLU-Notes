HazelCast ist eine Theadsafes [[In-Memory-Datagrid]].

>[!error]
>Alle zu verteilenden Objekte müssen `com.hazelcast.nio.serialization.DataSerializable` implementieren.

**Map**
```java
HazelcastInstance client = Hazelcast.newHazelcastInstance();
Map<Integer, String> map = client.getMap("mymap");
map.put(1, "value");
```

**Distributed Lock**
```java
String mylockobject = "MyLock";
FencedLock mylock = client.getCPSubsystem().getLock(mylockobject);
mylock.lock();
try {
	// do something
} finally {
	mylock.unlock();
}
```

**Nebenläuffige Map**
```java
HazelcastInstance client = Hazelcast.newHazelcastInstance();
ConcurrentMap<Integer, String> map = client.getMap("mymap");
map.put(1, "value");

map.putIfAbsent(2, "value2")
map.replace(1, "value1")
```

**Queue**
```java
HazelcastInstance client = Hazelcast.newHazelcastInstance();
BlockingQueue<Task> queue = client.getQueue("tasks");
Boolean done = queue.offer(new Task());
Task task = queue.poll();
LOG.info(task);

//Timed blocking operations
done = queue.offer(new Task(), 500, TimeUnit.MILLISECONDS);
task = queue.poll(5, TimeUnit.SECONDS);
LOG.info(task);

//Indefinitely blocking operations
queue.put(new Task());
task = queue.take();
LOG.info(task);
```

**Topic**
```java
public class DistributedTopic implements MessageListener<MyMessage>{
	@Override
	public void onMessage(Message<MyMessage> msg) {
		MyMessage message = msg.getMessageObject();
		LOG.info("Got msg: " + message.getText() +
			" from " + message.getName());
	}
}

HazelcastInstance client = Hazelcast.newHazelcastInstance();
DistributedTopic distributedTopic = new DistributedTopic();

ITopic<MyMessage> topic = client.getTopic("default");

topic.addMessageListener(distributedTopic);
topic.publish(new MyMessage("my message object", "hello"));
```


