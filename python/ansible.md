Ansible
-------


#### Generating a password hash for the 'user' module
    # Make sure 'passlib' is already installed:
    # pip install passlib

    from passlib.hash import sha512_crypt

    print(sha512_crypt.encrypt('[your password here]'))