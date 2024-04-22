# Understanding  subscriber and message broker

1. What is amqp?

amqp stands for Advanced Message Queueing Protocol. It is an open standard for passing business messages between applications or organizations. It connects systems, feeds business processes with the information they need and reliably transmits onward the instructions that achieve their goals.

2. What it means? `guest:guest@localhost:5672` , what is the first guest, and what is the second guest, and what is localhost:5672 is for? 

- `guest:guest@localhost:5672` is a connection for AMQP server. <Br>
- The first guest in `guest:guest` is the username for the server <br>
- The second guest in `guest:guest` is the password for the server <Br>
- `localhost:5672` is for defining where the host, in this case the hostname of the server, and which port it listens to, in this case 5672, which is the default port for AMQP.


- Chart Screenshot
![image](https://cdn.discordapp.com/attachments/874575252808667149/1231998243727216793/image.png?ex=6627db46&is=662689c6&hm=9e99a310cebece34d2346b945304cad0b1dce20c894eb37e64465104ed940e4c&)
It can be seen from the image above that there are a number of messages that can't be processed immediately resulting in an increase number of messages inside the queue (around 40 messages). This happens because the subscriber can't receive messages immediately.

- Terminal of 3 Subscribers
![image](https://cdn.discordapp.com/attachments/874575252808667149/1232001324787175544/image.png?ex=663901a5&is=66268ca5&hm=8d6955d942e8796cf05d83af17417f5086612075704255b433240dd87cd7d016&)

- Graph
![image](https://cdn.discordapp.com/attachments/874575252808667149/1232001340901687358/image.png?ex=6627de29&is=66268ca9&hm=c562a489fc7f6a7beceea05a85194400106bd5119004ccf1654052bfd174482c&)
In the image, it can be observed that each subscriber receives different data when the publisher sends a large amount of data to the message queue. This is because each subscriber functions like its own application, thus they operate separately when retrieving data from the message queue. Once data is retrieved from the message queue, the message will be consumed and unavailable for other applications to use.
In my opinion, one way to improve the performance of subscriber applications is by making them multithreaded so they can process multiple events from the publisher simultaneously.