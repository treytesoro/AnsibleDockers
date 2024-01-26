FROM debian


RUN apt update && \
    apt upgrade -y && \
    apt install -y gcc cmake libffi-dev && \
    apt install -y nano && \
    apt install -y vim && \
    apt install -y curl && \
    apt install -y wget && \
    apt install -y libkrb5-dev && \
    apt install -y krb5-user && \
    # We need all this for python3.11
    apt install -y libssl-dev libncurses5-dev libsqlite3-dev libreadline-dev libtk8.6 libgdm-dev libdb4o-cil-dev libpcap-dev && \
    wget https://www.python.org/ftp/python/3.11.3/Python-3.11.3.tgz && \
    tar xzf Python-3.11.3.tgz && \
    cd Python-3.11.3 && ./configure --enable-optimizations && make altinstall && \
    apt install -y python3.11-dev && \
    apt clean all
	
# If you make any changes above this layer or prune your build cache, it will take forever to rebuild
RUN pip3.11 install --upgrade pip && \
    pip3.11 install --upgrade virtualenv && \
    pip3.11 install pywinrm[kerberos] && \
    pip3.11 install jmspath && \
    pip3.11 install requests && \
    pip3.11 install ansible

ENTRYPOINT [ "tail", "-f", "/dev/null" ]