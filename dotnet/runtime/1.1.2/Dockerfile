FROM centos:7

LABEL dotnet=runtime \
      dotnet-version=1.1.2

#install dependencies
RUN yum -y update \
	&& yum install -y libunwind libicu
	
#install dotnet sdk
RUN curl -ssl -o dotnet.tar.gz https://download.microsoft.com/download/D/7/A/D7A9E4E9-5D25-4F0C-B071-210CB8267943/dotnet-centos-x64.1.1.2.tar.gz \
	&& mkdir -p /opt/dotnet && tar zxf dotnet.tar.gz -C /opt/dotnet \
	&& ln -s /opt/dotnet/dotnet /usr/local/bin \
	&& rm -f dotnet.tar.gz

