FROM centos:7

LABEL dotnet=sdk \
      dotnet-version=2.1.503

#install dependencies
RUN yum -y update \
 && yum install -y libunwind libicu epel-release 

#install dotnet sdk

RUN curl -sSL -o dotnet.tar.gz https://download.visualstudio.microsoft.com/download/pr/04d83723-8370-4b54-b8b9-55708822fcde/63aab1f4d0be5246e3a92e1eb3063935/dotnet-sdk-2.1.503-linux-x64.tar.gz \
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