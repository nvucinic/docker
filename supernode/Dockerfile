FROM  nvucinic/base

MAINTAINER Neven Vucinic neven.vucinic@gmail.com

RUN apt-get update && apt-get install libssl-dev git g++ make cmake gcc  -y --no-install-recommends 

WORKDIR /opt/

RUN git config --global http.sslVerify false
RUN git clone https://github.com/nvucinic/n2n.git

WORKDIR /opt/n2n/n2n_v2/

RUN  cmake ./ && make && make install 

RUN apt-get remove --purge -y git make cmake  && rm -rf /var/lib/apt/lists/*
RUN rm -rf /opt/n2n/


EXPOSE 12345

CMD ["/usr/sbin/supernode", "-l","12345","-f"]
