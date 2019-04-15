# Quantum Mobile

*Quantum Mobile* is a Virtual Machine for computational materials science.

## Note on this version
This is historical branch, stripped down from the main Quantum Mobile (e.g. with Quantum ESPRESSO only, installed from
the APT Ubuntu packages, and no other codes; fewer pseudopotential libraries; ...).

The main purpose is to recreate an environment where older versions work. In this case, AiiDA 0.9.1 (to 
address issue aiidateam/aiida_core#2426, and PR aiidateam/aiida_core#2478).

## Content

It comes with a collection of software packages for quantum
mechanical calculations, including

 * [Quantum ESPRESSO](http://www.quantum-espresso.org/)
 * [Yambo](http://www.yambo-code.org/)
 * [fleur](http://www.flapw.de/)
 * [Siesta](https://launchpad.net/siesta)
 * [CP2K](https://www.cp2k.org)

all of which are set up and ready to be used through the
[AiiDA](http://www.aiida.net) python framework for automated workflows and
provenance tracking.

## Download the VM

Please see [releases](https://github.com/marvel-nccr/quantum-mobile/releases) for the latest VM image and installation instructions.

## Build it from scratch

You would like to add/remove some components of the VM
and produce your own modified VM image?
Then, the first step is to familiarize yourself with how the VM is set up.

This git repository contains all the vagrant and ansible scripts 
required to set up the VM from scratch.

### Prerequisites

- [vagrant](https://www.vagrantup.com/downloads.html) >= 2.0.1
- [virtualbox](https://www.virtualbox.org/wiki/Downloads)
- [python](https://www.python.org/)
- Host OS: So far tested only on unix systems (MacOS, Ubuntu). Might work under Windows with a few modifications.

### Create Virtual Machine

```
git checkout git@github.com:marvel-nccr/quantum-mobile.git
cd quantum-mobile
pip install -r requirements.txt
vagrant plugin install vagrant-vbguest  # optional, improves interface
vagrant up  # build vm from scratch (takes some tens of minutes)
```

### Create image
```
# optional: reduce size of VM
ansible-playbook playbook.yml --extra-vars "clean=true"
bash create_image.sh
```

### Useful commands

 * `vagrant provision --provision-with ansible`: re-run ansible scripts
 * `vagrant reload`: restart machine
 * `vagrant halt`: stop machine
 * ```
   ./setup-ansible.sh             # inform ansible about ssh config
   ansible-playbook playbook.yml  # run ansible directly, add tags, ...
   ```
 * ```ssh -F vagrant-ssh default```
 * ```scp -F vagrant-ssh default:/path/on/vm  my/path```

## Publishing customized VMs

If you would like to publish a customized version of Quantum Mobile, we recommend that you

 1. Fork this repository
 1. Give your VM a different name to avoid confusion
 1. Adapt `globalconfig.yml`, `EULA.txt` and `README.md` appropriately
 1. Pull the latest changes from time to time to keep things up to date

Last, but not least, [let us know](mailto:leopold.talirz@gmail.com)!

## Acknowledgements

This work is supported by the [MARVEL National Centre for Competency in
Research](http://nccr-marvel.ch) and the [MaX European centre of
excellence](http://www.max-centre.eu/)
