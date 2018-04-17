# Openldap-schema role for Ansible

Idempotently load a schema to OpenLDAP server.

This role will ensure an LDIF-formatted schema exists on OpenLDAP server: either from a string
variable, or from a file on the remote host. It will detect schema CN from LDIF contents. LDIF line
wrapping is fully supported.

## Role Variables

Either `ols_schema` or `ols_ldif` variable is required.

### `ols_schema`

If `ols_schema` is *set*, then it should contain the schema LDIF. This string will be fed to
`ldapadd(1)` standard input.

LDIF line wrapping using a leading space is cumbersome to store in a YAML playbook, so you might
want to read it dynamically using a lookup.

### `ols_ldif`

If `ols_schema` is *not set*, then `ols_ldif` specifies the file name on the remote host. This file
will be loaded to LDAP using `ldapadd(1)` command.

## Example Playbook

# License

GPLv3 or later

# Author Information

2018, Development Gateway
