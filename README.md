
#	Producer and consumer 
#	Using G++ coompiler
#
#	Author: Justin Marasco
#	Date: 11/6/23

#Menu
msg:
	@echo 'Targets are: '
	@echo ' producer'
	@echo ' consumer'
	@echo ' run'
	@echo  ' clean'

consumer: ./src/consumer.cpp
	g++ "./src/consumer.cpp" -pthread -lrt -o ./out/consumer


producer: ./src/producer.cpp
	g++ "./src/producer.cpp" -pthread -lrt -o ./out/producer


run: ./src
	
	make producer
	make consumer
	clear
	./out/producer shmfile & ./out/consumer shmfile

clean:
	rm -f ./out/consumer
	rm -f ./out/producer
