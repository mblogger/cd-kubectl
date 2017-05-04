FROM jenkinsci/jnlp-slave
MAINTAINER Vic Iglesias <viglesias@google.com>

ENV CLOUDSDK_CORE_DISABLE_PROMPTS 1
ENV PATH /opt/google-cloud-sdk/bin:$PATH

USER root

#==============
# VNC and Xvfb
#==============
RUN apt-get update -y \
  && apt-get -qqy install xvfb \
  && rm -rf /var/lib/apt/lists/*

RUN apt-get install -y jq
RUN curl https://sdk.cloud.google.com | bash && mv google-cloud-sdk /opt
RUN gcloud components install kubectl
