Format: Log Type - Time(microsec) - Message - Optional Info
Log Type: B - Since Boot(Power On Reset),  D - Delta,  S - Statistic
S - QC_IMAGE_VERSION_STRING=BOOT.MXF.1.1-00666-MAKENA-1.56015.10
S - IMAGE_VARIANT_STRING=SocMakenaAU
S - OEM_IMAGE_VERSION_STRING=my26-idcu-aosp-ssd-8sl8s
S - Boot Interface: UFS
S - Secure Boot: Off
S - Boot Config @ 0x00786064 = 0x00000041
S - JTAG ID @ 0x00786130 = 0x1014b0e1
S - OEM ID @ 0x00786138 = 0x00000000
S - Serial Number @ 0x00786134 = 0x63585f7d
S - OEM Config Row 0 @ 0x007841c8 = 0x0000000000000000
S - OEM Config Row 1 @ 0x007841d0 = 0x0000000000000001
S - Feature Config Row 0 @ 0x00784148 = 0x0000000000000000
S - Feature Config Row 1 @ 0x00784150 = 0x0000000000000000
S - Core 0 Frequency, 1440 MHz
S - PBL Patch Ver: 0
D -      6020 - pbl_apps_init_timestamp
D -     60165 - bootable_media_detect_timestamp
D -      1923 - bl_elf_metadata_loading_timestamp
D -       566 - bl_hash_seg_auth_timestamp
D -     13871 - bl_elf_loadable_segment_loading_timestamp
D -      3971 - bl_elf_segs_hash_verify_timestamp
D -     16832 - bl_sec_hash_seg_auth_timestamp
D -       739 - bl_sec_segs_hash_verify_timestamp
D -        13 - pbl_populate_shared_data_and_exit_timestamp
S -    104100 - PBL, End
B -    120109 - SBL1, Start
B -    256413 - SBL1 BUILD @ 11:14:26 on Jan 13 2026
B -    261080 - usb: usb2phy: PRIM success , 0x4
B -    264160 - usb: eud_serial_upd , 0x63585f7d
B -    268827 - smss_load_cancel
B -    273463 - blocked the DDR access
B -    277672 - TCSR_SAFE_ISBPR    [0x0]
B -    280386 - SMSS_TCSR_SPARE1_REG0 [0xff]
B -    284290 - Skip the bist execution completely
B -    288743 - SMSS CSM DCMM zero init
B -    304908 - SMSS Load [TRUE]
B -    305152 - UFS Boot LUN: 1
B -    376705 - UFS INQUIRY ID: FORESEE C8H094          0011
B -    399916 - BOOT_LUN_1
B -    399916 - Recovery: boot_recovery_is_boot_partition_valid
B -    408608 - Recovery: partition magic not set
B -    408608 - Recovery: Info missing
B -    413366 - SMSS -  Image Load, Start
B -    425048 - XBL Config -  Image Load, Start
B -    425078 - SHRM -  Image Load, Start
B -    434808 - CDT -  Image Load, Start
B -    434808 - CDT Version:3,Platform ID:5,Major ID:1,Minor ID:0,Subtype:0
B -    457896 - PMIC A:3.0 C:3.0 E:3.0 G:3.0
B -    497058 - PM: PSI: b0x0f_v0x05
B -    500566 - PM: Device Init # SPMI Transn: 2351
B -    500596 - pm_driver_init, Start
B -    518134 - PM: Driver Init # SPMI Transn: 860
B -    518134 - P3 Q6 bist , Start
B -    522800 - SMSS_TCSR_SPARE1_REG0 [0xc80000ff]
B -    526003 - SMSS_TCSR_SPARE1_REG0 [0xc80000ff]
B -    530669 - vsense_init, Start
B -    535305 - cpr_init, Start
B -    542808 - Pre_DDR_clock_init, Start
B -    543083 - sbl1_ddr_init, Start
B -    546743 - 8 channel DDR configuration
B -    574681 - DSF version = 265.0.87
B -    574711 - Manufacturer ID = ff, Device Type = 7
B -    578280 - Rank 0 size = 12288 MB, Rank 1 size = 12288 MB
B -    583434 - do_ddr_training, Start
B -    590297 - DDR: Start of DDR Training Restore
B -    604815 - Frequency = 1555 MHz
B -    604845 - Max enabled DDR Freq = 2092 MHz
B -    608231 - DDR: End of DDR Training Restore
B -    612653 - safe_ivi_fuse:0
B -    617808 - checksum write to safety dram
B -    620126 - Pimem init cmd, entry
B -    634278 - External heap init, Start
B -    634308 - External heap init, End
B -    643489 - DDR -  Image Load, Start
B -    643580 - usb: UFS Serial - b5783d8a
B -    647271 - APDP -  Image Load, Start
B -    651297 - RamDump -  Image Load, Start
B -    655902 - ECC DISABLED
B -    659166 - Recovery: boot_smem_store_recovery_info
B -    662063 - CFE -  Data loaded
B -    666943 - OEM_MISC -  Image Load, Start
B -    671213 - QTI_MISC -  Image Load, Start
B -    674355 - SMSS_TCSR_SPARE1_REG0 [0xc80000ff]
B -    678564 - SMSS_TCSR_SPARE1_REG0 [0xc80000ff]
B -    688507 - PM: PM Total Mem Allocated: 4292
B -    688507 - AOP -  Image Load, Start
B -    698389 - QSEE Dev Config -  Image Load, Start
B -    699975 - QSEE -  Image Load, Start
B -    761585 - Soft SKU Data loaded
B -    761585 - SEC -  Image Load, Start
B -    765031 - CPUCPFW -  Image Load, Start
B -    807182 - QHEE -  Image Load, Start
B -    936289 - APPSBL -  Image Load, Start
S - Flash Throughput, 729197 KB/s  (40105843 Bytes,  55512 us)
S - DDR Frequency, 2092 MHz
B -    953430 - SBL1, End

No matched DTBO
swdl_lun_init:837 System banked to "A"
WARN: RTC initialization failed, err=7
CRM: QXA.QA.6.0.c4-00159-GEN4.HYP-1.56015.39 (Built 2025/03/28-09:01:48-UTC)
WriteProtect not Enabled , wp_enable = 0
Syspage Validation Succeeded, err:0
EL2 save/restore init
Exiting bootstrap executable el2-save-restore
QNX Host running
isfbl = 0
# [tid=2]loader_thread_main:1942 WriteProtect Status = 0
normal mode...
SA8295P_v2.1_ft0_sb1_skuBBBB_ADP_ROX_v1.0.0_UFS_NORMAL
fuse_launcher: Daemon name:passthrough
fuse_launcher: Got a message, rcvid is 1A0001 attach_point:nto_name=syslog_f_nsrv host_path:source=/syslog
fuse_launcher: pid of launched "passthrough" process is 462906.
fuse_launcher: Got a message, rcvid is 1B0001 attach_point:nto_name=update_f_nsrv host_path:source=/update
fuse_launcher: pid of launched "passthrough" process is 462907.
fuse_launcher: Got a message, rcvid is 1C0001 attach_point:nto_name=nfs_share_f_nsrv host_path:source=/nfs_share
fuse_launcher: pid of launched "passthrough" process is 462908.
fuse: Waiting for Neutrino messages at device name "syslog_f_nsrv"
fuse: Waiting for Neutrino messages at device name "update_f_nsrv"
fuse: Waiting for Neutrino messages at device name "nfs_share_f_nsrv"
[linux-la-mem.config:2] vinput: window position has been updated to: [0,0]
Successfully set the FDE key for /dev/disk/userdata
network_aptiv start
network_aptiv_adapter start vp0/vp1/emac1
passed in uClientIdx=5
passed in uClientIdx=6
passed in uClientIdx=7
passed in uClientIdx=8
if_up emac0
ifconfig emac0 up
ifconfig emac0 funcs
config vp0
config vp1
network_aptiv_adpater end
network_aptiv_tune start
network_aptiv_tune end
network_aptiv_vlan_bridge start
network_aptiv_vlanrox  emac0
network_aptiv_vlanrox end
network_static_ARP_Add
network_aptiv_vlan_bridge end
network_aptiv end
Set GPIO 26 function to 0 [0]
Set GPIO 26 direction to Out [1]
Set GPIO 26 pull to Pull down [1]
Wrote GPIO 26 to 0
Set GPIO 23 function to 0 [0]
Set GPIO 23 direction to Out [1]
Set GPIO 23 pull to Pull down [1]
Wrote GPIO 23 to 0
flashctl end ...
ADD : ftp proto=tcp, wait.max=0.40, user:group=root: builtin=0 server=/mnt/usr/sbin/ftpd policy=
registered /mnt/usr/sbin/ftpd on 5
ADD : ftp proto=tcp6, wait.max=0.40, user:group=root: builtin=0 server=/mnt/usr/sbin/ftpd policy=
registered /mnt/usr/sbin/ftpd on 6
ADD : shell proto=tcp, wait.max=0.40, user:group=root: builtin=0 server=/mnt/usr/sbin/rshd policy=
registered /mnt/usr/sbin/rshd on 7
ADD : ssh proto=tcp, wait.max=0.40, user:group=root: builtin=0 server=/mnt/usr/sbin/sshd policy=
registered /mnt/usr/sbin/sshd on 8

