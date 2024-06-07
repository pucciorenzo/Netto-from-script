# Netto deployment with Ansible
This ansible script allows to install [Netto](https://github.com/miolad/netto) tool on a set of hosts.
## Requisites
- Linux Kernel version: **5.5**
- Netto conteiner run in `--privileged` mode.
## Install Netto
Clone this repository and enter in the folder:
```
git clone https://github.com/pucciorenzo/netto-from-script.git
cd netto-from-script
```
Insert in `hosts` file the IP addresses of all the hosts. Do not delete the first line.

Run:
```
ansible-playbook -i hosts install_netto.yml -e "pyroscope_server_address=your_pyroscope_server_address"
```
Change `your_pyroscope_server_address` with the IP address of the pyroscope server. Do not insert the port as it is setted to `4040` by default.
### Pyroscope and Grafana
If you want to install Pyroscope and Grafana locally follow this [guide](https://grafana.com/docs/pyroscope/latest/get-started/).
## Remove Netto
To remove Netto run:
```
ansible-playbook -i hosts uninstall_netto.yml
```
Be sure that the file contains the IP addresses of all hosts from which to remove Netto.
