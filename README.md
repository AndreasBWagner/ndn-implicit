ndn-implicit
============

Only share unique substrings of data. The rest is implied.

status
======

Right now ndnibd is just a simple block driver. I need to add ndn networking to the module and the ndni networking as well.

usage
=====

    make                                         # Build the module.
    sudo insmod src/ndnibd.ko                    # Insert the module.
    sudo fdisk /dev/ndnibd0                      # Start by adding a parition to the block device.
    n                                            # (n)ew partition.
    p                                            # (p)rimary.
    1                                            # parition number (1).
                                                 # first cylinder (default).
                                                 # Last cylinder (default).
    w                                            # Write the partition table.
    mkfs /dev/ndnibd0p1                          # Format a filesystem to your new parition.
    mount /dev/ndnibd0p1 /mnt/ndni               # Mount your partition.
    echo 'Hello World' > /mnt/ndni/greetings.txt # Use the filesystem for stuff.
