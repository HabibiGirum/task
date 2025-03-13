# task

def check_droplet_ssh():
    droplets = client.droplets.list()["droplets"]
    for droplet in droplets:
        for net in droplet["networks"]["v4"]:
            if net["type"] == "public":
                return False
    return True

