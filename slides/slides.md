<section data-state="no-title-footer">
## __Docker__  
Build, run, ship,  any app,  anywhere. ![docker-logo](https://raw.githubusercontent.com/Kawohl/presentations/master/docker/reveal.js/presentations/johnspresentation/rsz_1docker-small.png)

---
## __Jonathan Kawohl__ 

<p>
  <br>
</p>




* Momentan tätig im second und third level support.

* Vorher: Marketing und Community Management.

* Docker als automatisierte Testumgebung aufgesetzt.

* Jetzt: Docker zum schnellen reproduzieren von Support Cases.

---
 ![ya'llmeme ](https://github.com/Kawohl/revealjs-docker/raw/master/docker/images/y'all.jpg)
---


## __Überblick__

<p>
  <br>
</p>

* Was sind eigentlich Linux Container?

* Linux Container im Vergleich zu VM´s

* Docker vs. LXC 

* Anwendungsszenarien 

* Die Zukunft? 

---

## __Linux Container__ 

<p>
  <br>
</p>

* Virtualisierung mit einem Kernel

* Prozesse durch Namespaces getrennt

* Komplette isolation voneinander und vom Host möglich

* Beispiele für Linux Container: docker, LXC, LXD, rkt


---

## __Control Groups (Cgroups)__

<p>
  <br>
</p>

* Verwaltung und Überwachung von Ressourcen:

* Ram

* CPU

* Netzwerk

* I/O 

---

## __Namespace__ 
<p>
  <br>
</p>

* Verwaltung der Sichtbarkeit von Prozessen:

* pid

* net

* mnt

* user    

---

## __Warum Container?__

<p>
  <br>
  <br>
  <br>
</p>


* ### Effiziente Ressourcen Nutzung

* ### Prozessisolierung


---

## __Docker vs. Virtuelle Maschinen__ 
![container-vm-comparison](https://cloud.githubusercontent.com/assets/12275313/23125280/3fcb2ab0-f771-11e6-9d13-e2dd6fb55e0f.png)
---

![meme](https://github.com/Kawohl/presentations/blob/master/docker/reveal.js/presentations/johnspresentation/wfmmeme.jpg?raw=true)


---


## __Warum Docker__ ? 

* Erweitert Linux Container u.a. um Portabilität

* Alle Libs und Abhängikeiten in einem "Paket" 

* Vielzahl an tools und implementierungen 

* integriert in Google Cloud Platform, Amazon Web Services etc

* Sehr einfaches interface design 

* open Source



---

#### Beispiel für den code für einen ssh server
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


#### __docker Ökosystem__ 

![overview](https://raw.githubusercontent.com/Kawohl/presentations/20b535b991dc08c91a03c9b5bed33b43d3ecd4be/docker/reveal.js/presentations/johnspresentation/dockerUsers.png)

---


## __Docker in meinem Arbeitsalltag__
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

## __Nutzungsszenarien:__ 

<p>
  <br>
  <br>
</p>

* Entwicklungsumgebung
 
* Effektive Nutzung von Ressourcen

* Deployment on Demand: Lastspitzen abfangen 

* Portabilität: Migrationen sind einfach

---

## __Ausblick:__

<p>
  <br>
  <br>
</p>

* Große Verbreitung 

* Immer mehr tools zur Vereinfachung des Setups

* "Enterprise" Container

* Auto-Skalierung 

* Deployment on Demand



---

## __Zusammenfassung__
<p>
  <br>
  <br>
</p>

* relativ "Einfaches" Interface

* "wfm": "Bei mir läuft das aber" ist kein Problem mehr.

* Datenpersistenz durch mountpoints auf dem Dateisystem
 
* Effektive Ressourcennutzung und Verwaltung

* In der cloud quasi unendlich skalierbar  

---

Den Sourcecode zu dieser Präsentation gibt es hier: 
https://github.com/Kawohl/revealjs-docker
  <br>
</p>

Das docker image: 
```
docker pull jonaka/dockerpres
```

---

<p>
  <br>
  <br>
  <br>
</p>

#Fragen? 




---


##__Links:__

* https://www.docker.com/

* https://traefik.io/

* https://kubernetes.io/

* https://twitter.com/JonathanKawohl

* https://github.com/Kawohl/






