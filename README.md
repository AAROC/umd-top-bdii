Unified Middleware Distribution Top-BDII role (standalone)
=========

This role is to deploy a top-bdii, outside of a container. It uses other roles of the @AAROC/DevOps repository. This playbook deploys the Top-BDII service of a gridcloud and configures it with site-specific variables necessary for service discovery in a region. There are a few performance tweaks which have been shown to improve reliability.

Requirements
------------

The role requires the application of _at least_ the `certificates`  and `umd` roles

Role Variables
--------------

This role requires several variables which are set in `defaults` and `vars`

  * `needs_certificate`: (default value: `false`) - whether this service needs a host certificate.
  * `relay_db_lines`:  These are the lines that we have by default in the slapd config. The standard configuration that comes with slapd installation usually causes segfaults on general usage. These lines are to be overwritten with `relay_db_fix`.
  * `relay_db_fix`: the lines that fix the segfault.
  * `glue_1_3_lines`: The Glue 1.3 db configuration lines used as regexp to fix db config
  * `glue_1_3_fix`: The lines that properly configure the db

Dependencies
------------

None in galaxy.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: top-bdiis
      roles:
         - { role: AAROC.umd-top-bdii }

License
-------

Apache-2.0

Author Information
------------------

Bruce Becker (brucellino@gmail.com) | C.S.I.R. Meraka Institute.
