#Download base neurodebian
#ran into several issues with ubuntu 18.04 image
#need to run docker as --priviledged
#see https://github.com/sylabs/singularity/issues/632
FROM neurodebian:latest

# Update Ubuntu Software repository
RUN apt-get -y  update -qqq

# Want some editors as I may go into interactive shells
RUN apt-get -y install vim
RUN apt-get -y install emacs
RUN apt-get -y install singularity-container