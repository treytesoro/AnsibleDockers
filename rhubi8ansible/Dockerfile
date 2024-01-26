FROM redhat/ubi8

RUN yum check-update; \
    yum install -y gcc libffi-devel python3; \
    yum install -y python3-pip; \
    yum install -y wget; \
    yum install -y python3-devel; \
    yum install -y krb5-devel; \
    yum install -y krb5-workstation; \
    yum clean all

RUN pip3 install --upgrade pip; \
    pip3 install --upgrade virtualenv; \
    pip3 install pywinrm[kerberos]; \
    pip3 install pywinrm; \
    pip3 install jmspath; \
    pip3 install requests; \
    pip3 install ansible;

ENTRYPOINT [ "tail", "-f", "/dev/null" ]