# vim: ft=automake

include $(top_srcdir)/mk/confdc.mk

snmpmibdir = $(sysconfdir)/confd/snmp
snmpbindir = $(sysconfdir)/confd/snmp

MIBS := \
	VIPTELA-APP-ROUTE.mib \
	VIPTELA-BFD.mib \
	VIPTELA-BRIDGE.mib \
	VIPTELA-HARDWARE.mib \
	VIPTELA-OMP.mib \
	VIPTELA-OPER-BGP.mib \
	VIPTELA-OPER-MULTICAST.mib \
	VIPTELA-OPER-OSPF.mib \
	VIPTELA-OPER-SYSTEM.mib \
	VIPTELA-OPER-VPN.mib \
	VIPTELA-POLICY.mib \
	VIPTELA-SECURITY.mib \
	VIPTELA-SNMP-USM.mib \
	VIPTELA-TRAPS.mib \
	VIPTELA-WLAN.mib \
	VIPTELA-WWAN.mib \
	VIPTELA-DOT1X.mib

AUTOGEN_MIBS := \
	VIPTELA-DEVICES.mib \
	VIPTELA-MODELS.mib

snmpmib_DATA = \
	VIPTELA-GLOBAL.mib \
	$(AUTOGEN_MIBS) \
	$(MIBS)

BINS = $(MIBS:.mib=.bin) $(AUTOGEN_MIBS:.mib=.bin)

IF-MIB.bin: IANAifType-MIB.bin
VIPTELA-MODELS.bin: VIPTELA-GLOBAL.bin
VIPTELA-DEVICES.bin: VIPTELA-HARDWARE.bin
$(BINS): VIPTELA-GLOBAL.bin VIPTELA-MODELS.bin

snmpbin_DATA = \
	IF-MIB.bin \
	IANAifType-MIB.bin \
	VIPTELA-GLOBAL.bin \
	$(BINS)


IF-MIB.bin: IF-MIB.mib $(builddir)/../yang/IF-MIB.fxs
	$(AM_V_CONFDC)$(CONFDC) --read-only -c  \
	        -o IF-MIB.bin                   \
		-f $(CONFD_DIR)/etc/confd       \
		-f $(CONFD_DIR)/etc/confd/snmp  \
		-f $(builddir)/../yang/         \
		-- $< $(builddir)/../yang/IF-MIB.fxs


IANAifType-MIB.bin: IANAifType-MIB.mib $(builddir)/../yang/IANAifType-MIB.fxs
	$(AM_V_CONFDC)$(CONFDC) --read-only -c  \
	        -o IANAifType-MIB.bin           \
		-f $(CONFD_DIR)/etc/confd       \
		-f $(CONFD_DIR)/etc/confd/snmp  \
		-f $(builddir)/../yang/         \
		-- $< $(builddir)/../yang/IANAifType-MIB.fxs

SUFFIXES = .mib .bin
CLEANFILES = $(snmpbin_DATA)
