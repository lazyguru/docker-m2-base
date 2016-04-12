# Example project directory

## Prerequisites
* If running on OSX or Windows, you need either VirtualBox, VMware, or another VM solution (check out https://github.com/nlf/dlite if running on OSX)
* Docker & Docker Compose

## More Info
The data directory will contain the contents of /var/lib/mysql from the DB container.
This is so that the database is persisted between docker runs (yes you could do a 
data volume for this instead, but I sometimes get a bit punch with ```docker rm```
so this is safer).  You should at least gitignore the contents of this directory.
You may get permissions issues on the host with this directory.  Since you really
shouldn't care about the contents of this directory on the host and only need the
docker instances to access it this can be ignored.

Install Magento2 into the magento sub-directory.  This directory will be exposed
to the nginx and php containers as a volume.  You can make changes to files in
this directory and the containers will see them instantly

## Running
* Copy docker-compose.yml to your project directory (should contain an empty data subdirectory and a magento directory containing your Magento source)
* Run ```docker-compose up -d``` from this directory to launch all instances. If you need to access the DB from the command line, make sure to add a host file entry for the host "php" pointed to your docker VM instance (not sure how that would work on Linux, I'm a Mac guy)

