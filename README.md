# runing nginx image in container 
 In this provider is Docker 
 provider "docker" {}

and i use nginx image 

resource "docker_image" "nginx" {
  name         = "nginx"
  keep_locally = false
}

after thi running this image on docker container 

resource "docker_container" "nginx" {
  image = docker_image.nginx.image_id
  name  = "tutorial"
}

<h4>default port for HTTP in 80 and im running it on 8000 </h4>
ports {
    internal = 80
    external = 8000
  }
  
  
