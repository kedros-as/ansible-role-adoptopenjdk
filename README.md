Role Name
=========

Install AdoptOpenJDK on Linux. 

Requirements
------------

None.

Role Variables
--------------

JDK/JREs to install are specified as a list in the following variable.

	adoptopenjdk: 			# Main variable holding a list of JDK/JREs to install
	    - name: jre11		# A symlink with this name will be created.
	      version: 11		# Version of JDK/JRE to install (8, 10, 11, ...)
	      implementation: hotspot	# hotspot, openj9
	      arch: x64			# x64, x32, ppc64, s390x, ppc64le, aarch64
	      release: latest		# latest, jdk8u172-b00-201807161800
	      type: jre			# jdk, jre


Any option other than name can be ommited and the following defaults will be applied (you can override them).

	default_version: 11
	default_implementation: hotspot
	default_arch: x64
	default_release: latest
	default_type: jre


JDK/JREs will be installed in the following directory.

	base_path: /opt/adoptopenjdk


Dependencies
------------

None.

Example Playbook
----------------

- hosts: servers
  roles:
      - role: adoptopenjdk
        vars:
            adoptopenjdk:
                - name: jdk11
                  version: 11
                  release: latest
                  type: jdk
		- name: jre10
		  version: 10

License
-------

BSD

Author Information
------------------

Juraj Hrubša
Kedros, a.s.
https://www.kedros.sk/