Loading deva-ctrl-qc version 2.0.0 on [Aug 26 2025]...
pps: NOTICE: PPS initializing
CryptoKitCA enter
Start app: enter
pps: WARNING: /mnt/etc/pps_acl.conf:29:slog2: ACL supercedes mode (was 0600 now 0771)
pps: NOTICE: PPS attaching /tmp/pps
pps: NOTICE: PPS attached /tmp/pps major 2 minor 17
value CarConfig741 is 0
set maxtry 200, interval 1000
slay: ifs/bin/dumper 49165 on (tty not known)
Analyzer not enabled. touch /etc/enable_analyzer and reset device to enable Analyzer debugging
    [ Ana_Info [Analyzer] starting on tool_policy_manager ]
Setting dump mode to mini_rawdump as /etc/enable_mini_rawdump is enabled
Enabling gcc_pcie_4_gdsc... Done!
Enabling gcc_pcie_2a_gdsc... Done!
Warning: Can not create file /etc/mntsubtab.localhost.1396956331
         Exports with -alldirs option may not work normally.
rpcbind debugging enabled.
Found ROX_v1.0.0
Found SA8295.
Starting the gpufrequnecy collection
Not found APTIVEMC_v1.0.0
Not found APTIVTB_v1.0.0
Enter Test
Invalid register address &
GPU Max Frequnecy = 757000000
01-01 00:00:03.201     5 I QProfilerInterface: Initializing (v2022.1, built Sep  9 2022@20:41:16)...
01-01 00:00:03.202     5 I GLESCollector.ShimConnection: Starting the process connection thread...
Found 000
Not found 001
ROX - sysinfo 000
BHW Type is HWB_ROX_IDCU
======>Add default route cmd: route add default 172.16.3.5
add net default: gateway 172.16.3.5
01-01 00:00:03.268     5 E GPUUtils: Could not read maximum GPU clock (3)
01-01 00:00:03.203     5 I Queried device ID: Adreno (TM) 690
01-01 00:00:03.203     5 I Queried device ID: Adreno (TM) 690
01-01 00:00:03.203     5 I Queried device ID: Adreno (TM) 690
01-01 00:00:03.203     5 I Queried device ID: Adreno (TM) 690
01-01 00:00:03.315     5 E QProfilerInterface: Number of drawcall metrics = 57
Num available metrics = 60
/tmp/skucli.txt: No such file or directory
Checking softsku_daemon running status........
Softsku_daemon running, check for initialization status.
Checking softsku_daemon initialization status........
Softsku_daemon initialized, going ahead with command.
Entered the gpu_mon constructor
dsp_mon constructor : cdsp profiler.
OemID = 0x0 blown on device
======>2220 Sec Log-Eth:p1emac0 link down and tx-hsip<======
Startup done
Entered the constructor
[setLogLevel 178] lev=0
[DIAG_DEBUG] DiagApp id:71, max:3
[DIAG_INFO]  DiagApp: DiagTaskComm initialized for IPC-to-queue bridging
[DIAG_DEBUG] DidManager: Constructor called
[DIAG_INFO]  DidManager: Initializing DID manager
[DIAG_INFO]  DidManager: Registering built-in DID implementations
[DIAG_DEBUG] DidF103: Initialized DID 0xF103
[DIAG_INFO]  DidManager: Registered DID 0xF103 (Equipment Maintenance Fingerprint Information)
[DIAG_DEBUG] DidF187: Initialized DID 0xF187
[DIAG_INFO]  DidManager: Registered DID 0xF187 (Vehicle Manufacturer Spare Part Number)
[DIAG_DEBUG] DidF18A: Initialized DID 0xF18A
[DIAG_INFO]  DidManager: Registered DID 0xF18A (System Supplier Identifier)
[DIAG_DEBUG] DidF197: Initialized DID 0xF197
[DIAG_INFO]  DidManager: Registered DID 0xF197 (ECU System Name)
[DIAG_DEBUG] DidF193: Initialized DID 0xF193
[DIAG_INFO]  DidManager: Registered DID 0xF193 (ECU Hardware Version Number)
[DIAG_DEBUG] DidF195: Initialized DID 0xF195
[DIAG_INFO]  DidManager: Registered DID 0xF195 (ECU Software Version Number)
[DIAG_DEBUG] DidF18C: Initialized DID 0xF18C
[DIAG_INFO]  DidManager: Registered DID 0xF18C (ECU Serial Number)
[DIAG_DEBUG] DidF190: Initialized DID 0xF190
[DIAG_INFO]  DidManager: Registered DID 0xF190 (Vehicle Identification Number (VIN))
[DIAG_DEBUG] DidF188: Initialized DID 0xF188
[DIAG_INFO]  DidManager: Registered DID 0xF188 (Software Number)
[DIAG_DEBUG] DidF191: Initialized DID 0xF191
[DIAG_INFO]  DidManager: Registered DID 0xF191 (Hardware Number)
[DIAG_DEBUG] DidF18B: Initialized DID 0xF18B
[DIAG_INFO]  DidManager: Registered DID 0xF18B (ECU Manufacture Date)
[DIAG_DEBUG] DidF15A: Initialized DID 0xF15A
[DIAG_INFO]  DidManager: Registered DID 0xF15A (Fingerprint Information)
[DIAG_DEBUG] DidF101: Initialized DID 0xF101
[DIAG_INFO]  DidManager: Registered DID 0xF101 (Vehicle Configuration)
[DIAG_DEBUG] DidF102: Initialized DID 0xF102
[DIAG_INFO]  DidManager: Registered DID 0xF102 (IDCU Configuration)
[DIAG_DEBUG] DidF110: Initialized DID 0xF110
[DIAG_INFO]  DidManager: Registered DID 0xF110 (IDCU VID)
[DIAG_DEBUG] DidF12A: Initialized DID 0xF12A
[DIAG_INFO]  DidManager: Registered DID 0xF12A (DBC Version)
[DIAG_DEBUG] DidF12B: Initialized DID 0xF12B
[DIAG_INFO]  DidManager: Registered DID 0xF12B (DDS Version)
[DIAG_DEBUG] DidF186: Initialized DID 0xF186
[DIAG_INFO]  DidManager: Registered DID 0xF186 (Active Diagnostic Session)
[DIAG_DEBUG] DidF1F1: Initialized DID 0xF1F1
[DIAG_INFO]  DidManager: Registered DID 0xF1F1 (MPU1 Software Version Number)
[DIAG_DEBUG] DidF1FA: Initialized DID 0xF1FA
[DIAG_INFO]  DidManager: Registered DID 0xF1FA (MCU1 Software Version Number)
[DIAG_DEBUG] DidA621: Initialized DID 0xA621
[DIAG_INFO]  DidManager: Registered DID 0xA621 (Ethernet Port Number)
[DIAG_DEBUG] DidA622: Initialized DID 0xA622
[DIAG_INFO]  DidManager: Registered DID 0xA622 (Ethernet Signal Quality)
[DIAG_DEBUG] DidA624: Initialized DID 0xA624
[DIAG_INFO]  DidManager: Registered DID 0xA624 (MAC Address)
[DIAG_DEBUG] DidDF01: Initialized DID 0xDF01
[DIAG_INFO]  DidManager: Registered DID 0xDF01 (HASH of the updated version in the target path)
[DIAG_DEBUG] DidD43D: Initialized DID 0xD43D
[DIAG_INFO]  DidManager: Registered DID 0xD43D (IDCU Communication Secret Request Status)
[DIAG_DEBUG] DidD43E: Initialized DID 0xD43E
[DIAG_INFO]  DidManager: Registered DID 0xD43E (A2B Status)
[DIAG_DEBUG] DidD001: Initialized DID 0xD001
[DIAG_INFO]  DidManager: Registered DID 0xD001 (ODO (Odometer))
[DIAG_DEBUG] DidD0D3: Initialized DID 0xD0D3
[DIAG_INFO]  DidManager: Registered DID 0xD0D3 (ECU Backup Status)
[DIAG_DEBUG] DidD100: Initialized DID 0xD100
[setloginfo, 89] path=/update/doipserver.log, isprintout=0
INITIALIZES slog BEFORE THE main() FUNCTION EXECUTION
2024-01-01 00:00:03:868  1871980      1  I  [main.cpp][main:81]:┌───────────────────────────────────────────────────────────────┐
[DIAG_INFO]  DidManager: Registered DID 0xD100 (SWB LIN Status)
[run 186] log thread start que.size=0...
[DIAG_DEBUG] DidF1A0: Initialized DID 0xF1A0
[DIAG_INFO]  DidManager: Registered DID 0xF1A0 (ECU Backup Software Version Number)
[DIAG_DEBUG] DidF1A1: Initialized DID 0xF1A1
[DIAG_INFO]  DidManager: Registered DID 0xF1A1 (ECU Backup Software Number)
[DIAG_DEBUG] DidF180: Initialized DID 0xF180
[DIAG_INFO]  DidManager: Registered DID 0xF180 (Bootloader Version Number)
[DIAG_DEBUG] DidF111: Initialized DID 0xF111
[DIAG_INFO]  DidManager: Registered DID 0xF111 (VDC WIFI SSID)
[DIAG_DEBUG] DidF112: Initialized DID 0xF112
2024-01-01 00:00:04:053  1871980      1  I  [main.cpp][main:82]:│                    UpdateEngine is running                    │
[DIAG_INFO]  DidManager: Registered DID 0xF112 (VDC WIFI Password)
[DIAG_DEBUG] DidF113: Initialized DID 0xF113
[DIAG_INFO]  DidManager: Registered DID 0xF113 (VDC WIFI AP MAC Whitelist)
[DIAG_DEBUG] DidF114: Initialized DID 0xF114
[DIAG_INFO]  DidManager: Registered DID 0xF114 (VDC SSID_Password_MAC Write State)
[DIAG_DEBUG] DidF1FE: Initialized DID 0xF1FE
[DIAG_INFO]  DidManager: Registered DID 0xF1FE (Level FBL security Constants)
[DIAG_DEBUG] DidF1FF: Initialized DID 0xF1FF
2024-01-01 00:00:04:055  1871980      1  I  [main.cpp][main:83]:└───────────────────────────────────────────────────────────────┘
[DIAG_INFO]  DidManager: Registered DID 0xF1FF (State of the security constant written)
[DIAG_INFO]  DidManager: Built-in DID registration completed
[DIAG_INFO]  DidManager: Initialization completed, 38 DIDs registered
[DIAG_INFO]  DidManager: Registered DIDs (38 total):
[DIAG_INFO]    DID 0xA621: Ethernet Port Number (1 bytes, R)
[DIAG_INFO]    DID 0xA622: Ethernet Signal Quality (1 bytes, R)
[DIAG_INFO]    DID 0xA624: MAC Address (6 bytes, R)
[DIAG_INFO]    DID 0xD001: ODO (Odometer) (3 bytes, R/W)
[DIAG_INFO]    DID 0xD0D3: ECU Backup Status (1 bytes, R)
[DIAG_INFO]    DID 0xD100: SWB LIN Status (2 bytes, R)
[DIAG_INFO]    DID 0xD43D: IDCU Communication Secret Request Status (1 bytes, R)
2024-01-01 00:00:04:056  1871980      1  D  [main.cpp][handle_args:75]:########################### normal mode ###########################
[DIAG_INFO]    DID 0xD43E: A2B Status (1 bytes, R)
[DIAG_INFO]    DID 0xDF01: HASH of the updated version in the target path (32 bytes, R/W)
[ROX] 创建P2P句柄...
2024-01-01 00:00:04:057  1871980      1  D  [DoipComm.cpp][DoipComm:106]:enter
my_slog_handle is null 2
========== init slog before main() =============
INITIALIZES slog BEFORE THE main() FUNCTION EXECUTION
INITIALIZES slog BEFORE THE main() FUNCTION EXECUTION
[DIAG_INFO]    DID 0xF101: Vehicle Configuration (32 bytes, R/W)
[DIAG_INFO]    DID 0xF102: IDCU Configuration (16 bytes, R/W)
[DIAG_INFO]    DID 0xF103: Equipment Maintenance Fingerprint Information (9 bytes, R/W)
[DIAG_INFO]    DID 0xF110: IDCU VID (17 bytes, R/W)
[DIAG_INFO]    DID 0xF111: VDC WIFI SSID (32 bytes, R/W)
[DIAG_INFO]    DID 0xF112: VDC WIFI Password (64 bytes, R/W)
[DIAG_INFO]    DID 0xF113: VDC WIFI AP MAC Whitelist (335 bytes, R/W)
[DIAG_INFO]    DID 0xF114: VDC SSID_Password_MAC Write State (1 bytes, R/W)
2024-01-01 00:00:04:333  1871980      1  I  [FullInstaller.cpp][FullInstaller:23]:enter
[DIAG_INFO]    DID 0xF12A: DBC Version (8 bytes, R)
[DIAG_INFO]    DID 0xF12B: DDS Version (8 bytes, R)
[DIAG_INFO]    DID 0xF15A: Fingerprint Information (9 bytes, R/W)
[DIAG_INFO]    DID 0xF180: Bootloader Version Number (16 bytes, R)
[DIAG_INFO]    DID 0xF186: Active Diagnostic Session (1 bytes, R)
[DIAG_INFO]    DID 0xF187: Vehicle Manufacturer Spare Part Number (10 bytes, R)
[DIAG_INFO]    DID 0xF188: Software Number (10 bytes, R)
[DIAG_INFO]    DID 0xF18A: System Supplier Identifier (6 bytes, R)
[DIAG_INFO]    DID 0xF18B: ECU Manufacture Date (3 bytes, R)
[DIAG_INFO]    DID 0xF18C: ECU Serial Number (18 bytes, R/W)
[DIAG_INFO]    DID 0xF190: Vehicle Identification Number (VIN) (17 bytes, R/W)
2024-01-01 00:00:04:334  1871980      1  I  [DeltaInstaller.cpp][DeltaInstaller:26]:enter
[DIAG_INFO]    DID 0xF191: Hardware Number (10 bytes, R)
[DIAG_INFO]    DID 0xF193: ECU Hardware Version Number (2 bytes, R)
[DIAG_INFO]    DID 0xF195: ECU Software Version Number (12 bytes, R)
[DIAG_INFO]    DID 0xF197: ECU System Name (10 bytes, R)
[DIAG_INFO]    DID 0xF1A0: ECU Backup Software Version Number (8 bytes, R)
[DIAG_INFO]    DID 0xF1A1: ECU Backup Software Number (10 bytes, R)
[DIAG_INFO]    DID 0xF1F1: MPU1 Software Version Number (30 bytes, R)
[DIAG_INFO]    DID 0xF1FA: MCU1 Software Version Number (30 bytes, R)
2024-01-01 00:00:04:335  1871980      1  I  [MCUInstaller.cpp][MCUInstaller:32]:enter
[DIAG_INFO]    DID 0xF1FE: Level FBL security Constants (16 bytes, R/W)
[DIAG_INFO]    DID 0xF1FF: State of the security constant written (1 bytes, R)
[DIAG_DEBUG] RidManager: Constructor called
[DIAG_INFO]  RidManager: Initializing RID manager
[DIAG_INFO]  RidManager: Registering built-in RID implementations
[DIAG_DEBUG] RidBase: Initialized RID 0x0213 with access type 1
[DIAG_DEBUG] Rid0213: Initialized RID 0x0213
[ROX] 句柄创建成功
2024-01-01 00:00:04:336  1871980      1  I  [UpdateAction.cpp][UpdateAction:30]:enter
opt = s
[DIAG_INFO]  RidManager: Registered RID 0x0213 (A/B Switch Control)
optarg = 1
2024-01-01 00:00:04.380argv[optind - 1] = 1
[DIAG_DEBUG] RidBase: Initialized RID 0x0761 with access type 5

