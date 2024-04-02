# **Correction TP LINUX**

1. useradd test

- usermod -aG sudo testeu

3. apt update -y && apt upgrade -y

4. useradd technicien && userade salarie

5. usermod -l sysadmin technicien

6. userdel salarie

- deluser

7. apt install ssh

8.  

 - ssh-keygen
 - mkdir ~/.ssh
 - touch authorized_keys
 - chmod 660 ~/.ssh
 - chmod 600 authorized_keys
 - Get-Content $HOME\.ssh\id_rsa.pub | ssh utilisateur@192.168.1.42 "cat >> .ssh/authorized_keys"
 
 - sudo nano /etc/ssh/sshd_config
    - GNU nano MaxSession 2
    - AllowUser utilisateur sysadmin
    - PermitRootLogin no
    - Aller sur wikipedia port = à partir de 1024 port
    - ctrl + x pour sauvegarder

9. sudo apt install ufw -y

- sudo nano /etc/default/ufw
    - IPV6=no
    - ctrl + x pour sa sauvegarde
    - sudo ufw allow 2874/tcp

10. sudo systemctl restart ssh

11. ssh utilisateur@192.168.0.10 -p 2874

12. sudo journalctl -u ssh --since "2024-04-02 09:00:00"

13. sudo chmod 1777 /tmp

- crontab -e
    - 30 9 10 * * journamctl -u ssh >> ~/ssh_logs.txt
    - échap : wq

14. sudo apt install neofetch -y

- neofetch

15. Google docker install debian 

- install Docker Engine on Debian
- sudo apt-get update
- sudo apt-get install ca-certificates curl
- sudo install -m 0755 -d /etc/apt/keyrings
- sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
- sudo chmod a+r /etc/apt/keyrings/docker.asc

- echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

- sudo apt-get update

16. sudo usermod -aG docker $USER

17. sudo systemctl enable docker

18. 

- docker volume create portainer_data

- docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest

19. 

20. mkdir ~/DOCKER

- cd ..
- ls

21. cd DOCKER

- nano docker-compose.yaml
    - # Simple docker-compose.yml
# You can change your port or volume location

version: '3.8'

services:
  uptime-kuma:
    image: louislam/uptime-kuma:1
    container_name: uptime-kuma
    volumes:
      - ./uptime-kuma-data:/app/data
    ports:
      - 3001:3001  # <Host Port>:<Container Port>
    restart: always

- docker-compose up -d

22. sudo chmod 770 docker-compose.yaml

- sudo chmod ug+rwx docker-compose.yaml

23. Google grafana docker compose template

-   grafana:
    container_name: grafana
    image: grafana/grafana-oss
    ports:
      - "3000:3000"
    environment:
      - GF_PATHS_CONFIG=/etc/grafana/custom.ini
    volumes:
      - ./config/grafana/custom.ini:/etc/grafana/custom.ini
      - ./config/grafana/provisioning/:/etc/grafana/provisioning/
      - type: bind
        source: ./config/grafana/dashboard.json
        target: /var/lib/grafana/dashboards/curity/idsvr-dashboard.json
    links:
      - prometheus
    networks:
      demonetwork:
        aliases:
          - grafana

networks:
  demonetwork:
    name: metrics-demo-net

- docker-compose down ou kill

24. 3001:3001 