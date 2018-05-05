# Docker as Development Workbench

Using Docker Compose to setup a **Development** environments; The goal is not for the production, but having isolated environment for development.

# How does it work?

`docker-compose` allows setting up multiple applications (called `services`) and allows inter-dependencies among `services`.

For the purpose of setting up seprate developments, each `service` is setup as an isolated development environment, including databases.


# General Structure

In `docker-compose.yml`, 

> # Sample Set Up
> 
> ```
> version: '3'
> services:
>  my_elixir:
>    build: ./elixir
>    volumes:
>     - /Users/john/code:/code
>    working_dir: /code
> ```

* defines a development environment as a `service`
    * `build`
      * the location desired development environment Dockerfile
      * ie. `./elixir/Dockerfile` means start up with the elixir runtimes
    * `volume`
      * the path to source code
    * `working_dir`
      * the default path upon login

* `run.sh SERVICE_NAME`
  * shortcut to start the `SERVICE_NAME` shell
    * the same as running `> docker-compose run SERVICE_NAME /bin/zsh`
    * ie `> run.sh my_elixir`

  # Starting Up
  
  * `> docker-compose up`
      * build and initialise all environments
  * `> docker-compose ps`
      * list all containers
  
  ```
  
  ```