[DIAG_DEBUG] Rid0761: Initialized RID 0x0761
[DIAG_INFO]  RidManager: Registered RID 0x0761 (get IDCU Com_Key)
[[ROX] 连接失败，将自动重连
[DIAG_DEBUG] RidBase: Initialized RID 0x0596 with access type 1
TRANSPORT_UDPV4[DIAG_DEBUG] Rid0596: Initialized RID 0x0596
 [DIAG_INFO]  RidManager: Registered RID 0x0596 (ODO Clear)
Error[DIAG_DEBUG] RidBase: Initialized RID 0x0214 with access type 1
] 2024-01-01 00:00:04:614  1871980      1  I  [UpdateEngine.cpp][UpdateEngine:36]:enter
[DIAG_DEBUG] Rid0214: Initialized RID 0x0214
All whitelist interfaces were filtered out[DIAG_INFO]  RidManager: Registered RID 0x0214 (Vehicle pitch Angle and roll Angle Calibration)
[DIAG_DEBUG] RidBase: Initialized RID 0x0215 with access type 1
 -> Function [DIAG_DEBUG] Rid0215: Initialized RID 0x0215
[DIAG_INFO]  RidManager: Registered RID 0x0215 (ShowTouches_pointerLocation)
UDPv4Transport[DIAG_DEBUG] RidBase: Initialized RID 0x0216 with access type 7

