polkadot-base
=========

A base role for to configure various Polkadot nodes.

Role Variables
--------------

There are a number of variables that can be customized, with all of them having preset defaults.
These are provided in the format of:

- variable_name: default_value

### Service Ports
- node_exporter_port: 9100
- p2p_port: 30333
- prometheus_port: 9610
- api_rpc_port: 9933
- api_wss_port: 9944
- health_check_port: 5500
- consul_dns_port: 8600
- consul_api_port: 8500
- consul_serf_lan_port: 8301
- consul_serf_wan_port: 8302

### Flags to enable services
- node_exporter_enabled: true
- health_check_enabled: true
- consul_enabled: true

### Node Exporter
- node_exporter_user: prometheus
- node_exporter_password: node_exporter
- node_exporter_binary_url: https://github.com/prometheus/node_exporter/releases/download/v0.18.1/node_exporter-0.18.1.linux-amd64.tar.gz
- node_exporter_binary_checksum: 'sha256:b2503fd932f85f4e5baf161268854bf5d22001869b84f00fd2d1f57b51b72424'

### Polkadot Client
- polkadot_binary_url: "https://github.com/w3f/polkadot/releases/download/v0.8.23/polkadot"
- polkadot_binary_checksum: "sha256:cdf31d39ed54e66489d1afe74ed7549d5bcdf8ff479759e8fc476d17d069901e"
- polkadot_restart_enabled: false
- polkadot_restart_minute: "0"
- polkadot_restart_hour: "0"
- polkadot_restart_day: "*"
- polkadot_restart_month: "*"
- polkadot_restart_weekday: "*"

### Other
- chain: "kusama"


Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: insight_w3f.polkadot_base, x: 42 }

License
-------

Apache 2.0

Author Information
------------------

Maintained by [Richard Mah](https://github.com/shinyfoil) for [Insight Infrastructure](https://github.com/insight-infrastructure)
