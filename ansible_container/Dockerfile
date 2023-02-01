FROM alpine:3.17

LABEL author="Aron Donaldson (ardonald@cisco.com)"
LABEL description="A simple Docker container for using Ansible to automate Cisco products."

WORKDIR /ansible

COPY ./projects .

RUN apk update \
    && apk add ansible py3-pip \
    && ansible-galaxy collection install cisco.dnac cisco.intersight cisco.aci \
    && pip install dnacentersdk

# Comment this line out if you want to use an interactive shell,
# otherwise simply specify the filename of the Playbook to run.
ENTRYPOINT ["/usr/bin/ansible-playbook"]