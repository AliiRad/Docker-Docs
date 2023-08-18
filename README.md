# Docker-Docs
This is a Document of my experience about Learning Docker

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
run the image that you want 

		docker run [image-name] 
		

pull image that you want to your images

		docker pull [image-name]
		

show you all images you download from dockerHub

		docker images 
		
		
show images that run now !

		docker ps (prossesed)
		

show archive of all ran images !

		docker ps -a 
		
	
remove By Container Id
PAY ATTENTION : if you want to delete some image , first you must delete (rm) containter that run that image , and second you can delete that image. 

		docker rm [Containter ID] 
		
  
remove By IMAGE NAME

		docker rmi [IMAGE NAME]
		

WARNING! This will remove all stopped containers. 

		docker container prune  
		

Stop container that is running now

		docker stop [Container ID] 
		

Start container By container ID

		docker start [Container ID] 
		
		
after running and Stoping hello-world delete from prossesed List OR(docker ps -a)

		docker run --rm hello-world 
		

while busybox is running ( -it STDIN wait) and after that remove from (docker ps -a)

		docker run --rm -it busybox 
		

description is in command.. very useful

		docker exec [Container ID] [Some Command that image that run on this container support it] 



-------------------------------------------------------------------------------------------
<h1>how to push some image in your own repository</h1>


1. first you must create new repository from dockerHub 

2. 		docker tag [reposiory wanted to copy to your own address(username/repositoryName)] [address(more description in last code)]

3. docker login --> login to your dockerHub to acceess to your repositories

4. docker push your address --> address(username/repositoryName) information in 35:0

5. your images pushed to your dockerHub repository  --> check it in your repository in dockerHub

-------------------------------------------------------------------------------------------
<h1>How to set tag for images</h1>

see image that you want to update that tag (default:latest)
						
1. 		docker images 


2. 		docker tag [repository-Name (OR images-name)] [image-name:tag (v1,v2,v3,latest)]

3. 		docker push images-name(OR REPOSITORY-name):tag

----------------------------------------------------------------------------------------------

<h1>Formatting images in Docker</h1>

<h3><strong>What it Formatting</strong></h3>
		<h4>Formatting is a method to show "docker ps" but with more human readable info</h4>

			docker ps --format=" "\nDocker Details \nID:{{.ID}} \nNames: {{.Names}} \nSize: {{.Size}} "
			result - More Human Readable:
		    
			Docker Details
			ID:a1dcca6f78fc
			Names: website
			Size: 1.09kB (virtual 187MB)
			Status: Up 5 minutes
			
			
		
<h1>Volums In Docker </h1>

volume is a method to share data from started container and our System

For example in this Command i authowired between NGINX directory on web and my tools/Docker folder in my system . 
so if i save file in tools/Docker , it must save in Nginx directory Or if a file or somthing save in NGINX directory on web ,
it must save in my directory that is tools/Docker

		docker run --name website -v /some/content:/desktop/tools/docker:ro nginx:latest
		

<h1>Mounting in docker</h1>

<h2>What is mounting</h2>
<strong>mounting means that you wnat to set a folder of file from your system to Cloud Service that is running now</strong>

<h3>Example of Mounting</h3>
In this example i want to set index.html file to my nginx cloud directory
			docker run --name website -vC:\Users\Sazgar\Desktop\website:/usr/share/nginx/html:ro -d -p 8080:80 nginx:latest
			
			<h4>Explain</h4> :
			1. --name = set name to my container to make easier work for delete or stop it
			2. -v Volumes = mount C:/Users\Sazgar\Desktop\website To Nginx cloud directory that is /user/share/nginx/html
			3. :ro = read Only
			4. -d = dettach after stop container (remove container after stop)
			5. -p myPort:ImagePort(Container Port) = authowired Port to 8080 of my Web from 80 of NGINX Port OR (Container Port)
			6. nginx:latest = say to docker that image i want to run is nginx (If i dont write latest tag , docker automatically use latest version on Image)