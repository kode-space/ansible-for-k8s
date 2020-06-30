<h1 align="center">Welcome to Ansible for Provision K8s Clusters 👋</h1>
<p>
  <a href="#" target="_blank">
    <img alt="License: MIT" src="https://img.shields.io/badge/License-MIT-yellow.svg" />
  </a>
  <a href="https://twitter.com/restuhaqza" target="_blank">
    <img alt="Twitter: restuhaqza" src="https://img.shields.io/twitter/follow/restuhaqza.svg?style=social" />
  </a>
</p>

> Provision Kubernetes Clusters Denagn Menggunakan Ansible

## Requirements
* Ansible
* Two Linux Machine (VPS, VM, Container)

## Sudah dicoba
* Menggunakan Dua Instance dengan AWS Lightsail dengan spesifikasi 2x`2Core+4GB+80GB_SSD`

## Cara Penggunaan
1. Siapkan Minimal 2 Server dengan spesifikasi masing-masing:
```
CPU : 2 Core
RAM : 2 GB
Storage : 20 GB
OS : Ubuntu 18.04
Network : 100 Mbps
```

2. Ubah Konfigurasi di file `hosts` dengan menginputkan IP Public Server pada file hosts replace `master_ip` dengan alamat yang akan digunakan sebagai Node Master dan `worker_ip` dengan alamat yang akan digunakan sebagai Worker Node
3. Melakukan Instalasi Kubernetes Depedencies seperti Docker, Kubeadm, Kubelet dan Kubectl
```
ansible-playbook -i hosts kube-tools.yaml
```
4. Melakukan Inisialisasi Node Master dengan menggunakan Kubeadm
```
ansible-playbook -i hosts master.yaml
```
5. Melakukan Join Clusters dari Worker Node ke Master Node. Worker digunakan untuk host pod container
```
ansible-playbook -i hosts worker.yaml
```

Referensi : 
* [How To Create a Kubernetes Cluster Using Kubeadm on Ubuntu 18.04]('https://www.digitalocean.com/community/tutorials/how-to-create-a-kubernetes-cluster-using-kubeadm-on-ubuntu-18-04')




## Author

👤 **Restu Muzakir**

* Website: https://restuhaqza.dev
* Twitter: [@restuhaqza](https://twitter.com/restuhaqza)
* Github: [@restuhaqza](https://github.com/restuhaqza)
* LinkedIn: [@restuhaqza](https://linkedin.com/in/restuhaqza)

## Show your support

Give a ⭐️ if this project helped you!

***
_This README was generated with ❤️ by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_
