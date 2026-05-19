BUILD ?= "build"

all: build

.PHONY: build
build:
	mkdir -p $(BUILD)
	cd $(BUILD); cmake ..
	cd $(BUILD); $(MAKE)

.PHONY: clean
clean:
	rm -rf $(BUILD)

.PHONY: run
run:
	cd $(BUILD); ./companion_server /dev/ttyUSB1 115200

.PHONY: format
format:
	find ../src -iname '*.h' -o -iname '*.c' -o -iname '*.cpp' | xargs clang-format -i
	find ../include -iname '*.h' -o -iname '*.c' -o -iname '*.cpp' | xargs clang-format -i
	echo "server.c" | xargs clang-format -i
