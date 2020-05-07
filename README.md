# Prometheus + Grafana + Ansible

This is Ansible Playbook that I use to provision new Prometheus and Grafana
node in DigitalOcean.

You can use [my referral](https://m.do.co/c/ddb6db36549a) to get $100
DigitalOcean voucher for 60 days.


## Setup

Clone this repository:

    git clone https://github.com/pyk/prometheus-grafana-ansible.git
    cd prometheus-grafana-ansible/

Create new python environment:

    python3 -m venv venv

Activate the environment:

    source venv/bin/activate

Install the dependencies:

    pip install -r requirements.txt


## Provision

Create new `secrets.yaml` file with the following content:

    digitalocean:
        access_token: ACCESS_TOKEN
        droplet_name: DROPLET_NAME

    prometheus:
        user: USERNAME
        pass: PASSWORD

You can create new access token in your DigitalOcean dashboard.

    Account > API > Personal access tokens

Then you can provision new node with prometheus and grafana installed using the
following command:

    ansible-playbook provision.yaml

Go to `http:://IP_ADDRESS` to setup the grafana, use username & password `admin:admin`
to login to the first time.

Go to `http://IP_ADRESS:9000` to access the prometheus.


## Configuration

To update grafana configuration, you can update `grafana/grafana.ini` file.

To update prometheus configuration, you can update `prometheus/prometheus.yaml`
file.

To apply the update, rerun the following command:

    ansible-playbook provision.yaml

This will update existing droplet with the same `digitalocean.droplet_name`.
