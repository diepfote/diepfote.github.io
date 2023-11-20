# Full archlinux on Mac OS (docker container)

Tries to resemble my personal archlinux system at home as close as possible.  
VM and container runtime set up via `limactl` -> [limactl config](https://github.com/diepfote/dot-files/blob/25f80250cfdd92b2a04c374915c9c0e5628a009f/.lima/default/lima.yaml).

Commands below explicitly require these [Mac OS host mounts](https://github.com/diepfote/dot-files/blob/25f80250cfdd92b2a04c374915c9c0e5628a009f/.lima/default/lima.yaml#L34).

* build process:  
  
  ```
  build-container-image arch-all
  ```

  [command](https://github.com/diepfote/dockerfiles/blob/1c2161a0eb6684516015cfddf2f81db2c4552dcc/bin/build-container-image)  
  [Dockerfile etc.](https://github.com/diepfote/dockerfiles/tree/cd54932a801134daf13ae62c5a8133bd5855fd1b/arch-all)

* running the container

  ```
  run_arch-all
  ```

  [command](https://github.com/diepfote/dockerfiles/blob/8b280ab183278b1b568bea660fe001521c02a640/bin/run_arch-all)


---

by Florian Sorko
