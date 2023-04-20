# runing nginx image in container 
<h4> In this provider is Docker </h4>
 provider "docker" {}

<h4>and i use nginx image </h4>

resource "docker_image" "nginx" {
  name         = "nginx"
  keep_locally = false
}

 <h4> after this running this image on docker container </h4>

resource "docker_container" "nginx" {
  image = docker_image.nginx.image_id
  name  = "tutorial"
}

<h4>default port for HTTP in 80 and im running it on 8000 </h4>
ports {
    internal = 80
    external = 8000
  }
  
 <h4>after all configuration select terraform pipeline from github action  </h4>
 
 <h5> in pipeline nginx image is downloaded and this is running on docker container</h5>
