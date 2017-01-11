A docker image for ansible target machine with dependent tools pre-installed.

# Example usage

- Create a container that listens on 80 port without running any services.
  (So you can test your ansible playbook on the container.)

      docker run -d --expose 80 beatada/ansible:trusty tail -f /dev/null

- docker-compose exmaple:

    - Setup `docker-compose.yml`
    
      ```
      db:
        container_name: db
        restart: always
        image: beatada/ansible:trusty
        expose:
          - "3306"
      ```

    - Create the container
      ```
      $ docker-compose up -d db
      ```
