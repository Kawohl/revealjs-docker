<section data-state="no-title-footer">
## Docker  
Build, run, ship,  any app,  anywhere. ![docker-logo](https://raw.githubusercontent.com/Kawohl/presentations/master/docker/reveal.js/presentations/johnspresentation/rsz_1docker-small.png)
---

## Überblick

* Was sind eigentlich Linux Container?

* Linux Container im Vergleich zu VM´s

* Docker vs. LXC 

* Anwendungsszenarien 

* Die Zukunft? 

---

## Linux Container 

* Virtualisierung mit einem Kernel

* Prozesse durch Namespaces getrennt

* Komplette isolation voneinander und vom Host möglich

* Beispiele für Linux Container: docker, LXC, LXD, rkt

* Alle Libs und Abhängikeiten in einem "Paket" 

---

## Control Groups (Cgroups)

Verwaltung und Überwachung von Ressourcen:

**Beispiele:**
* Ram

* CPU

* Netzwerk

* I/O Festplatte 

---

## Namespace 

**Beispiele:**

* Verwaltung der Sichtbarkeit von Prozessen:

* pid

* net

* mnt

* user    

---

## Warum Container?

* Effiziente Ressourcen Nutzung

* Prozessisolierung


---

## Docker vs. Virtuelle Maschinen 
![container-vm-comparison](https://cloud.githubusercontent.com/assets/12275313/23125280/3fcb2ab0-f771-11e6-9d13-e2dd6fb55e0f.png)
---

![meme](https://github.com/Kawohl/presentations/blob/master/docker/reveal.js/presentations/johnspresentation/wfmmeme.jpg?raw=true)


---


## Warum Docker

* Erweitert Linux Container u.a. um Portabilität

* Industriestandard 

* Vielzahl an tools und implementierungen 

* integriert in Google Cloud Platform, Amazon Web Services, azure container-services u.v.m. 

* Sehr einfaches interface design 

* open Source



---

<p>
  <br>
  <br>
  <br>
</p>



```
FROM debian
RUN \
    apt-get update && \
    apt-get install -y \
        openssh-server && \
    mkdir /var/run/sshd && \
    sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
```


---


#### docker Ökosystem 
![overview](https://raw.githubusercontent.com/Kawohl/presentations/20b535b991dc08c91a03c9b5bed33b43d3ecd4be/docker/reveal.js/presentations/johnspresentation/dockerUsers.png)

---


## Docker in meinem Arbeitsalltag
* pakete testen: z.b. : 
```
docker run -ti centos:7
```

* owncloud Test-Instanz hochfahren: 
```
git clone https://github.com/owncloud-docker/server.git
cd server/
docker-compose up 
```

* container image von Dockerhub ziehen: 
```
docker pull ubuntu:16.04
```


---

## Nutzungsszenarien: 

* Entwicklungsumgebung
 
* Effektive Nutzung von Ressourcen

* Deployment on Demand: Lastspitzen abfangen 

* Portabilität: Migrationen sind einfach

---

## Ausblick:

* Große Verbreitung 
* Immer mehr tools zur Vereinfachung des Setups
* "Enterprise" Container
* Scalierung 
* Deployment on Demand



---

## Zusammenfassung

* relativ "Einfaches" Interface

* "wfm": "Bei mir läuft das aber" ist kein Problem mehr.

* Datenpersistenz durch mountpoints auf dem Dateisystem
 
* Effektive Ressourcennutzung und Verwaltung

* In der cloud quasi unendlich skalierbar  

---

Den Sourcecode zu dieser Präsentation gibt es hier: 
https://github.com/Kawohl/presentations

Das docker image: 
```
docker pull jonaka/dockerpres
```
---


######Links:

* https://www.docker.com/
* https://traefik.io/
* https://kubernetes.io/
* https://twitter.com/JonathanKawohl
* https://github.com/Kawohl/


---



