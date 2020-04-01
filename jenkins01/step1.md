## Install Jenkins

https://jenkins.io/doc/book/installing/#debianubuntu

`wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | apt-key add -`{{execute}}

`echo "deb https://pkg.jenkins.io/debian-stable binary/" > /etc/apt/sources.list.d/jenkins.list`{{execute}}

`apt update && apt-get install -y jenkins`{{execute}}

`usermod jenkins -a -G docker && systemctl restart jenkins`{{execute}}

## Test, if Jenkins running

`curl -I http://localhost:8080/`{{execute}}

## Open the initial admin password file

`ln -s /var/lib/jenkins/secrets/initialAdminPassword`{{execute}}

Open `initialAdminPassword`{{open}}

## Jenkins Web Link

https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com
