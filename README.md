crypteduser

Tiny authentication server written in python & flask.

Setup
-----

Install the requirements either in a virtualenv or natively
    pip install -r requirements.txt

Edit the configuration file (crypteduser.conf) to set the database and disable debug
Create the database by setting the environment variable CREATEDB

    CREATEDB=1 ./crypteduser.py

Then run the server.

Add a user
* curl -i -d username=jamesp -d password=WombleW1m http://127.0.0.1:5000/adduser/

Check password
* curl -i -d username=jamesp -d password=WombleW1m http://127.0.0.1:5000/verifyuser/

Update password
* curl -i -d username=jamesp -d password=WombleW1m2 http://127.0.0.1:5000/updatepass/

Notes
-----

If you run this over the network (ie - not over localhost), put an a SSL-terminating proxy in front.
Do NOT send the usernames & passwords over in plain text. Do not run in debug mode in production.
