FROM docker.io/library/jenkins:2.0

MAINTAINER Siamak Sadeghianfar <ssadeghi@redhat.com>

ENV OC_VERSION v1.1.1-e1d9873

RUN OV=`echo "${OC_VERSION}" | sed "s/\(.*\)-[a-z0-9]*$/\1/"` && \
	curl -fsSL -o /tmp/origin-client.tar.gz https://github.com/openshift/origin/releases/download/$OV/openshift-origin-client-tools-$OC_VERSION-linux-64bit.tar.gz && \
	cd /tmp && \
	tar -xf origin-client.tar.gz

USER root
RUN cp /tmp/openshift-origin-client-tools-$OC_VERSION-linux-64bit/oc /usr/local/bin
USER jenkins
