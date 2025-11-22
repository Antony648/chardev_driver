this is a sample character device driver for modern linux

it implements all basic device driver functionalities like 

    open
    read
    write 
    release

it uses mutex based synchronization between read/write
and atomic based synchronization betweenb open/release

it also sends apporpriate kernel messages on each operation and proper error messages on failure

