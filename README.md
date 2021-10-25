## How I made this load balancer and reverse proxy using nginx

First i created my three websites on node js and checked that they are running on 

- localhost:5001
- localhost:5002
- localhost:5003

Then i made  a load balancer for the websites so that they can utilize the round robin alogorithm for running on localhost:80 sequentially.

## How to make the load-balancer file?

Make the file in /etc/nginx/sites-available with the syntax given in the repository.

- Then when you will run localhost:80 first the port 5001 will get served
- then the 5002 will get served
- and then 5003 will get served.

But to make this run a successful one you will have to link this to sites-enabled by 

**sudo ln -s /etc/nginx/sites-available/load-balancer  /etc/nginx/sites-enabled**

## How to make the reverse-proxy file

Now make this file in /etc/nginx/sites-available with the syntax given in the repository

Now this is for reverse proxy so as per the configuration in the file when you will run 

localhost:80/server1  -----> will redirect to first website

localhost:80/server2 -------> will redirect to second website

localhost:80/server3 -------> will redirect to third website

**NOTE:**- This will not run until you will unlink the above laodbalancer file .SO first unlink it and then link this.



