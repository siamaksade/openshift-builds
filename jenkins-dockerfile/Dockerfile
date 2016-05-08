FROM docker.io/library/jenkins:2.0

MAINTAINER Siamak Sadeghianfar <ssadeghi@redhat.com>

ENV OC_VERSION v1.1.1-e1d9873
ENV JENKINS_HOME /var/jenkins_home
ENV OC_HOME ${JENKINS_HOME}/oc-client

RUN mkdir -p ${OC_HOME} && \
	OV=`echo "${OC_VERSION}" | sed "s/\(.*\)-[a-z0-9]*$/\1/"` && \
	curl -fsSL -o ${OC_HOME}/origin-client.tar.gz https://github.com/openshift/origin/releases/download/$OV/openshift-origin-client-tools-$OC_VERSION-linux-64bit.tar.gz && \
	cd ${OC_HOME} && \
	tar -xf origin-client.tar.gz

RUN echo "PATH=$PATH:${OC_HOME}/openshift-origin-client-tools-#{ORIGIN_VERSION}-linux-64bit" >> ${JENKINS_HOME}/.bash_profile