Graphite + Grafana + Nexenta Dashboard
---------------------------------------------

This image contains a sensible default configuration of Graphite and Grafana, and comes bundled with a example
dashboard that gives you the basic metrics currently collected by Kamon for both Actors and Traces. There are two ways
for using this image:


### Building the image ###

The Dockerfile and supporting configuration files are available in the [Github repository](https://github.com/wkettler/docker-grafana-graphite).
This comes specially handy if you want to change any of the Graphite or Grafana settings, or simply if you want
to know how tha image was built. The repo also has `build` and `start` scripts to make your workflow more pleasant.


### Running the image ###

All you need as a prerequisite is having Docker installed on your machine. The container exposes the following ports:

- `80`: the Grafana web interface.
- `2003`: the Carbon-cache port.

To start a container with this image you just need to run the following command:

```bash
docker run -d -p 80:80 -p 2003:2003/udp --name nexenta-grafana-dashboard nexenta/grafana_graphite
```

If you already have services running on your host that are using any of these ports, you may wish to map the container
ports to whatever you want by changing left side number in the `-p` parameters. Find more details about mapping ports
in the [Docker documentation](http://docs.docker.io/use/port_redirection/#port-redirection).


### Using the Dashboard ###

Once your container is running all you need to do is open your browser pointing to the host/port you just published and
play with the dashboard at your wish. We hope that you have a lot of fun with this image and that it serves it's
purpose of making your life easier. This should give you an idea of how the dashboard looks like when receiving data
from one of our toy applications:
