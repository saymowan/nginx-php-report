## Ngnix PHP Report 📦
Docker image builder based on Nginx + Trafex + Celeron to easy view HTML Files.
Use suggestions:
 - Include all your static HTML test report files to easy folks access 
 -  1 Click view report (better than download them on CI tool as artifact 😁)
 
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