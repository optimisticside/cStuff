CC = gcc
CFLAGS = -g -Wall -Wextra -Wpedantic --std=c17

all: server clientTraffic 

# Target (ClientTraffic)
clientTraffic: clientTraffic.o client.o
	$(CC) $(CFLAGS) $^ -o $@

# Target (Server)
server: server.o queue.o
	$(CC) $(CFLAGS) $^ -o $@

# Object
clientTraffic.o: clientTraffic.c client.c client.h
	$(CC) $(CFLAGS) -c $< -o $@

# Object
client.o: client.c client.h queue.h 
	$(CC) $(CFLAGS) -c $< -o $@

# Object
server.o: server.c server.h queue.h
	$(CC) $(CFLAGS) -c $< -o $@

# Object
queue.o: queue.c queue.h
	$(CC) $(CFLAGS) -c $< -o $@

# clean
clean:
	rm -f *.o clientTester server

.PHONY: clean
