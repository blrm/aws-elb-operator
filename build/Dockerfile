FROM registry.access.redhat.com/ubi7/ubi-minimal:latest

ENV OPERATOR=/usr/local/bin/aws-elb-operator \
    USER_UID=1001 \
    USER_NAME=aws-elb-operator

# install operator binary
COPY build/_output/bin/aws-elb-operator ${OPERATOR}

COPY build/bin /usr/local/bin
RUN  /usr/local/bin/user_setup

ENTRYPOINT ["/usr/local/bin/entrypoint"]

USER ${USER_UID}
