#
# Copyright 2016 Red Hat, Inc. and/or its affiliates
# and other contributors as indicated by the @author tags.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

FROM jboss/base-jdk:8

USER root

# Set the JBOSS_VERSION env variable
ENV JBOSS_VERSION 7.0.0
ENV JBOSS_HOME /opt/jboss/jboss-eap-7.0

WORKDIR /opt/jboss

RUN yum install -y wget
RUN wget http://download.devel.redhat.com/released/JBEAP-7/7.0.0/jboss-eap-${JBOSS_VERSION}.zip

RUN unzip jboss-eap-$JBOSS_VERSION.zip \
    && rm jboss-eap-$JBOSS_VERSION.zip \
    && chown -R jboss:jboss ${JBOSS_HOME}

ENV LAUNCH_JBOSS_IN_BACKGROUND true

# Expose ports
EXPOSE 8080 9990

USER jboss

# Boot JBoss EAP in the standalone mode and bind to all interface
CMD ["/opt/jboss/jboss-eap-7.0/bin/standalone.sh", "-b", "0.0.0.0", "-bmanagement", "0.0.0.0"]
