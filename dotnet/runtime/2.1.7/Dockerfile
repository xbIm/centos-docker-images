FROM centos:7

LABEL dotnet=runtime \
      dotnet-version=2.1.7

#install dependencies
RUN yum -y update \
	&& yum install -y libicu
	
#install dotnet sdk
RUN curl -ssl -o dotnet.tar.gz https://download.visualstudio.microsoft.com/download/pr/085b427b-66f6-4cf5-bee3-5f4cbef2b72c/9c1ad276cf957258d123a3b268ec9304/aspnetcore-runtime-2.1.7-linux-x64.tar.gz \
	&& mkdir -p /opt/dotnet && tar zxf dotnet.tar.gz -C /opt/dotnet \
	&& ln -s /opt/dotnet/dotnet /usr/local/bin \
	&& rm -f dotnet.tar.gz

