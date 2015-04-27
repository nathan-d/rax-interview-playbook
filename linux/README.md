# Ansible Linux Build Scripts
A simple Ansible playbook to build and configure a Linux cloud server for DSE interviews.

Provisions a 4Gb Performance server running Ubuntu with supporting development packages and environments.

Shared LXDE remote desktop sessions are handled via x2go. On initial build the first x2go session will need to be started as an LXDE session. Subsequent connections for shadow or shared sessions can be set to use the 'Local desktop connection' setting.

## Editors
All editors are installed with standard language support and debug packages.

* vi
* vim
* emacs
* Sublime text 3

## Languages & SDKs
The following languages and SDKs are installed to allow candidates to debug assessment code.

* Python
    * ipython
    * Pyrax SDK
* Ruby
    * pry
    * Fog SDK


## Usage
The ansible playbook can be run with a specific variable set to build with specific interview content.

To perform a generic build without interview content run the following:

    ansible-playbook -i inventory main.yml -u root

### Building for interviews
Individual interview stages can be passed as Ansible command line params.

To build for a specific stage set the stage value as an extra vars option.
    ansible-playbook -i inventory main.yml -u root --extra-vars "server_name=interview-env stage=4"
