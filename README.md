# Prometheus + Grafana + Ansible
This is Ansible Playbook that I use to provision new Prometheus and Grafana
node in DigitalOcean.

You can use [my referral](https://m.do.co/c/ddb6db36549a) to get $100
DigitalOcean voucher for 60 days.

## Setup
Clone this repository:

    git clone https://github.com/pyk/prometheus-grafana-ansible.git
    cd prometheus-ansible-grafana/

Create new python environment:

    python3 -m venv venv

Activate the environment:

    source venv/bin/activate

Install the dependencies:

    pip install -r requirements.txt


## Provision

Create new droplet named `prometheus-grafana` with the following command:

    ansible-playbook provision.yaml

Access `http:://IP` to setup the grafana, use username & password `admin:admin`
to login to the first time.
