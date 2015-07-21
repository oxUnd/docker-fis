## image of docker for fis


### USE

#### start

- run docker

    ```
    boot2docker start
    boot2docker shellinit
    ```
- go to the project ROOT of fis

    ```
    cd path/to/fis/proj
    ```
- run a container from fis image

    ```
    docker run -it -P -v "$PWD":/usr/src/app --rm --name fis fis
    ```

- enter container RUN

    ```
    fis3 server start
    ```

    **NOTICE** keep container running, not exist

#### visit FIS server

- open other ternimal
- get real port of the FIS server

    ```
    docker port fis
    ```

- get IP

    ```
    boot2docker ip
    ```
- such port `32769`, Browser open '<pi>:32769'

#### release project

- go to the project root of fis

    ```
    cd path/to/fis/proj
    ```

- RUN release command
    
    ```
    docker exec fis fis3 release
    ```

### todo

- [ ] support livereload port map