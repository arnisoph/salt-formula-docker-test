FROM bechtoldt/saltstack_formula_tests:{{ TEST_OS }}_{{ TEST_SALTVERSION }}
MAINTAINER Arnold Bechtoldt <mail@arnoldbechtoldt.com>

COPY data/etc/salt/ /etc/salt
COPY data/srv/salt/ /srv/salt

RUN salt-call --local --retcode-passthrough --out=json test.version
RUN salt-call --local --retcode-passthrough --out=json state.show_sls {{ TEST_SLS }}
