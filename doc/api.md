SmartSNMP API
=============

Generally, if you want to embed **SmartSNMP** to your application, then you need use SmartSNMP as a lua library instead of using `bin/snmpd`. 

Actually, `bin/snmpd` is the best example for you.

Use SmartSNMP as a lua library
------------------------------

First, you need to import SmartSNMP library like this.

    local smartsnmp = require "smartsnmp"

And now, SmartSNMP provide following API.

- `smartsnmp.init(port)` : initialize snmp agent with port number.
- `smartsnmp.set_ro_community(ro_community_string)` : set read only community.
- `smartsnmp.set_rw_community(rw_community_string)` : set read/write community.
- `smartsnmp.register_mib_group(mib_oid, mib_group, name)
  - `oid` :(table): oid you want to register, eg: `{1,3,6,1,2,1,1}`
  - `mib_group` :(generated by SmartSNMP group generator): see `doc/how-to-write-mib-group.md` for more detail.
  - `name` :(string): mib group name for this mib
- `smartsnmp.start() : start to run snmp agent.
