# Understanding  subscriber and message broker

1. What is amqp?

amqp stands for Advanced Message Queueing Protocol. It is an open standard for passing business messages between applications or organizations. It connects systems, feeds business processes with the information they need and reliably transmits onward the instructions that achieve their goals.

2. What it means? `guest:guest@localhost:5672` , what is the first guest, and what is the second guest, and what is localhost:5672 is for? 

- `guest:guest@localhost:5672` is a connection for AMQP server. <Br>
- The first guest in `guest:guest` is the username for the server <br>
- The second guest in `guest:guest` is the password for the server <Br>
- `localhost:5672` is for defining where the host, in this case the hostname of the server, and which port it listens to, in this case 5672, which is the default port for AMQP.