**Fork of https://github.com/akaihola/docker-vma/pulls with Proxmox 6 support**

# Usage

1. Clone this repo
2. cd to local repo folder
3. mkdir ./out
4. docker build --rm -f Dockerfile -t vma .
5. docker run --rm -it --name vma -v $PWD/out:/out vma
6. use `vma` utility inside the container

To convert vma images to qcow2 inside the container:
1. cd /out
2. vma extract <FILENAME>.vma <DEST_FOLDER>
3. stop the container and return to the host OS
4. qemu-img convert -f raw -O qcow2 out/<DEST_FOLDER>/disk-drive-scsi0.raw out/<DEST_FOLDER>/final-image.qcow2