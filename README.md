# Cisco Systems Public MIB Area
Various Public Simple Network Management Protocol (SNMP) management information bases (MIBs) from Cisco Systems.

### Usage Guidelines
The suggested way to retrieve the MIBs applicable to the Cisco products that you wish to manage is as follows:
1. For each product, retrieve the file `supportlists/[product]/supportlist.txt` or `supportlists/[product]/supportlist.html`,
2. Determine which MIBs each product supports from the retrieved file.
3. Consult the `v2/readme` or `v1/readme` file for brief descriptions of the functionality provided by each MIB.
4. Retrieve all MIBs which provide the functionality you are interested in, and are applicable to the Cisco products you wish to support.
5. If you need the SunNet Manager OID files, retrieve those for each MIB from the `oid` directory.
6. If you need the SunNet Manager schema files, retrieve those for each MIB from the `schema` directory

### Directory Structure
- `app_notes` directory with application notes for using the MIBs.
- `archive` directory with MIBs, OIDs, schema for IOS 10.0 and earlier releases.
- `contrib` directory with helpful mib-related scripts/files (see `contrib/README`)
- `IE1000-MIBS` directory with IE1000 MIBs.
- `ME1200-MIBS` directory with ME1200 MIBs.
- `oid` directory with SunNet Manager OID files for the MIBs.
- `schema` directory with SunNet Manager schema files for the MIBs.
- `STRATIX2500-MIBS` directory with STRATIX2500 MIBs.
- `supportlist` directory with directories for each product with information about which MIBs that product supports. 
- `traps` directory with SunNet Manager trap files for the MIBs.
- `ucs-C-Series-mibs` directory with UCS C-Series MIBs.
- `ucs-mibs` directory with other UCS related MIBs.
- `v1` SNMP version 1 MIBs and SNMPv1 conversions of the SNMP version 2 MIBs.
- `v2` SNMP version 2 MIBs.
- `viptela-mibs` directory with Viptela MIBs.

### Other Notes
- This GitHub repository is a 2/28/2022 backup of the public `ftp://ftp.cisco.com/pub/mibs/`
  - Empty folders have not been backed up.
- Some Wireless LAN Controller model MIBs are located on the applicable [software.cisco.com](https://software.cisco.com/download/home) downloads page. 
  - e.g. [3504 Wireless Controller, Release 8.10.162.0 MIBs](https://software.cisco.com/download/home/286312601/type/280775088/release/8.10.162.0)
- All instances of `ftp://ftp.cisco.com/pub/mibs/` have been replaced with `https://raw.githubusercontent.com/cisco/cisco-mibs/main/` within `.html`/`.htm` files.
