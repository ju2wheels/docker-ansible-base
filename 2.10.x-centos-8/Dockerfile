FROM       centos:8
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV LANG               "en_US.UTF-8"
ENV LANGUAGE           "en_US.UTF-8"
ENV LC_ALL             "en_US.UTF-8"
ENV PATH               "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV PYCURL_SSL_LIBRARY "nss"
ENV PYTHONUNBUFFERED   "1"

RUN yum upgrade -y                               && \
    yum install -y crontabs                         \
                   curl                             \
                   dnf                              \
                   git                              \
                   gnupg2                           \
                   openssl                          \
                   python3                          \
                   python3-devel                    \
                   python3-dnf                      \
                   python3-pip                      \
                   python3-setuptools               \
                   rsync                         && \
    python3 -m pip install --force-reinstall        \
                           --upgrade                \
                           --user pip            && \
    python3 -m pip install --force-reinstall        \
                           --upgrade                \
                           --user setuptools     && \
    python3 -m pip install --force-reinstall        \
                 --upgrade                          \
                 --user "ansible-base == 2.10.*" && \
    rm -rf /root/.cache                                                                        \
           /var/cache/yum

CMD        []
ENTRYPOINT ["ansible-playbook"]
