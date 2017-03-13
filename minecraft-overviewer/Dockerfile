FROM centos:6

RUN yum -y -q install atlas freetype libgfortran libjpeg-turbo numpy python-imaging python-nose python-setuptools wget

RUN curl -sS http://overviewer.org/rpms/overviewer.repo > /etc/yum.repos.d/overviewer.repo

RUN yum install -y Minecraft-Overviewer

RUN  export VERSION=1.11 &&  wget https://s3.amazonaws.com/Minecraft.Download/versions/${VERSION}/${VERSION}.jar -P ~/.minecraft/versions/${VERSION}/
