CXX = g++
CXXFLAGS = -std=c++17 -Wall -Wextra -pedantic
LDFLAGS = 

all: build

build: client server

client: client.cpp
	$(CXX) $(CXXFLAGS) -o client client.cpp $(LDFLAGS)

server: server.cpp
	$(CXX) $(CXXFLAGS) -o server server.cpp $(LDFLAGS)

run: client server
	./server & sleep 1 && ./client

plot: build
	python3 plot.py

clean:
	rm -f client server plot.png output.txt
	killall server 2>/dev/null || true

.PHONY: all build run plot clean