[DIAG_DEBUG] Rid0216: Initialized RID 0x0216 (ADB Enable)
[DIAG_DEBUG] Rid0216: Initializing ADB communication interface
[DIAG_DEBUG] Rid0216: Reading ADB status from lighting control module
3
[DIAG_INFO]  Rid0216: Interface initialized, current ADB status: ADB Disabled
[DIAG_INFO]  RidManager: Registered RID 0x0216 (ADB Enable)
2024-01-01 00:00:04:616  1871980      1  I  [UpdateEngine.cpp][init:80]:enter
[DIAG_DEBUG] RidBase: Initialized RID 0x0218 with access type 1
[DIAG_DEBUG] Rid0218: Initialized RID 0x0218
[DIAG_INFO]  RidManager: Registered RID 0x0218 (Reset vehicle maintenance period)
[DIAG_DEBUG] RidBase: Initialized RID 0x0411 with access type 4
[DIAG_DEBUG] Rid0411: Initialized RID 0x0411
[DIAG_INFO]  RidManager: Registered RID 0x0411 (Debug Switch)
[DIAG_DEBUG] RidBase: Initialized RID 0x0412 with access type 1
[DIAG_DEBUG] Rid0412: Initialized RID 0x0412
[DIAG_INFO]  RidManager: Registered RID 0x0412 (Upgrade Method)
[DIAG_INFO]  RidManager: Built-in RID registration completed
[DIAG_INFO]  RidManager: Initialization completed, 9 RIDs registered
[DIAG_INFO]  RidManager: Registered RIDs (9 total):
[DIAG_INFO]    RID 0x0213: A/B Switch Control (Start)
[DIAG_INFO]    RID 0x0214: Vehicle pitch Angle and roll Angle Calibration (Start)
[DIAG_INFO]    RID 0x0215: ShowTouches_pointerLocation (Start)
[DIAG_INFO]    RID 0x0216: ADB Enable (Full)
[DIAG_INFO]    RID 0x0218: Reset vehicle maintenance period (Start)
2024-01-01 00:00:04:621  1871980      1  I  [UpdatePostInstall.cpp][UpdatePostInstall:17]:enter
[DIAG_INFO]    RID 0x0411: Debug Switch (Start/Stop)
[DIAG_INFO]    RID 0x0412: Upgrade Method (Start)
[DIAG_INFO]    RID 0x0596: ODO Clear (Start)
[DIAG_INFO]    RID 0x0761: get IDCU Com_Key (Start/Results)
[DIAG_DEBUG] DtcManager: Constructor called
[DIAG_INFO]  DtcManager: Initialized successfully
[DIAG_INFO]  CommunicationManager: Successfully initialized
[DIAG_INFO]  EcuResetManager: Successfully initialized
[DIAG_INFO]  DiagAppTask: Initializing IPC connection as 'aptiv'
2024-01-01 00:00:04:896  1871980      1  I  [UpdatePostInstall.cpp][getCurrentBank:162]:Enter
DefApp: 0-[]-A-00:00:04.896-logger.cpp-155-[OTA][1] file.cpp verify cmd:
swdl_utils -b
swdl_utils -b
[OTA][1] file.cpp verify cmd:
swdl_utils -b
swdl_utils -b
DefApp: 1-[]-A-00:00:04.897-logger.cpp-155-[OTA][2] file.cpp RunCommand start:[swdl_utils] tid:[2]
[OTA][2] file.cpp RunCommand start:[swdl_utils] tid:[2]
[DIAG_INFO]  DiagAppTask: IPC handle created successfully, attempting to connect to 'rox'
DefApp: 2-[]-A-00:00:04.899-logger.cpp-155-[OTA][2] file.cpp posix_spawnp:[swdl_utils] stdout:[/tmp/OTATmpFile-1AfpeH] stderr:[/tmp/OTATmpFile-3G8o3g]
[OTA][2] file.cpp posix_spawnp:[swdl_utils] stdout:[/tmp/OTATmpFile-1AfpeH] stderr:[/tmp/OTATmpFile-3G8o3g]
[DIAG_INFO]  DiagAppTask: Successfully established IPC connection with 'rox'
[DIAG_DEBUG] DiagAppTask create sal queue succeed
[DIAG_DEBUG] DiagAppTask create sal queue succeed
[DIAG_INFO]  DiagAppTask: DEM and HISIP services initialized
[DIAG_INFO]  DiagAppTask: Ready to process MCU protocol messages via IPC callback
[DIAG_DEBUG] DiagAppTask create sal queue succeed
[DIAG_INFO]  UdsManage initialize.
DefApp: 3-[]-A-00:00:04.902-logger.cpp-155-[OTA][2] file.cpp posix_spawnp success [swdl_utils] pid:1912900
[OTA][2] file.cpp posix_spawnp success [swdl_utils] pid:1912900
DefApp: 4-[]-A-00:00:04.955-logger.cpp-155-[OTA][2] file.cpp wait child process quit success. pid:1912900 timeout:50ms
[OTA][2] file.cpp wait child process quit success. pid:1912900 timeout:50ms
DefApp: 5-[]-A-00:00:04.955-logger.cpp-155-[OTA][2] file.cpp stdout:swdl_utils: BANK_A
Result: Success

