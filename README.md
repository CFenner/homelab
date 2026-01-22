# Homelab

## Topology

This describes the services in my homelab.

<details><summary>RS422+</summary>

```mermaid
flowchart LR
  subgraph RS422+
    secondary-pihole[Pi-Hole]
    Jellyfin

    syncthing[Syncthing]
  end
```

</details>

<details><summary>RPi5</summary>

```mermaid
flowchart LR

  subgraph RPi5
    Authentik
    Paperless
    
    traefik-rpi5[Traefik]
    watchtower-rpi5[Watchtower]
    syncthing-rpi5[Syncthing]
    portainer-rpi5[Portainer-Agent]
    dockerproxy-rpi5[Docker-Proxy]
  end
```

</details>

<details><summary>RPi3</summary>

```mermaid
flowchart LR

  subgraph RPi3
    Pi-Hole
    Orbital-Sync
    EVCC

    traefik-rpi3[Traefik]
    watchtower-rpi3[Watchtower]
    syncthing-rpi3[Syncthing]
    portainer-rpi3[Portainer-Agent]
    dockerproxy-rpi3[Docker-Proxy]
  end
```

</details>

<details><summary>RPi4</summary>
  
```mermaid
flowchart LR
  subgraph RPi4
    ha[Home Assistant]
    
    portainer-rpi4[Portainer-Agent]
  end
```


</details>

<details><summary>RPi2</summary>
  
```mermaid
flowchart LR

  subgraph RPi2
    Homepage
    Gotify
    traefik-rpi2[Traefik]
    watchtower-rpi2[Watchtower]
    syncthing-rpi2[Syncthing]
    portainer-rpi2[Portainer-Agent]
    dockerproxy-rpi2[Docker-Proxy]
  end
```

</details>

<details><summary>Blade01</summary>
  
```mermaid
flowchart LR

  subgraph Blade01
  end
```

</details>

<details><summary>Blade02</summary>
  
```mermaid
flowchart LR

  subgraph Blade02
  end
```

</details>

## SSH Setup

Generate SSH key on local machine:

```sh
ssh-keygen
```

Copy key over to remote machine:

```sh
ssh-copy-id -i <secret.pub> <user>@<ip>
```

Add the key to the local ssh `config` file:

```sh
echo "Host <ip>\n  IdentityFile ~/.ssh/<secret>" >> ~/.ssh/config
```
