# Traefik
        networks:
            - web
        labels:
            - "traefik.enable=true"
            - "traefik.http.routers.se.rule=Host(`sections-europeennes.fr.localhost`)"
            - "traefik.http.routers.se.rule=Host(`sections-europeennes-preprod.ac-montpellier.fr`, `vml2011docker-03.ac-montpellier.fr`)"
            - "traefik.http.routers.se.entrypoints=web"
            - "traefik.http.services.app.loadbalancer.server.port=80"
            - "traefik.docker.network=web"


      networks:
          se-network :
          web:
              external: true
                  
