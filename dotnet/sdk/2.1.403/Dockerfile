FROM centos:7

LABEL dotnet=sdk \
      dotnet-version=2.1.401

#install dependencies
RUN yum -y update \
 && yum install -y libunwind libicu epel-release 

#install dotnet sdk

RUN curl -sSL -o dotnet.tar.gz https://download.visualstudio.microsoft.com/download/pr/e85de743-f80b-481b-b10e-d2e37f05a7ce/0bf3ff93417e19ad8d6b2d3ded84d664/dotnet-sdk-2.1.403-linux-x64.tar.gz \
 && mkdir -p /opt/dotnet && tar zxf dotnet.tar.gz -C /opt/dotnet \
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