stderr:swdl_lun_init:858 System banked to "A"

[OTA][2] file.cpp stdout:swdl_utils: BANK_A
Result: Success

stderr:swdl_lun_init:858 System banked to "A"

DefApp: 6-[]-A-00:00:04.955-logger.cpp-155-[OTA][2] file.cpp remove temporary file:[/tmp/OTATmpFile-3G8o3g]
[OTA][2] file.cpp remove temporary file:[/tmp/OTATmpFile-3G8o3g]
DefApp: 7-[]-A-00:00:04.955-logger.cpp-155-[OTA][2] file.cpp remove temporary file:[/tmp/OTATmpFile-1AfpeH]
[OTA][2] file.cpp remove temporary file:[/tmp/OTATmpFile-1AfpeH]
DefApp: 8-[]-A-00:00:04.955-logger.cpp-155-[OTA][2] file.cpp RunCommand end:[swdl_utils] tid:[2]
[OTA][2] file.cpp RunCommand end:[swdl_utils] tid:[2]
DefApp: 9-[]-A-00:00:04.956-logger.cpp-155-[OTA][1] file.cpp wait cmd:[swdl_utils] delta time:[59.0/600000] result:[0]
[OTA][1] file.cpp wait cmd:[swdl_utils] delta time:[59.0/600000] result:[0]
DefApp: 10-[]-A-00:00:04.956-logger.cpp-155-[OTA][1] utils.cpp [swdl_utils -b] got slot:[0] output:
swdl_utils: BANK_A
Result: Success
swdl_lun_init:858 System banked to "A"

[OTA][1] utils.cpp [swdl_utils -b] got slot:[0] output:
swdl_utils: BANK_A
Result: Success
swdl_lun_init:858 System banked to "A"

DefApp: 11-[]-A-00:00:04.956-logger.cpp-155-[OTA][1] aptiv_installer.cpp aptiv_installer_get_current_bank called. current_bank=0
[OTA][1] aptiv_installer.cpp aptiv_installer_get_current_bank called. current_bank=0
2024-01-01 00:00:05:233  1871980      1  D  [UpdatePostInstall.cpp][getCurrentBank:166]:bank in _a parti

2024-01-01 00:00:05:233  1871980      1  I  [UpdatePostInstall.cpp][getCurrentBank:162]:Enter
DefApp: 12-[]-A-00:00:05.233-logger.cpp-155-[OTA][1] aptiv_installer.cpp aptiv_installer_get_current_bank called. current_bank=0
[OTA][1] aptiv_installer.cpp aptiv_installer_get_current_bank called. current_bank=0
2024-01-01 00:00:05:233  1871980      1  D  [UpdatePostInstall.cpp][getCurrentBank:166]:bank in _a parti

2024-01-01 00:00:05:234  1871980      1  I  [UpdateEngine.cpp][init:91]:current slot is A
2024-01-01 00:00:05:234  1871980      1  D  [UpdateStoreFile.cpp][write:71]:status:2 verify:-1 result:0 object:0
2024-01-01 00:00:05:235  1871980      1  I  [UpdateCrypto.cpp][UpdateCrypto:14]:enter
2024-01-01 00:00:05:235  1871980      1  I  [PackageAnalyzer.cpp][PackageAnalyzer:29]:enter mPkgPath:/var/update/ota/package/update.zip
2024-01-01 00:00:05:236  1871980      1  I  [TrackManager.cpp][initialize:76]:track manager init success
2024-01-01 00:00:05:236  1871980      1  I  [UpdateEngine.cpp][init:142]:------------------start selfcheck
2024-01-01 00:00:05:236  1871980      1  D  [DoipComm.cpp][setDoipListener:134]:enter
2024-01-01 00:00:05:236  1871980      1  D  [DoipComm.cpp][init:125]:enter
[setloginfo, 89] path=, isprintout=1
[setLogLevel 178] lev=2
[Mon 01 Jan 2024 00:00:05.242][pid:1871980] LOG_DEBUG:[DoipMsgHandle: 14] DoipCommHeader size=6
[Mon 01 Jan 2024 00:00:05.242][pid:1871980] LOG_DEBUG:[openServer: 34]serverId=7

[Mon 01 Jan 2024 00:00:05.242][pid:1871980] LOG_DEBUG:[openServer, 69] server_tcp=7 start listen doipserver...
[Mon 01 Jan 2024 00:00:05.242][pid:1871980] LOG_DEBUG:[init, 80]inited...
[Mon 01 Jan 2024 00:00:05.242][pid:1871980] LOG_DEBUG:[run, 136]start listen thread tid=4

