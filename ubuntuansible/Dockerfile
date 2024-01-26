FROM ubuntu

RUN apt update && \
    apt upgrade -y && \
    apt install -y gcc libffi-dev python3.11 && \
    apt install -y curl && \
    apt install -y wget && \
    apt install -y python3.11-dev && \
    apt install -y libkrb5-dev && \
    apt install -y krb5-user && \
    apt clean all && \
    curl -sS https://bootstrap.pypa.io/get-pip.py | python3.11 

RUN pip3 install --upgrade pip && \
    pip3 install --upgrade virtualenv && \
    pip3 install pywinrm[kerberos] && \
    pip3 install jmspath && \
    pip3 install requests && \
    pip3 install ansible

ENTRYPOINT [ "tail", "-f", "/dev/null" ]