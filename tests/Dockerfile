FROM williamyeh/ansible:ubuntu14.04

RUN cd /etc/apt && \
    sed -i 's/archive.ubuntu.com/ftp.neowiz.com/g' sources.list


# ==> Copying Ansible playbook...
WORKDIR /tmp
COPY  .  /tmp

# ==> Creating inventory file...
RUN echo localhost > inventory

# ==> Executing Ansible...

RUN ansible-galaxy install -r install_roles.yml

RUN ansible-playbook -i inventory playbook.yml --connection=local --sudo #