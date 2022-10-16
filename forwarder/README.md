# Forwarder Proxy

This directory contains the configuration required to setup a
forwarding HTTPS proxy. This can be useful if the Arvan CDN solution
stops working or for whatever reason you do not want to use it.

You need two domains (possibly sub-domains of the same domain), one
for the proxy server and one for the backend server. Each server would
acquire a separate HTTPS certificate.

In order to use this setup, you need a server inside Iran. Clone to
repository, go to the `forwarder` sub-directory. Before running the
proxy you need to edit the `.env` file and update the following
variables:

 - `FORWARDER_DOMAIN`: The domain name used by the forwarder
   proxy. You need to have configured the nameservers and DNS records
   properly for the domain to be accessible.

 - `BACKEND_SERVER`: The domain name of the backend proxy, which
   should be outside Iran and running shadowsocks/v2ray.

 - If the backend is not running on port 443, you should also change
   the value of the `BACKEND_PORT` variable.

After you've made the changes, save the file and run `docker-compose
build`. If the build is successful, proceed to running the proxy by
`docker-compose up -d`.

You can view the logs by running `docker-compose logs -f`.

