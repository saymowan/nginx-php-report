## Ngnix PHP Report 📦
Docker image builder based on [Nginx](https://www.nginx.com/) + [Trafex](https://hub.docker.com/r/trafex/alpine-nginx-php7/) + [Celeron](https://gitlab.com/desbest/celeron-dude-indexer.git) to easy view HTML Files.
Use suggestions:
 - Include all your static HTML test report files to easy folks access 
   - E.g. [Mocha Awesome](https://www.npmjs.com/package/mochawesome), [Allure Report](http://allure.qatools.ru/), [ExtentReports](https://www.extentreports.com/)
 -  1 Click view reports (better than download them on CI tool as artifact 😁  )

### Build the Docker image
 - `docker build -t nginx-trafex-celeron .`   

### Run a container image based
 - `docker run --rm --name nginx-php-report -p 80:8080 nginx-trafex-celeron` 

### Run a container image based including volume (files)
 - `docker run --rm --name nginx-php-report2 -p 80:8080 -v "$(pwd):/var/www/html" -w "/var/www/html/" nginx-trafex-celeron` 

### Copy your new html static website to the current container
 - Current file/folder directory and `docker cp file_to_upload.txt nginx-trafex-celeron:/var/www/html`

### Easy access the container running
 - Go to your favorite web browser and `http://localhost:8080/index.php`

### Enter in the running container (prompt sh)
 - `docker exec -it --user root nginx-trafex-celeron sh`
