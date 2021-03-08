obj-m += lkm_example.o
all:
	make -C /tmp/tinycore-kernel-build/modules-4.19.152/lib/modules/4.19.152-tinycore64/build M=$(PWD) modules
clean:
	make -C /tmp/tinycore-kernel-build/modules-4.19.152/lib/modules/4.19.152-tinycore64/build M=$(PWD) clean
test:
	# We put a — in front of the rmmod command to tell make to ignore
	# an error in case the module isn’t loaded.
	-sudo rmmod lkm_example
	# Clear the kernel log without echo
	sudo dmesg -C
	# Insert the module
	sudo insmod lkm_example.ko
	# Display the kernel log
	dmesg
