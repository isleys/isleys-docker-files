FROM amazonlinux:2.0.20201218.1

# Default version 0.62
ARG po4a_hash="a2c9de0a"

# Installing a Dependency Library
RUN amazon-linux-extras install epel -y && \
yum install -y git perl-Module-Build perl-Pod-Parser perl-gettext perl-SGMLSpm perl-Text-WrapI18N perl-Unicode-LineBreak perl-YAML-Tiny \
asciidoc libxslt gettext && \
yum clean all

ENV LANG=en_US.UTF-8 LC_ALL=en_US.UTF-8

RUN git clone https://github.com/mquinson/po4a.git && cd po4a/ && \
git checkout ${po4a_hash} && perl Build.PL && ./Build && ./Build install
