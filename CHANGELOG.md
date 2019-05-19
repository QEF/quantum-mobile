# Changelog

## Quantum Mobile v19.XX.0

### Improvements
* now installing fixed versions of ansible roles for improved reproducibility
  and tracking of changes between Quantum Mobile releases

### Software updates
* roles:
  * marvel-nccr.add_user v0.2.1
  * marvel-nccr.simulationbase v0.1.1

### Build process
 * Virtualbox v6.0.8

## Quantum Mobile v19.03.0

### Improvements
* add link to FAQ on desktop
* switch from torque to slurm scheduler

### Software updates
* Ubuntu 18.04 LTS
* Quantum Espresso v6.3
* cp2k v6.1
* yambo v4.3.2
* fleur 0.27 MaXR3
* siesta v4.0.2
* aiida-core v0.12.3
* aiidalab v19.03.0

### Build process
* ansible 2.7.5
* Vagrant v2.2.4
  * vbguest v0.17.1
  * bento/ubuntu-18.04 v201812.27.0
* Virtualbox v6.0.4


## Quantum Mobile v18.06.0

### Software updates
* aiida-core v0.12.0
* aiida-quantumespresso v2.0.1

### Improvements

- Add /scratch directory
- Using shared folders no longer requires sudo

### Build process

- Separate roles into independent repositories
- Roles are installed via ansible-galaxy
- Continuous integration tests for individual roles 

## Quantum Mobile v18.04.0

### Software updates
* aiida-core v0.11.4
* aiida-quantumespresso v2.0.0
* aiida-cp2k v0.9.0
* aiida-yambo v0.2.5

### Improvements

- Switch to Chromium browser as Firefox struggles with WebGL
- Add cp2k data directory
- AiiDA Daemon is now a system service - no need to start it or shut it down
- Import SSSP from AiiDA export files hosted on the Materials Cloud Archive

### Build process

- Add variables that can be used to turn on/off features for
  increased flexibility (e.g. to install Quantum Mobile as a
  server):

     * 'headless': if true, avoids GUI-related setup
     * 'release_notes': if false, does not add release notes
- Running the ansible roles on a different host is now as easy as
  `ansible-playbook playbook.yml -i inventory_file`
- Adjustments for ansible 2.5

## Quantum Mobile v18.03.0

### Improvements

- Add Wannier90 v2.1 + aiida-wannier90 v1.0.0

### Build process

- VM image built using Virtualbox 5.2.8

## Quantum Mobile v18.02.2

### Software updates
* aiida-core v0.11.0
* aiida-siesta v0.11.5

## Quantum Mobile v18.02.0

### Improvements

- Add jupyter apps (just like on [aiidalab.materialslcoud.org](aiidalab.materialscloud.org))

### Software updates
* aiida-yambo v0.2.4
* aiida-siesta v0.9.8
* QE 6.2.1
* SSSP (PBE) accuracy 1.0
* SSSP (PBE) efficiency 1.0

## Build process

- VM image built using Virtualbox 5.2.6 + Guest Additions 5.2.7


## Quantum Mobile v17.12.0

### Improvements

- Add Quantum Mobile Logo
- Add AiiDA Demos

### Software updates

- yambo 4.2.1
- fleur 0.27 MaXR2.1
- aiida 0.10.1
- aiida-cp2k 0.7

### Build process

- VM image built using Virtualbox 5.2.4
- Size of VM image and virtual disk added to install instructions

## Quantum Mobile v17.11.0

### Initial release

- Operating System: Ubuntu 16.04.3 LTS
- Tools:
  - torque server
  - openmpi libraries
  - xmgrace, gnuplot, xcrysden, jmol
- Quantum Espresso v6.2
- Yambo v4.2.0
- fleur v0.27 MaXR2
- siesta v4.0.1
- cp2k v5.1
- aiida v0.10.0
  - aiida-fleur v0.6.0
  - aiida-quantumespresso v1.0.1
  - aiida-siesta v0.9.7.1
  - aiida-cp2k v0.2.2
- pseudopotentials: 
  - sssp-pbe-accuracy v0.7
  - sg15-oncv-1.1
