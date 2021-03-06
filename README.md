[![GitHub license](https://img.shields.io/github/license/PDOK/k8s_role)](https://github.com/PDOK/k8s_role/blob/main/LICENSE)
[![GitHub release](https://img.shields.io/github/release/PDOK/k8s_role.svg)](https://github.com/PDOK/k8s_role/releases)

# k8s_role

This role validates, applies and deletes objects to a kubernetes cluster.
This role is developed for use in pdok operators.

## Requirements

This role uses the k8s module.
This requires: 
- openshift >= 0.8.0
- kubernetes-validate python module

## Role Variables

objects: a list of kubernetes objects and which state they should be in.
If no state is specified, it is defaulted to present.

## Example Playbook

    - hosts: servers
      include_role:
        name: k8s_role
      vars:
        objects:
          - object: "{{ deployment }}"
          - object: "{{ server }}"
            state: absent
