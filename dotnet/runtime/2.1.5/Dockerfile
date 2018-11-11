FROM centos:7

LABEL dotnet=runtime \
      dotnet-version=2.1.5

#install dependencies
RUN yum -y update \
	&& yum install -y libicu
	
#install dotnet sdk
RUN curl -ssl -o dotnet.tar.gz https://download.visualstudio.microsoft.com/download/pr/05a71d80-3e59-4f1f-8298-2697013e261c/be191f2f4f4db74c29030008ed3632f0/dotnet-runtime-2.1.5-linux-x64.tar.gz \
	&& mkdir -p /opt/dotnet && tar zxf dotnet.tar.gz -C /opt/dotnet \
	&& ln -s /opt/dotnet/dotnet /usr/local/bin \
	&& rm -f dotnet.tar.gz

