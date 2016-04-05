# Example project directory

Run ```docker-compose up -d``` from this directory to launch all instances. If you need to access the DB 
from the command line, make sure to add a host file entry for the host "php" pointed to your docker VM 
instance (not sure how that would work on Linux, I'm a Mac guy)

The data directory will contain the contents of /var/lib/mysql from the DB container.  This is so that the
database is persisted between docker runs.  You should at least gitignore the contents of this directory

Install Magento2 into the magento sub-directory.  This directory will be exposed to the nginx and php 
containers as a volume.  You can make changes to files in this directory and the containers will see
them instantly
