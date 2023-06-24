First layer of a image is a **scratch**.
Creating new image is easier cause of cashe. 
Each layer is unique and stored on a host system.

`docker image history nameofimage` history of all layers.

`docker image inspect nameofimage` inspecting all information about layers in an image.\
Images: file system changes and metadata.

**Container is an layer read and write only on top of image**.

Repository of a image is organization or username who created this. Official doesn't need that.

**Tags are labels which point to image id. Downloading image with different tag will be shown in docker image history as two different images, but ID will be the same**.

Double ampersand **&&** in dockerfile is a way to add something **to the same layer**.

`docker image build -t nameofimage .` building image form dockerfile inside this directory (the dot at the end).

Chashed layers are built quickly, but lines changed will be executed again and **every line after changed one** - layers built on top of that.

