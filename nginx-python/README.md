nginx-python
============

Description
-----------

This folder creates a Docker deploy with all you need for testing your Python API made in Flask. This deploy is intended for a developement stage of your front-end application, made in any language, such as node-js.

`nginx` comes as-is, it has no PHP, ruby or perl interpreter inside. It's the same like you would've downloaded it from your linux console. In that case, you could create a Dockerfile with the files required for running your frontend app.

Usage
-----

You need to install Docker on you Linux distro. For debian, is as simple as `sudo apt-install docker.io`. If you use any other distro, you can look for specific instructions for it.

Once you have installed, you can run this commands (As root or sudo):

```
cd /path/to/this/folder/
docker compose -p yourproyectname up -d (This runs this deploy detached from screen, in case you want to see its output, you can remove -d)
```

Once you're done, if you've run detached, you can run this command to stop all your containers inside this deployment (If you didn't run detached, you can just press Ctrl-C):

`docker compose -p yourproyectname down`

Docker will download all required images for running.

Notes
-----

This deploy copies your .py files into a Python image and install its required modules (loaded from requirements.txt), and then runs a Flask App. If you ever need to update its files, you need to rebuild the image.

If you just stop the deployment, and re-run it, it won't recreate Python image with your fresh files.

You can rebuild all images by going to your back/Dockerfile and running `docker-compose build --no-cache`, so it recreates that image. I made this for safety measures, so I know which version is a frontend developer is using.


Feedback
--------

Please feel free to collaborate, make a pull request, comment or fork this. I'd love to hear your feedback and learn in the process!
