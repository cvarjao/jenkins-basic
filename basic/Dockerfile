FROM local/jenkins:core

USER root

COPY ./contrib/jenkins/configuration $JENKINS_REF_HOME

RUN set -x && \
    chgrp -R 0 $JENKINS_REF_HOME && \
    chmod -R 644 $JENKINS_REF_HOME && \
    chmod -R g+rwX $JENKINS_REF_HOME && \
    (export REF=$JENKINS_REF_HOME/plugins; /usr/local/bin/jenkins-install-plugins $JENKINS_REF_HOME/plugins.txt)

USER 1001

