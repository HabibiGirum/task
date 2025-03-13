# task

def check_droplet_ssh():
    droplets = client.droplets.list()["droplets"]
    for droplet in droplets:
        for net in droplet["networks"]["v4"]:
            if net["type"] == "public":
                return False
    return True

import os
from pydo import Client

client = Client(token=os.environ.get("DIGITALOCEAN_TOKEN"))

resp = client.load_balancers.get(lb_id="afda3ad")
Load balancer unhealthy host count monitored (DigitalOcean)

