# Docker-Docs
This is a Document of my experience about Learning Docker

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

docker run [image-name] -->  run the image that you want 

docker pull [image-name] --> pull image that you want to your images

docker images -->            show you all images you download from dockerHub

docker ps (prossesed) -->    show images that run now !

docker ps -a -->             show archive of all ran images !	

docker rm [Containter ID] -> remove By Container Id  
PAY ATTENTION : if you want to delete some image , first you must delete (rm) containter that run that image , and second you can delete that image. 

docker rmi [IMAGE NAME] --> remove By IMAGE NAME

docker container prune  --> WARNING! This will remove all stopped containers. 

docker stop [Container ID] --> Stop container that is running now

docker start [Container ID] --> Start container By container ID

docker run --rm hello-world --> after running and Stoping hello-world delete from prossesed List OR(docker ps -a)

docker run --rm -it busybox --> while busybox is running ( -it STDIN wait) and after that remove from (docker ps -a)

docker exec [Container ID] [Some Command that image that run on this container support it] --> description is in command.. very useful


-------------------------------------------------------------------------------------------
<h1>how to push some image in your own repository</h1>


1. first you must create new repository from dockerHub 

2. docker tag [reposiory wanted to copy to your own address(username/repositoryName)] [address(more description in last code)]

3. docker login --> login to your dockerHub to acceess to your repositories

4. docker push your address --> address(username/repositoryName) information in 35:0

5. your images pushed to your dockerHub repository  --> check it in your repository in dockerHub

-------------------------------------------------------------------------------------------
<h1>How to set tag for images</h1>
									
1. docker images --> see image that you want to update that tag (default:latest)

2. docker tag [repository-Name (OR images-name)] [image-name:tag (v1,v2,v3,latest)]

3. docker push images-name(OR REPOSITORY-name):tag

----------------------------------------------------------------------------------------------

Formatting images in Docker :
			docker ps --format=" "\nDocker Details \nID:{{.ID}} \nNames: {{.Names}} \nSize: {{.Size}} "
			result - More Human Readable:
		    
			Docker Details
			ID:a1dcca6f78fc
			Names: website
			Size: 1.09kB (virtual 187MB)
			Status: Up 5 minutes
			
			
			


