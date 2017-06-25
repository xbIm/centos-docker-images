FROM centos:7

LABEL dotnet=sdk \
      dotnet-version=1.0.4

#install dependencies
RUN yum install -y sudo \
	&& sudo yum -y update \
	&& sudo yum install -y libunwind libicu 
#install dotnet sdk

RUN curl -sSL -o dotnet.tar.gz https://download.microsoft.com/download/E/7/8/E782433E-7737-4E6C-BFBF-290A0A81C3D7/dotnet-dev-centos-x64.1.0.4.tar.gz \
	&& mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet \
	&& ln -s /opt/dotnet/dotnet /usr/local/bin \
	&& rm -f dotnet.tar.gz

# Trigger the population of the local package cache
ENV NUGET_XMLDOC_MODE skip
RUN mkdir warmup \
    && cd warmup \
    && dotnet new \
    && cd .. \
    && rm -rf warmup \
    && rm -rf /tmp/NuGetScratch