# docker-centos

Run container from command line
```
    docker run --detach --privileged --volume /sys/fs/cgroup:/sys/fs/cgroup:ro hxpro/docker-centos
```

Run by Ansible task

```
    - name: Run container by ansible task  
      docker_container:
          name: centos7
          image: hxpro/docker-centos
          command: /usr/sbin/init
          privileged: true
          volumes:
            - "/sys/fs/cgroup:/sys/fs/cgroup:ro"
          state: started    
```
