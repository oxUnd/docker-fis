## image of docker for fis


### USE

#### start

- open a terminal ( iterm2 or konsole or same one)
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

- enter the container RUN

    ```
    fis3 server start
    ```

    **NOTICE** keep container running, not exist

#### visit FIS server

- **[MUST]** open other Terminal
- get real port of the FIS server

    ```
    docker port fis
    ```

- get IP

    ```
    boot2docker ip
    ```
- such port `32769`, Browser open `<ip>:32769`

#### release project

- go to the project root of fis

    ```
    cd path/to/fis/proj
    ```

- RUN release command
    
    ```bash
    ### only release
    docker exec fis fis3 release
    # with watch
    docker exec fis fis3 release -w
    # to local dir
    docker exec fis fis3 release -d ./output
    ```

    **NOTICE**

    watch feature must set

    ```js
    fis.set('project.watch.usePolling', true);
    ```

    to `fis-conf.js`

### todo

- [ ] support livereload port map
