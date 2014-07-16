Ansible
-------


#### Generate a password hash for the 'user' module
`python -c "from passlib.hash import sha512_crypt; print(sha512_crypt.encrypt('[password]'))"`