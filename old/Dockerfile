FROM bechtoldt/saltstack_formula_tests:{{ TEST_OS }}_{{ TEST_SALTVERSION }}
MAINTAINER Arnold Bechtoldt <mail@arnoldbechtoldt.com>

COPY data/etc/salt/ /etc/salt
COPY data/srv/salt/ /srv/salt

#RUN wget -q \
#    --no-check-certificate \
#    --no-cookies \
#    --header "Cookie: oraclelicense=accept-securebackup-cookie" \
#    -O /tmp/jdk-8u66-linux-x64.tar.gz \
#    http://download.oracle.com/otn-pub/java/jdk/8u66-b17/jdk-8u66-linux-x64.tar.gz

RUN salt-call --local --retcode-passthrough --out=json test.version
RUN salt-call --local --retcode-passthrough --out=json state.show_sls elasticsearch
#RUN salt-call --local --retcode-passthrough state.sls repos,java,elasticsearch test=True
