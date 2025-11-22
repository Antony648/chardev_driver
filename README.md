this is a sample character device driver for modern linux

it implements all basic device driver functionalities like 

    open
    read
    write 
    release

it uses 
    mutex based synchronization between read/write
    atomic based synchronization betweenb open/release
    dynamic major number allocation
    automatic driver creation using class_create() and device_create()
    it also sends apporpriate kernel messages on each operation and proper error messages on failure

the goal is to demonstrate and get better understanding of implementations inside linux kernel

how to run:

command1:
    make 
        will run the Makefile and build all neccessary kernel files 
command2:
    sudo insmod chardev.ko
        will load the device driver to kernel 
command3:
    ls -l  /dev/chardev1
        (optional) verify the creation of device
command4:
    sudo chmod 666 /dev/chardev1
        this is neccesary for the next steps as read write permissions are not given by default
command5:
    echo "hello kernel"  >> /dev/chardev1
        this writes the message to the device driver
command6:
    cat /dev/chardev1
        should print "hello kernel"
command7:
    sudo rmmod chardev
        unloads the chardevice for kernel space
one  could also use dmesg to veiw all kernel level messages printed by the program...


REQURIEMENTS:
    linux kernel headers installed
    GCC toolchain
    Make
    Root privileges
