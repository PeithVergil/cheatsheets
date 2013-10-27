Pillow (Python Imaging Library)
===============================


Install dependencies
--------------------------------------------------

#### Install Python headers
`sudo apt-get install python-dev python-setuptools`

#### Install image libraries
`sudo apt-get install libfreetype6-dev liblcms1-dev libtiff4-dev libjpeg8-dev libwebp-dev zlib1g-dev tcl8.5-dev tk8.5-dev`


Symlink libraries
--------------------------------------------------

# 32-bit
    sudo ln -s /usr/lib/i386-linux-gnu/libz.so /usr/lib/libz.so
    sudo ln -s /usr/lib/i386-linux-gnu/libjpeg.so /usr/lib/libjpeg.so
    sudo ln -s /usr/lib/i386-linux-gnu/libfreetype.so /usr/lib/libfreetype.so

# 64-bit
    sudo ln -s /usr/lib/x86_64-linux-gnu/libz.so /usr/lib/libz.so
    sudo ln -s /usr/lib/x86_64-linux-gnu/libjpeg.so /usr/lib/libjpeg.so
    sudo ln -s /usr/lib/x86_64-linux-gnu/libfreetype.so /usr/lib/libfreetype.so


Install Pillow
--------------------------------------------------
`pip install Pillow`