2024-01-01 00:00:05:243  1871980      1  I  [UpdatePostInstall.cpp][~UpdatePostInstall:22]:enter
2024-01-01 00:00:05:243  1871980      5  D  [DoipComm.cpp][pps_test_proc:316]:enter
2024-01-01 00:00:05:243  1871980      1  I  [UpdateEngine.cpp][doSelfCheck:270]:enter
2024-01-01 00:00:05:243  1871980      1  I  [UpdateAction.cpp][doSelfCheck:341]:enter
2024-01-01 00:00:05:243  1871980      1  I  [MCUInstaller.cpp][isMCUInBootState:216]:enter
2024-01-01 00:00:05:243  1871980      5  D  [DoipComm.cpp][pps_test_proc:324]:open test fd failed:-1
2024-01-01 00:00:05:243  1871980      1  I  [UpdateAction.cpp][doSelfCheck:345]:SelfCheck MCU not in boot state
2024-01-01 00:00:05:244  1871980      1  E  [PanelInstaller.cpp][getPkgVersion:282]:panel package path not exist : /etc/PANEL/
2024-01-01 00:00:05:244  1871980      1  E  [PanelInstaller.cpp][getPkgVersion:282]:panel package path not exist : /etc/PANEL/
2024-01-01 00:00:05:244  1871980      1  E  [PanelInstaller.cpp][getPkgVersion:282]:panel package path not exist : /etc/PANEL/
2024-01-01 00:00:05:245  1871980      1  E  [PanelInstaller.cpp][getPkgVersion:282]:panel package path not exist : /etc/PANEL/
2024-01-01 00:00:05:245  1871980      1  I  [UpdateEngine.cpp][run:190]:current status: 0, switch to next status: 1
2024-01-01 00:00:05:245  1871980      1  D  [UpdateStoreFile.cpp][write:71]:status:1 verify:-1 result:0 object:0
2024-01-01 00:00:05:525  1871980      1  I  [UpdateEngine.cpp][startSelfCheckCallback:254]:enter
2024-01-01 00:00:05:526  1871980      1  I  [UpdateEngine.cpp][calculatePkgHash:277]:enter
2024-01-01 00:00:05:526  1871980      1  E  [CFile.cpp][isExisted:37]:cannot access /var/update/ota/package/update.zip, error: No such process
2024-01-01 00:00:05:526  1871980      1  D  [UpdateEngine.cpp][calculatePkgHash:280]:/var/update/ota/package/update.zip is not existed
2024-01-01 00:00:05:526  1871980      1  I  [UpdateEngine.cpp][run:190]:current status: 1, switch to next status: 2
2024-01-01 00:00:05:526  1871980      1  D  [UpdateStoreFile.cpp][write:71]:status:2 verify:-1 result:0 object:0
[DIAG_INFO]  DiagAppTask: Received message: 82 00 07 02 00 00 00 00 (len=8)
[DIAG_INFO]  DiagAppTask: Processing business message, type=0x82
[DIAG_INFO]  DiagAppTask: Processing business message type=0x82
[DIAG_INFO]  DiagAppTask: 0x82 query - group=0x07, func=0x02
[DIAG_INFO]  DiagAppTask: Handling speed request
[DIAG_INFO]  DiagAppTask: Processing vehicle speed request
[DIAG_INFO]  DID 0x0001 HISIP read success, length=3
[DIAG_INFO]  Did0001: HISIP read successful, length=3
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=6
[DIAG_INFO]  DiagAppTask: Sent payload: 07 02 01 00 00 00
[DIAG_INFO]  DiagAppTask: Received message: 82 00 02 02 00 00 00 00 (len=8)
[DIAG_INFO]  DiagAppTask: Processing business message, type=0x82
[DIAG_INFO]  DiagAppTask: Processing business message type=0x82
[DIAG_INFO]  DiagAppTask: 0x82 query - group=0x02, func=0x02
[DIAG_INFO]  DiagAppTask: Handling MCU version request
[DIAG_INFO]  DiagAppTask: Processing MCU version request
[DIAG_INFO]  DID 0x0002 HISIP read success, length=17
[DIAG_INFO]  Did0002: HISIP read successful, length=17
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=20
[DIAG_INFO]  DiagAppTask: Sent payload: 02 02 01 42 4F 4F 54 2E 00 00 00 FF 00 00 00 60 6B 00 70 00
[DIAG_INFO]  DiagAppTask: Received message: 97 81 01 01 00 00 00 00 07 0F 00 15 23 22 D1 00 (len=16)
[DIAG_INFO]  DiagAppTask: Processing UDS diagnostic message
[DIAG_INFO]  DiagAppTask: UDS frame header: frame_cnt=1, frame_no=0, payload_len=7, SA=0x0F00, TA=0x1523
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=14
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 01 01 00 00 00 00 05 15 23 0F 00 00
[DIAG_INFO]  DiagAppTask: UDS message target_addr=0x1523
[DIAG_INFO]  DiagAppTask: UDS data[3]: 22 D1 00
[DIAG_INFO]  DiagAppTask: Processing local UDS service, len=3
[DIAG_INFO]  DiagAppTask: Processing UDS SID: 0x22, len=3
[DIAG_INFO]  DiagAppTask: UDS data detail: 22 D1 00
[DIAG_INFO]  DiagAppTask: Read DID 0xD100
[DIAG_INFO]  DidManager: Handling ReadDataByIdentifier for DID 0xD100
[DIAG_INFO]  DidD100: Reading SWB LIN status
[DIAG_INFO]  DID 0xD100 HISIP read success, length=2
[DIAG_INFO]  DidD100: HISIP read successful, length=2
[DIAG_DEBUG] DidD100: Data[0]=0x00 Data[1]=0x00
[DIAG_INFO]  DidD100: Read successful - Byte0: 0x00, Byte1: 0x00
[DIAG_INFO]  DidManager: Read operation successful for DID 0xD100, 2 bytes
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=18
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 03 01 00 00 00 00 09 15 23 0F 00 62 D1 00 00 00
[DIAG_INFO]  DiagAppTask: Received message: 97 81 02 01 00 00 00 00 07 0F 00 15 23 22 DF 01 (len=16)
[DIAG_INFO]  DiagAppTask: Processing UDS diagnostic message
[DIAG_INFO]  DiagAppTask: UDS frame header: frame_cnt=1, frame_no=0, payload_len=7, SA=0x0F00, TA=0x1523
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=14
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 01 01 00 00 00 00 05 15 23 0F 00 00
[DIAG_INFO]  DiagAppTask: UDS message target_addr=0x1523
[DIAG_INFO]  DiagAppTask: UDS data[3]: 22 DF 01
[DIAG_INFO]  DiagAppTask: Processing local UDS service, len=3
[DIAG_INFO]  DiagAppTask: Processing UDS SID: 0x22, len=3
[DIAG_INFO]  DiagAppTask: UDS data detail: 22 DF 01
[DIAG_INFO]  DiagAppTask: Read DID 0xDF01
[DIAG_INFO]  DidManager: Handling ReadDataByIdentifier for DID 0xDF01
[DIAG_INFO]  DidDF01: Reading software update hash
[DIAG_INFO]  DidDF01: Reading Software Update Hash from EEPROM via HISIP
[DIAG_INFO]  DID 0xDF01 HISIP read success, length=32
[DIAG_INFO]  DidDF01: HISIP read successful, hash length: 32 bytes
[DIAG_INFO]  DidDF01: Read successful - Hash: 0000000000000000000000000000000000000000000000000000000000000000
[DIAG_INFO]  DidManager: Read operation successful for DID 0xDF01, 32 bytes
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=48
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 03 01 00 00 00 00 27 15 23 0F 00 62 DF 01 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
[DIAG_INFO]  DiagAppTask: Received message: 97 81 03 01 00 00 00 00 07 0F 00 15 23 22 F1 01 (len=16)
[DIAG_INFO]  DiagAppTask: Processing UDS diagnostic message
[DIAG_INFO]  DiagAppTask: UDS frame header: frame_cnt=1, frame_no=0, payload_len=7, SA=0x0F00, TA=0x1523
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=14
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 01 01 00 00 00 00 05 15 23 0F 00 00
[DIAG_INFO]  DiagAppTask: UDS message target_addr=0x1523
[DIAG_INFO]  DiagAppTask: UDS data[3]: 22 F1 01
[DIAG_INFO]  DiagAppTask: Processing local UDS service, len=3
[DIAG_INFO]  DiagAppTask: Processing UDS SID: 0x22, len=3
[DIAG_INFO]  DiagAppTask: UDS data detail: 22 F1 01
[DIAG_INFO]  DiagAppTask: Read DID 0xF101
[DIAG_INFO]  DidManager: Handling ReadDataByIdentifier for DID 0xF101
[DIAG_INFO]  DidF101: Reading vehicle configuration
[DIAG_INFO]  DidF101: Reading Vehicle Configuration from EEPROM via HISIP
[DIAG_INFO]  DID 0xF101 HISIP read success, length=32
[DIAG_INFO]  DidF101: HISIP read successful, length=32
[DIAG_INFO]  DidF101: Config - Model:0, Battery:0, Color:0(new: standard), AC:0
[DIAG_INFO]  DidF101: Advanced - FenceLock:0(Dealer), Seats:0, CityNOA:0, TrafficLight:0
[DIAG_INFO]  DidManager: Read operation successful for DID 0xF101, 32 bytes
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=48
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 03 01 00 00 00 00 27 15 23 0F 00 62 F1 01 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
[Mon 01 Jan 2024 00:00:08.618][pid:1871980] LOG_DEBUG:[run: 183]accept new client=8, ip=127.0.0.1, port=65479
[DIAG_INFO]  DiagAppTask: Received message: 97 81 04 01 00 00 00 00 07 0F 00 15 23 22 F1 11 (len=16)
[DIAG_INFO]  DiagAppTask: Processing UDS diagnostic message
[DIAG_INFO]  DiagAppTask: UDS frame header: frame_cnt=1, frame_no=0, payload_len=7, SA=0x0F00, TA=0x1523
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=14
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 01 01 00 00 00 00 05 15 23 0F 00 00
[DIAG_INFO]  DiagAppTask: UDS message target_addr=0x1523
[DIAG_INFO]  DiagAppTask: UDS data[3]: 22 F1 11
[DIAG_INFO]  DiagAppTask: Processing local UDS service, len=3
[DIAG_INFO]  DiagAppTask: Processing UDS SID: 0x22, len=3
[DIAG_INFO]  DiagAppTask: UDS data detail: 22 F1 11
[DIAG_INFO]  DiagAppTask: Read DID 0xF111
[DIAG_INFO]  DidManager: Handling ReadDataByIdentifier for DID 0xF111
[DIAG_INFO]  DidF111: Reading VDC WIFI SSID
[DIAG_INFO]  DidF111: Reading VDC WIFI SSID from EEPROM via HISIP
[DIAG_INFO]  DID 0xF111 HISIP read success, length=32
[DIAG_INFO]  DidF111: HISIP read successful, length=32
[DIAG_INFO]  DidF111: Read successful - SSID length: 0
[DIAG_INFO]  DidManager: Read operation successful for DID 0xF111, 32 bytes
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=48
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 03 01 00 00 00 00 27 15 23 0F 00 62 F1 11 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
[DIAG_INFO]  DiagAppTask: Received message: 97 81 05 01 00 00 00 00 07 0F 00 15 23 22 F1 12 (len=16)
[DIAG_INFO]  DiagAppTask: Processing UDS diagnostic message
[DIAG_INFO]  DiagAppTask: UDS frame header: frame_cnt=1, frame_no=0, payload_len=7, SA=0x0F00, TA=0x1523
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=14
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 01 01 00 00 00 00 05 15 23 0F 00 00
[DIAG_INFO]  DiagAppTask: UDS message target_addr=0x1523
[DIAG_INFO]  DiagAppTask: UDS data[3]: 22 F1 12
[DIAG_INFO]  DiagAppTask: Processing local UDS service, len=3
[DIAG_INFO]  DiagAppTask: Processing UDS SID: 0x22, len=3
[DIAG_INFO]  DiagAppTask: UDS data detail: 22 F1 12
[DIAG_INFO]  DiagAppTask: Read DID 0xF112
[DIAG_INFO]  DidManager: Handling ReadDataByIdentifier for DID 0xF112
[DIAG_INFO]  DidF112: Reading VDC WIFI Password
[DIAG_INFO]  DidF112: Reading VDC WIFI Password from EEPROM via HISIP
[DIAG_INFO]  DID 0xF112 HISIP read success, length=64
[DIAG_INFO]  DidF112: HISIP read successful, length=64
[DIAG_INFO]  DidF112: Read successful - Password length: 0
[DIAG_INFO]  DidManager: Read operation successful for DID 0xF112, 64 bytes
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=80
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 03 01 00 00 00 00 47 15 23 0F 00 62 F1 12 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
[DIAG_INFO]  DiagAppTask: Received message: 97 81 06 01 00 00 00 00 07 0F 00 15 23 22 F1 13 (len=16)
[DIAG_INFO]  DiagAppTask: Processing UDS diagnostic message
[DIAG_INFO]  DiagAppTask: UDS frame header: frame_cnt=1, frame_no=0, payload_len=7, SA=0x0F00, TA=0x1523
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=14
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 01 01 00 00 00 00 05 15 23 0F 00 00
[DIAG_INFO]  DiagAppTask: UDS message target_addr=0x1523
[DIAG_INFO]  DiagAppTask: UDS data[3]: 22 F1 13
[DIAG_INFO]  DiagAppTask: Processing local UDS service, len=3
[DIAG_INFO]  DiagAppTask: Processing UDS SID: 0x22, len=3
[DIAG_INFO]  DiagAppTask: UDS data detail: 22 F1 13
[DIAG_INFO]  DiagAppTask: Read DID 0xF113
[DIAG_INFO]  DidManager: Handling ReadDataByIdentifier for DID 0xF113
[DIAG_INFO]  DidF113: Reading VDC WIFI AP MAC whitelist
[DIAG_INFO]  DidF113: Reading VDC WIFI AP MAC whitelist from EEPROM via HISIP
[DIAG_INFO]  DID 0xF113 HISIP read success, length=335
[DIAG_INFO]  DidF113: HISIP read successful (received length=335, buffer length=335)
[DIAG_INFO]  DidF113: Read successful - 0 MAC addresses
[DIAG_INFO]  DidManager: Read operation successful for DID 0xF113, 335 bytes
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=351
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 03 01 00 00 00 01 56 15 23 0F 00 62 F1 13 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
[DIAG_INFO]  DiagAppTask: Received message: 97 81 07 01 00 00 00 00 07 0F 00 15 23 22 F1 14 (len=16)
[DIAG_INFO]  DiagAppTask: Processing UDS diagnostic message
[DIAG_INFO]  DiagAppTask: UDS frame header: frame_cnt=1, frame_no=0, payload_len=7, SA=0x0F00, TA=0x1523
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=14
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 01 01 00 00 00 00 05 15 23 0F 00 00
[DIAG_INFO]  DiagAppTask: UDS message target_addr=0x1523
[DIAG_INFO]  DiagAppTask: UDS data[3]: 22 F1 14
[DIAG_INFO]  DiagAppTask: Processing local UDS service, len=3
[DIAG_INFO]  DiagAppTask: Processing UDS SID: 0x22, len=3
[DIAG_INFO]  DiagAppTask: UDS data detail: 22 F1 14
[DIAG_INFO]  DiagAppTask: Read DID 0xF114
[DIAG_INFO]  DidManager: Handling ReadDataByIdentifier for DID 0xF114
[DIAG_INFO]  DidF114: Reading VDC WIFI configuration write state
[DIAG_INFO]  DidF114: Reading VDC WIFI Configuration Write State from EEPROM via HISIP
[DIAG_INFO]  DID 0xF114 HISIP read success, length=1
[DIAG_INFO]  DidF114: HISIP read successful, write state: 0x00
[DIAG_INFO]  DidF114: Read successful - State: 0x00 (SSID:NA, Password:NA, MAC:NA)
[DIAG_INFO]  DidManager: Read operation successful for DID 0xF114, 1 bytes
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=17
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 03 01 00 00 00 00 08 15 23 0F 00 62 F1 14 00
[DIAG_INFO]  DiagAppTask: Received message: 97 81 08 01 00 00 00 00 07 0F 00 15 23 22 F1 90 (len=16)
[DIAG_INFO]  DiagAppTask: Processing UDS diagnostic message
[DIAG_INFO]  DiagAppTask: UDS frame header: frame_cnt=1, frame_no=0, payload_len=7, SA=0x0F00, TA=0x1523
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=14
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 01 01 00 00 00 00 05 15 23 0F 00 00
[DIAG_INFO]  DiagAppTask: UDS message target_addr=0x1523
[DIAG_INFO]  DiagAppTask: UDS data[3]: 22 F1 90
[DIAG_INFO]  DiagAppTask: Processing local UDS service, len=3
[DIAG_INFO]  DiagAppTask: Processing UDS SID: 0x22, len=3
[DIAG_INFO]  DiagAppTask: UDS data detail: 22 F1 90
[DIAG_INFO]  DiagAppTask: Read DID 0xF190
[DIAG_INFO]  DidManager: Handling ReadDataByIdentifier for DID 0xF190
[DIAG_INFO]  DidF190: Reading VIN
[DIAG_INFO]  DidF190: Reading Vehicle Identification Number (VIN) from EEPROM via HISIP
[DIAG_INFO]  DID 0xF190 HISIP read success, length=17
[DIAG_INFO]  DidF190: HISIP read successful, length=17
[DIAG_INFO]  DidF190: Read successful - VIN:
[DIAG_INFO]  DidManager: Read operation successful for DID 0xF190, 17 bytes
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=33
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 03 01 00 00 00 00 18 15 23 0F 00 62 F1 90 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
[DIAG_INFO]  DiagAppTask: Received message: 97 81 09 01 00 00 00 00 07 0F 00 15 23 22 F1 F1 (len=16)
[DIAG_INFO]  DiagAppTask: Processing UDS diagnostic message
[DIAG_INFO]  DiagAppTask: UDS frame header: frame_cnt=1, frame_no=0, payload_len=7, SA=0x0F00, TA=0x1523
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=14
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 01 01 00 00 00 00 05 15 23 0F 00 00
[DIAG_INFO]  DiagAppTask: UDS message target_addr=0x1523
[DIAG_INFO]  DiagAppTask: UDS data[3]: 22 F1 F1
[DIAG_INFO]  DiagAppTask: Processing local UDS service, len=3
[DIAG_INFO]  DiagAppTask: Processing UDS SID: 0x22, len=3
[DIAG_INFO]  DiagAppTask: UDS data detail: 22 F1 F1
[DIAG_INFO]  DiagAppTask: Read DID 0xF1F1
[DIAG_INFO]  DidManager: Handling ReadDataByIdentifier for DID 0xF1F1
[DIAG_INFO]  DidF1F1: Reading MPU1 software version
[DIAG_DEBUG] DidF1F1: Read from /version.txt completed
[DIAG_INFO]  DidF1F1: Read successful - MPU1 Software Version: MY26X_DA01DXXDEV_260113_0203
[DIAG_INFO]  DidManager: Read operation successful for DID 0xF1F1, 30 bytes
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=46
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 03 01 00 00 00 00 25 15 23 0F 00 62 F1 F1 4D 59 32 36 58 5F 44 41 30 31 44 58 58 44 45 56 5F 32 36 30 31 31 33 5F 30 32 30 33 20 20
[DIAG_INFO]  DiagAppTask: Received message: 97 81 0A 01 00 00 00 00 07 0F 00 15 23 22 F1 FA (len=16)
[DIAG_INFO]  DiagAppTask: Processing UDS diagnostic message
[DIAG_INFO]  DiagAppTask: UDS frame header: frame_cnt=1, frame_no=0, payload_len=7, SA=0x0F00, TA=0x1523
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=14
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 01 01 00 00 00 00 05 15 23 0F 00 00
[DIAG_INFO]  DiagAppTask: UDS message target_addr=0x1523
[DIAG_INFO]  DiagAppTask: UDS data[3]: 22 F1 FA
[DIAG_INFO]  DiagAppTask: Processing local UDS service, len=3
[DIAG_INFO]  DiagAppTask: Processing UDS SID: 0x22, len=3
[DIAG_INFO]  DiagAppTask: UDS data detail: 22 F1 FA
[DIAG_INFO]  DiagAppTask: Read DID 0xF1FA
[DIAG_INFO]  DidManager: Handling ReadDataByIdentifier for DID 0xF1FA
[DIAG_INFO]  DidF1FA: Reading MCU1 software version
[DIAG_INFO]  DidF1FA: Reading storage from EEPROM via HISIP
[DIAG_INFO]  DID 0xF1FA HISIP read success, length=30
[DIAG_INFO]  DidF1FA: HISIP read successful
[DIAG_DEBUG] DidF1FA: Read from storage completed
[DIAG_INFO]  DidF1FA: Read successful - MCU1 Software Version: preEMC.S.5P00.000.20260113.BN2
[DIAG_INFO]  DidManager: Read operation successful for DID 0xF1FA, 30 bytes
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=46
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 03 01 00 00 00 00 25 15 23 0F 00 62 F1 FA 70 72 65 45 4D 43 2E 53 2E 35 50 30 30 2E 30 30 30 2E 32 30 32 36 30 31 31 33 2E 42 4E 32
[DIAG_INFO]  DiagAppTask: Received message: 97 81 0B 01 00 00 00 00 07 0F 00 15 23 22 F1 FE (len=16)
[DIAG_INFO]  DiagAppTask: Processing UDS diagnostic message
[DIAG_INFO]  DiagAppTask: UDS frame header: frame_cnt=1, frame_no=0, payload_len=7, SA=0x0F00, TA=0x1523
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=14
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 01 01 00 00 00 00 05 15 23 0F 00 00
[DIAG_INFO]  DiagAppTask: UDS message target_addr=0x1523
[DIAG_INFO]  DiagAppTask: UDS data[3]: 22 F1 FE
[DIAG_INFO]  DiagAppTask: Processing local UDS service, len=3
[DIAG_INFO]  DiagAppTask: Processing UDS SID: 0x22, len=3
[DIAG_INFO]  DiagAppTask: UDS data detail: 22 F1 FE
[DIAG_INFO]  DiagAppTask: Read DID 0xF1FE
[DIAG_INFO]  DidManager: Handling ReadDataByIdentifier for DID 0xF1FE
[DIAG_INFO]  DidF1FE: Reading FBL security constant
[DIAG_WARN]  SecureStore: Get_Secret_Data failed, rc=-341
[DIAG_WARN]  DidF1FE: SecureStore read failed or length mismatch (len=0), using default value
[DIAG_INFO]  DidManager: Read operation successful for DID 0xF1FE, 16 bytes
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=32
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 03 01 00 00 00 00 17 15 23 0F 00 62 F1 FE 97 38 F4 95 37 6F 60 E6 27 F7 75 81 CB 30 74 F8
[DIAG_INFO]  DiagAppTask: Received message: 97 81 0C 01 00 00 00 00 07 0F 00 15 23 22 F1 FF (len=16)
[DIAG_INFO]  DiagAppTask: Processing UDS diagnostic message
[DIAG_INFO]  DiagAppTask: UDS frame header: frame_cnt=1, frame_no=0, payload_len=7, SA=0x0F00, TA=0x1523
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=14
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 01 01 00 00 00 00 05 15 23 0F 00 00
[DIAG_INFO]  DiagAppTask: UDS message target_addr=0x1523
[DIAG_INFO]  DiagAppTask: UDS data[3]: 22 F1 FF
[DIAG_INFO]  DiagAppTask: Processing local UDS service, len=3
[DIAG_INFO]  DiagAppTask: Processing UDS SID: 0x22, len=3
[DIAG_INFO]  DiagAppTask: UDS data detail: 22 F1 FF
[DIAG_INFO]  DiagAppTask: Read DID 0xF1FF
[DIAG_INFO]  DidManager: Handling ReadDataByIdentifier for DID 0xF1FF
[DIAG_INFO]  DidF1FF: Reading security constant write status
[DIAG_WARN]  SecureStore: Get_Secret_Data failed, rc=-341
[DIAG_INFO]  DidF1FF: Read successful - Status=0x10 (IMMO=0, Safety=0, FBL=1)
[DIAG_INFO]  DidManager: Read operation successful for DID 0xF1FF, 1 bytes
[DIAG_INFO]  DiagAppTask: Pure payload sent - len=17
[DIAG_INFO]  DiagAppTask: Sent payload: 06 81 03 01 00 00 00 00 08 15 23 0F 00 62 F1 FF 10