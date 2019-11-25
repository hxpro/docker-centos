# docker-centos

Run container from command line
```
    docker run --detach --privileged --volume /sys/fs/cgroup:/sys/fs/cgroup:ro hxpro/docker-centos:8
```

Run by Ansible task

```
    - name: Run container by ansible task  
      docker_container:
          name: centos8
          image: hxpro/docker-centos:8
          command: /usr/sbin/init
          privileged: true
          volumes:
            - "/sys/fs/cgroup:/sys/fs/cgroup:ro"
          state: started    
```
