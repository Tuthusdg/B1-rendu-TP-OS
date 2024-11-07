# TP1 Plip plap votre 1. 
## I.Ressources de l'OS
### 1. Programme, service, processus

Lister tous les processus en cours d'exécution sur votre machine

```powershell
PS C:\Users\arthu> Get-Process

Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName
-------  ------    -----      -----     ------     --  -- -----------
    193      12     4760      11344              3688   0 AggregatorHost
    493      24    15732      37128       0,81   8712   1 ApplicationFrameHost
    692      30    45352      85656      19,39  18976   1 ArcControl
    690      46   187076     142332      14,28   1216   1 ArcControlAssist
    372      26    43428      71944      10,70   9504   1 ArcControlAssist
    363      25    42304      69240      13,05  17036   1 ArcControlAssist
    356      39    18464      76916       4,30  19480   1 ArcControlAssist
    272      17    11648      15000       0,09  19524   1 ArcControlAssist
    355      20    13688      23624       1,17  19556   1 ArcControlAssist
    581      33   155384      83468              4536   0 ArcControlService
    171      10     5612      11128       0,03  15180   0 audiodg
    414      42    23640       1600       0,13  19080   1 backgroundTaskHost
    311      33    18148       2264       0,05  20056   1 backgroundTaskHost
    459      31    93444     156952       7,30   6584   1 chrome
    601      48   180772     232808      20,98   9840   1 chrome
   1657      64    88532     218152      12,36  10408   1 chrome
    215      11     6640       9076       0,02  10792   1 chrome
    315      24    33232      79844       0,42  10892   1 chrome
   1443      54   329896     362604      19,70  10952   1 chrome
    229      18    15032      30348       0,02  15068   1 chrome
    179      14     6996      16856       0,03  21576   1 chrome
    203      14     8960      21104       0,19  24904   1 chrome
    296      21    21340      51264       0,11  26000   1 chrome
    577      62    24288      49960       1,19  26668   1 chrome
     94       7     5256       5172             10048   0 conhost
    130       9     5484       6336             12656   0 conhost
    148       9     1392       8388       0,02  20072   1 conhost
    875      30     2436       5216               908   0 csrss
    880      33     3284       7352              1008   1 csrss
    730      25    24928      31552       6,16  11888   1 ctfmon
    205      14     4164      12240             18204   0 dasHost
    208      12    11556      33480       0,00  14948   1 Discord
   1366      34   171744     217344      18,80  14968   1 Discord
    283      17    12424      81576       0,05  23688   1 Discord
    358      20    15904      54124       0,44  24352   1 Discord
   1085      46    97920     131780       5,00  24836   1 Discord
   1332     105   370276     356940      77,17  26484   1 Discord
    216      15     3312      10432       0,05  10468   1 dllhost
    150       9     2012       9508       0,19  11564   1 dllhost
    129       8     1452       6788       0,00  15992   1 dllhost
   1194      78    75204     103960              4356   0 DSAService
    532      49    29540      48736       0,94   7540   1 DSATray
    691      30    33052      37672              4336   0 DSAUpdateService
   1992      89   230312     134756              1656   1 dwm
    534      32    23536      36328             13224   0 EABackgroundService
    896      35   212156     129588       7,02  13480   1 EACefSubProcess
    242      17     9308      15652       0,16  14040   1 EACefSubProcess
    347      25    13808      30716       5,86  14052   1 EACefSubProcess
    426      24    99448     131460      36,22  14172   1 EACefSubProcess
    267      19    14324      24728       0,14  14280   1 EACefSubProcess
   1343     131   244700     132972      51,80   2692   1 EADesktop
    445      27    16652      26784      13,31  13668   1 EALocalHostSvc
   1266     127   217812      88200      51,88  26664   1 EpicGamesLauncher
    303      22    37224      30600       1,06  16148   1 EpicWebHelper
    463      27    65440      41912       0,06  21012   1 EpicWebHelper
    119       8     1620       5360              4908   0 esif_uf
    898      29   148608      32184      18,59  16376   1 esrv
   1696      37   208648      56600             11448   0 esrv_svc
   7630     216   418892     394268      96,09   1312   1 explorer
    437      21     6864      27500       0,05  16780   1 FileCoAuth
    263      10     1888       7284              4408   0 FMService64
     42       8     2068       2752              1248   0 fontdrvhost
     42      10     3444       6984              1256   1 fontdrvhost
    372      21     6376      22992       0,45   8224   1 GameBarFTServer
      0       0       60          8                 0   0 Idle
    579      35    49568      26208       1,17  16176   1 IGCC
    770      49    95616      89080       1,27  17972   1 IGCCTray
    219      12     2560      10152              2892   0 igfxCUIServiceN
    604      15     4292      13784       1,05   6532   1 igfxEMN
    122       8     1456       5996              7152   0 igfxextN
    207      12     2316       9624             10628   0 Intel_PIE_Service
    150       8     1436       5344              2084   0 IntelCpHDCPSvc
    136       8     1276       5128              5084   0 jhi_service
    405      20     3764      17428       0,69   7344   1 jucheck
    460      23     4032      22288       0,69  12388   1 jusched
    465      28    39396      33732              4592   0 LCD_Service
    230      12     3176       9144              3996   0 LMS
    624      30    41656      57700       1,34   5188   1 LockApp
     61      10     1448       3704              1088   0 LsaIso
   1949      30    12192      24324              1104   0 lsass
   1718      86    68456      94508      23,52   8492   1 MBAMessageCenter
    295      23    12864      19144              7764   1 MBAPersistentCenter
    187      14     2312       7276              4276   0 mDNSResponder
      0       0     1520     437548              3252   0 Memory Compression
    526      30    36260      41276       0,92  13648   1 Microsoft.SharePoint
    485      18    13884      25956             18704   0 MpDefenderCoreService
    350      22    12732      37392       0,33   3840   1 msedge
    383      23    61204      58012       0,28   5844   1 msedge
    172      12     7544      18052       0,02  12232   1 msedge
    147      10     2164       8468       0,00  14616   1 msedge
   1225      46    54368     131772       1,70  16004   1 msedge
    160      10     2172       7164       0,00    628   1 msedgewebview2
   1329      53    40064       5240       8,06   2244   1 msedgewebview2
    176      12     8656          0       0,63   4884   1 msedgewebview2
    374      22    12828        460       3,63   6200   1 msedgewebview2
    373      34    99956     144040       7,33   7628   1 msedgewebview2
    406      25    13872      39496       1,53  12140   1 msedgewebview2
    687      55   224844        804      57,05  14032   1 msedgewebview2
   1274      44   237412       5052      21,98  14080   1 msedgewebview2
    159      10     2180       8468       0,03  24236   1 msedgewebview2
    280      23    31004      62620       0,41  24400   1 msedgewebview2
   1252      54    37384     114296       3,06  26436   1 msedgewebview2
    224      15     7472        788       0,34  26440   1 msedgewebview2
    798      28    95488     119244       2,19  26516   1 msedgewebview2
    174      11     9196      19740       0,11  27020   1 msedgewebview2
    994     216   268196     175836              8460   0 MsMpEng
    441      18     6652      21316              4772   0 NahimicService
    227      14     4468      11536              2920   0 NisSrv
    772      28    37384      37884              4328   0 OfficeClickToRun
    451      28    41880      44832              4520   0 OneApp.IGCC.WinService
   1134      63   100456     117212       2,75  14308   1 OneDrive
    295      15     3076      16064       0,05  22912   1 OpenConsole
    245      13     2692      11016              4808   0 osdservice
    579      34    17880      32204              4668   0 PCManagerMainService
   1493     159    95424     205580       8,22  24944   1 PhoneExperienceHost
    735      32    71028      89576       1,52   1540   1 powershell
    252      29    31812      20136              8960   0 PresentationFontCache
      0      19    11092      43864               144   0 Registry
    361      16     4632      11084              4824   0 RtkAudUService64
    249      10     2072       8640              9304   1 RtkAudUService64
    366      14     4720      11716       0,41  11900   1 RtkAudUService64
    511      28    11244      41440       2,22   5016   1 RuntimeBroker
    162      11     2248      11156       0,02   5644   1 RuntimeBroker
    964      41    17316      57992       5,42   8928   1 RuntimeBroker
    654      30    14004      38360       3,44  12976   1 RuntimeBroker
    128       8     1448       6448       0,03  16736   1 RuntimeBroker
    160       9     2196       9184       0,00  16808   1 RuntimeBroker
    370      16     4020      22820       0,41  17304   1 RuntimeBroker
    152       9     2180      10024       0,48  19008   1 RuntimeBroker
    597      24     6284      30144       0,84  19488   1 RuntimeBroker
    244      14     3028      17516       0,06  24044   1 RuntimeBroker
   1148      55    69504     147152       9,52  10236   1 SearchHost
    839      23    27696      40256              3532   0 SearchIndexer
      0       0      184      40612               108   0 Secure System
    544      22     7900      18172             12212   0 SecurityHealthService
    190      11     2092       9788       0,03  12192   1 SecurityHealthSystray
   1003      19     8004      15424              1064   0 services
     70       6      888       3608              4152   0 SessionService
   1186      46    62188      72104       3,28   4900   1 ShellExperienceHost
    843      23     7940      35892      11,80   6632   1 sihost
    176      11     2560      10912       0,00   4860   1 smartscreen
     58       4     1120       1088               564   0 smss
    349      18    13868      13504              4964   0 spacedeskService
    317      18     2736      18472       0,97   3580   1 spacedeskServiceTray
    525      28     9108      22564              3940   0 spoolsv
    993      47    87208     122476       6,77   4504   1 StartMenuExperienceHost
    846      69    78992      70644              4944   0 SurSvc
   1641      30    16268      34776              1220   0 svchost
   1713      23    12528      19316              1396   0 svchost
    254      15     3744      11804              1412   0 svchost
    326      13     3044       7832              1584   0 svchost
    202      16     6708      10208              1680   0 svchost
    111      10     1272       5052              1748   0 svchost
    177      38     8544      11768              1756   0 svchost
    124       8     1300       4908              1764   0 svchost
    233      23     2164       8308              1864   0 svchost
    247      21     3364      13344              1872   0 svchost
    320      26     3824      12492              1884   0 svchost
    459      15     3052      10504              1892   0 svchost
    151       9     1552       6688              1924   0 svchost
    312      10     2168       9476              2036   0 svchost
    264      14     3192       9616              2044   0 svchost
    276      12     3380       8420              2056   0 svchost
    643      14     3512       9420              2100   0 svchost
    128       8     1376       6432              2108   0 svchost
   1236      26     9940      19180              2136   0 svchost
    202      12     2604       9948              2152   0 svchost
    129      11     1604       5552              2184   0 svchost
    186      10     2060       7804              2216   0 svchost
    157      11     1860       8436              2280   0 svchost
    210      11     2188       7448              2304   0 svchost
    360      18     5788      11136              2412   0 svchost
    284      12     3176      11884              2424   0 svchost
    249      17     3248      12596              2472   0 svchost
    294       8     1388       5536              2556   0 svchost
    276      14     3788      15876              2560   0 svchost
    190      14     1972       8328              2700   0 svchost
    275      17     2868       9516              2708   0 svchost
    353      14     4096      13076              2836   0 svchost
    254      13     2732       8884              2864   0 svchost
    519      17    20508      20280              2984   0 svchost
    223      11     2060       8736              3088   0 svchost
    271      12     2396       8964              3172   0 svchost
    192      12     2120       8140              3180   0 svchost
    435      21     6756      15824              3328   0 svchost
    501      16     4240      15020              3616   0 svchost
    175      10     1616       6548              3652   0 svchost
    223      12     2372       9924              3788   0 svchost
    344      13    20732      23484              3796   0 svchost
    588      29     7664      21388              3868   0 svchost
    356      16     3748      13752              3892   0 svchost
    545      37    15564      25524              4000   0 svchost
    192      11     1952       7164              4040   0 svchost
    138       9     1560       7092              4220   0 svchost
    389      33     5256      15948              4292   0 svchost
    745      34    26484      38752              4308   0 svchost
    387      27    26572      31964              4320   0 svchost
    252       8     2172       6236              4344   0 svchost
    125       8     1468       5900              4368   0 svchost
    516      19     5908      17192              4532   0 svchost
    373      22     2868      10188              4564   0 svchost
    167      11     1740       7464              4584   0 svchost
    249      15     3152      11252              4620   0 svchost
    187      11     2072       7504              4916   0 svchost
    145       8     1424       5452              5064   0 svchost
    300      16     3780      18076       0,23   5092   1 svchost
    413      20     4752      18244              5132   0 svchost
    469      19    13548      22540              5160   0 svchost
    304      12     2308      12032              5572   0 svchost
    182      12     1708       6888              5828   0 svchost
    180      12     4036      12280              5960   0 svchost
    160      42     1772       6832              6208   0 svchost
    645      23     9668      35596      11,20   6460   1 svchost
    283      12     2716       8560              6552   0 svchost
    506      20    15308      30572       5,28   6624   1 svchost
    153      10     2144       8372       0,41   6696   1 svchost
    339      18     4840      18148              6796   0 svchost
    468      29     6524      22032              8184   0 svchost
    208      14     2448      10364              8532   0 svchost
    294      14     5148      18756              8664   0 svchost
    112       8     1288       5604       0,03   8900   1 svchost
    432      25     3684      12612              9548   0 svchost
    302      15     3808      21224       0,20   9832   1 svchost
    298      15     3700      19492       0,25   9896   1 svchost
    179      10     2012       8632       0,03  12016   1 svchost
    434      26     5724      21492       0,27  12056   1 svchost
    116       8     1368       5988             12260   0 svchost
    177      10     1824       7784             12304   0 svchost
    275      22     2888       8820             12372   0 svchost
    223      12     2816      12760             12948   0 svchost
    192     795     3836       7140             13116   0 svchost
    289      15     2748      11704             13444   0 svchost
    453      14     3552      14216             14612   0 svchost
    330      18     7968      19896             15676   0 svchost
    305      16     5128      15612             15704   0 svchost
    280      16     4028      14868             16236   0 svchost
    321      15     3304      13528             16452   0 svchost
    209      13     1844       7912             16988   0 svchost
    318      17     9640      21048             18100   0 svchost
    573      21     6592      19624             18396   0 svchost
    230      12     2804      13416       0,14  19232   1 svchost
    137      10     1600       7412             27532   0 svchost
   6254       0       52        152                 4   0 System
   1467      76   120280       1600       1,19  19976   1 SystemSettings
    614      27     7892      34024       0,63   9112   1 SystemSettingsBroker
    609      29    37868      48212       0,72  12440   1 TabTip
    340      40     9912      20300       2,66    680   1 taskhostw
    682      26    11592      27396       0,81  20524   1 taskhostw
   1006      40    45208      63392       2,97  17932   1 TextInputHost
    139       9     1700       7476              3952   1 unsecapp
    135       8     1404       7568             13008   0 unsecapp
    154      11     2228       9176       0,16  11784   1 UserOOBEBroker
    183      11     2572      11624             20996   0 vmcompute
   1264      64    74028      65784       2,08  16112   1 WhatsApp
    942      42    15036      58224       9,53   9176   1 Widgets
    348      20     5548      21340       1,36   9640   1 WidgetService
    873      38    65712     115952       0,91  18824   1 WindowsTerminal
    146      13     1512       5760              1000   0 wininit
    288      14     2676      10060               912   1 winlogon
    241      12     3452      11308              1632   0 wlanext
    403      23    27256      20008              6732   0 WmiPrvSE
    470      24     9724      26416             10584   0 WmiPrvSE
   1155      21    10148      20960             21796   0 WmiPrvSE
    468      22     5740      24332              5264   0 wslservice
    405      18    10160      18092              1276   0 WUDFHost
    296      10     2820       7492              1460   0 WUDFHost
    230       8     1620       5464              1524   0 WUDFHost
    268      12     1968       7020              3856   0 WUDFHost
    340      14     4200      12580             14852   0 WUDFHost
    962      37    52668      53372       1,03  21160   1 XboxGameBarSpotify
    817      49    49324      66060       0,84  18948   1 XboxIdp
    331      18     4768      19528       0,06  16232   1 XboxPcAppFT

```
 Trouver les 3 processus qui ont le plus petit identifiant

 ``` powershell
 PS C:\Users\arthu> Get-Process | Sort-Object Id | Select-Object -First 3

Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName
-------  ------    -----      -----     ------     --  -- -----------
      0       0       60          8                 0   0 Idle
   6488       0       52        152                 4   0 System
      0       0      184      40612               108   0 Secure System
 ```

 Lister tous les services de la machine...

 ```powershell
 PS C:\Users\arthu> Get-Service | Where-Object { $_.Status -eq 'Running' }

Status   Name               DisplayName
------   ----               -----------
Running  Appinfo            Informations d’application
Running  AudioEndpointBu... Générateur de points de terminaison...
Running  Audiosrv           Audio Windows
Running  BFE                Moteur de filtrage de base
Running  BluetoothUserSe... Service de support des utilisateurs...
Running  Bonjour Service    Service Bonjour
Running  BrokerInfrastru... Service d’infrastructure des tâches...
Running  BTAGService        Service de passerelle audio Bluetooth
Running  BthAvctpSvc        Service AVCTP
Running  bthserv            Service de prise en charge Bluetooth
Running  camsvc             Service Gestionnaire d’accès aux fo...
Running  cbdhsvc_1bcf56     Service utilisateur du Presse-papie...
Running  CDPSvc             Service de plateforme des appareils...
Running  CDPUserSvc_1bcf56  Service pour utilisateur de platefo...
Running  ClickToRunSvc      Microsoft Office Click-to-Run Service
Running  ClipSVC            Service de licences de client (Clip...
Running  CoreMessagingRe... CoreMessaging
Running  cplspcon           Intel(R) Content Protection HDCP Se...
Running  CryptSvc           Services de chiffrement
Running  DcomLaunch         Lanceur de processus serveur DCOM
Running  DeviceAssociati... Service d’association de périphérique
Running  DevicesFlowUser... Flux d’appareils_1bcf56
Running  Dhcp               Client DHCP
Running  DiagTrack          Expériences des utilisateurs connec...
Running  DispBrokerDeskt... Service de stratégie d'affichage
Running  DisplayEnhancem... Service d'amélioration de l'affichage
Running  Dnscache           Client DNS
Running  DoSvc              Optimisation de livraison
Running  DPS                Service de stratégie de diagnostic
Running  DSAService         Intel(R) Driver & Support Assistant
Running  DSAUpdateService   Intel(R) Driver & Support Assistant...
Running  DsSvc              Service de partage des données
Running  DusmSvc            Consommation des données
Running  EABackgroundSer... EABackgroundService
Running  EapHost            Protocole EAP (Extensible Authentic...
Running  EFS                Système de fichiers EFS (Encrypting...
Running  esifsvc            Intel(R) Dynamic Tuning service
Running  ESRV_SVC_QUEENC... Energy Server Service queencreek
Running  EventLog           Journal d’événements Windows
Running  EventSystem        Système d’événement COM+
Running  fdPHost            Hôte du fournisseur de découverte d...
Running  FDResPub           Publication des ressources de décou...
Running  FMAPOService       Fortemedia APO Control Service
Running  FontCache          Service de cache de police Windows
Running  FontCache3.0.0.0   Cache de police de Windows Presenta...
Running  FrameServer        Serveur de trame de la Caméra Windows
Running  gpsvc              Client de stratégie de groupe
Running  hidserv            Service du périphérique d’interface...
Running  hns                Service de réseau hôte
Running  HvHost             Service d'hôte HV
Running  igccservice        Intel(R) Graphics Command Center Se...
Running  igfxCUIService2... Intel(R) HD Graphics Control Panel ...
Running  InstallService     Installation du service Microsoft S...
Running  IntelArcControl... Intel(R) Arc Control Service
Running  InventorySvc       Service d’Appraisal inventaire et c...
Running  iphlpsvc           Assistance IP
Running  jhi_service        Intel(R) Dynamic Application Loader...
Running  KeyIso             Isolation de clé CNG
Running  LanmanServer       Serveur
Running  LanmanWorkstation  Station de travail
Running  LCD_Service        HONOR LCD_Service
Running  lfsvc              Service de géolocalisation
Running  LicenseManager     Serveur Gestionnaire de licences Wi...
Running  lmhosts            Assistance NetBIOS sur TCP/IP
Running  LMS                Intel(R) Management and Security Ap...
Running  LSM                Gestionnaire de session locale
Running  MBAMainService     HONOR PCManager Windows Service
Running  MDCoreSvc          Microsoft Defender Service de base
Running  mpssvc             Pare-feu Windows Defender
Running  NahimicService     Nahimic service
Running  NcbService         Service Broker pour les connexions ...
Running  NcdAutoSetup       Configuration automatique des périp...
Running  netprofm           Service Liste des réseaux
Running  NgcCtnrSvc         Conteneur Microsoft Passport
Running  NgcSvc             Microsoft Passport
Running  NPSMSvc_1bcf56     NPSMSvc_1bcf56
Running  nsi                Service Interface du magasin réseau
Running  nvagent            Service de virtualisation de réseau
Running  OneSyncSvc_1bcf56  Hôte de synchronisation_1bcf56
Running  OSDServer          OSD Service
Running  PcaSvc             Service de l’Assistant Compatibilit...
Running  PenService_1bcf56  PenService_1bcf56
Running  PhoneSvc           Service téléphonique
Running  PIEServiceNew      Intel® PROSet/Wireless Service
Running  PimIndexMainten... Données de contacts_1bcf56
Running  PlugPlay           Plug-and-Play
Running  PolicyAgent        Agent de stratégie IPsec
Running  Power              Alimentation
Running  ProfSvc            Service de profil utilisateur
Running  QWAVE              Expérience audio-vidéo haute qualit...
Running  RasMan             Gestionnaire des connexions d’accès...
Running  RmSvc              Service de gestion radio
Running  RpcEptMapper       Mappeur de point de terminaison RPC
Running  RpcSs              Appel de procédure distante (RPC)
Running  RtkAudioUnivers... Realtek Audio Universal Service
Running  SamSs              Gestionnaire de comptes de sécurité
Running  Schedule           Planificateur de tâches
Running  seclogon           Ouverture de session secondaire
Running  SecurityHealthS... Service Sécurité Windows
Running  SENS               Service de notification d’événement...
Running  SessionSvc         Session Detection
Running  SharedAccess       Partage de connexion Internet (ICS)
Running  ShellHWDetection   Détection matériel noyau
Running  spacedeskService   spacedeskService
Running  Spooler            Spouleur d’impression
Running  SSDPSRV            Découverte SSDP
Running  SstpSvc            Service SSTP (Secure Socket Tunneli...
Running  StateRepository    Service State Repository (StateRepo...
Running  StiSvc             Acquisition d’image Windows (WIA)
Running  StorSvc            Service de stockage
Running  SysMain            SysMain
Running  SystemEventsBroker Service Broker des événements système
Running  SystemUsageRepo... Intel(R) System Usage Report Servic...
Running  TextInputManage... Service de gestion des entrées de t...
Running  Themes             Thèmes
Running  TimeBrokerSvc      Service Broker pour les événements ...
Running  TokenBroker        Gestionnaire de comptes web
Running  TrkWks             Client de suivi de lien distribué
Running  UdkUserSvc_1bcf56  Service utilisateur du kit de dével...
Running  UnistoreSvc_1bcf56 Stockage des données utilisateur_1b...
Running  UserDataSvc_1bcf56 Accès aux données utilisateur_1bcf56
Running  UserManager        Gestionnaire des utilisateurs
Running  UsoSvc             Service Orchestrator pour les mises...
Running  VaultSvc           Gestionnaire d’informations d’ident...
Running  vmcompute          Service de calcul hôte Hyper-V
Running  W32Time            Temps Windows
Running  Wcmsvc             Gestionnaire des connexions Windows
Running  WdiSystemHost      Hôte système de diagnostics
Running  WdNisSvc           Service d’inspection réseau de l’an...
Running  webthreatdefuse... Service d’utilisateur Web Threat De...
Running  WFDSConMgrSvc      Service Wi-Fi Direct Service de ges...
Running  WinDefend          Service antivirus Microsoft Defender
Running  WinHttpAutoProx... Service de découverte automatique d...
Running  Winmgmt            Infrastructure de gestion Windows
Running  WlanSvc            Service de configuration automatiqu...
Running  WpnService         Service du système de notifications...
Running  WpnUserService_... Service utilisateur de notification...
Running  wscsvc             Centre de sécurité
Running  WSearch            Windows Search
Running  WSLService         WSL Service
Running  XblAuthManager     Gestionnaire d'authentification Xbo…
 ```
 
 ```powershell
 PS C:\Users\arthu> Get-Service | Where-Object { $_.Status -eq 'Stopped' }

Status   Name               DisplayName
------   ----               -----------
Stopped  AarSvc_1bcf56      Agent Activation Runtime_1bcf56
Stopped  AJRouter           Service de routeur AllJoyn
Stopped  ALG                Service de la passerelle de la couc...
Stopped  AppIDSvc           Identité de l’application
Stopped  AppReadiness       Préparation des applications
Stopped  autotimesvc        Heure cellulaire
Stopped  AxInstSV           Programme d’installation ActiveX (A...
Stopped  BcastDVRUserSer... Service utilisateur de diffusion et...
Stopped  BDESVC             Service de chiffrement de lecteur B...
Stopped  BITS               Service de transfert intelligent en...
Stopped  CaptureService_... CaptureService_1bcf56
Stopped  CertPropSvc        Propagation du certificat
Stopped  ClipSVC            Service de licences de client (Clip...
Stopped  CloudBackupRest... Service de restauration et de sauve...
Stopped  COMSysApp          Application système COM+
Stopped  ConsentUxUserSv... Service utilisateur ConsentUX_1bcf56
Stopped  CredentialEnrol... CredentialEnrollmentManagerUserSvc_...
Stopped  dcsvc              Service de configuration (DC) déclaré
Stopped  defragsvc          Optimiser les lecteurs
Stopped  DeviceAssociati... DeviceAssociationBroker_1bcf56
Stopped  DeviceInstall      Service d’installation de périphérique
Stopped  DevicePickerUse... DevicePicker_1bcf56
Stopped  DevQueryBroker     Service Broker de découverte en arr...
Stopped  diagnosticshub.... Service Collecteur standard du conc...
Stopped  diagsvc            Diagnostic Execution Service
Stopped  DmEnrollmentSvc    Service d'inscription de la gestion...
Stopped  dmwappushservice   Service de routage de messages Push...
Stopped  dot3svc            Configuration automatique de réseau...
Stopped  DsmSvc             Gestionnaire d’installation de péri...
Stopped  edgeupdate         Microsoft Edge Update Service (edge...
Stopped  edgeupdatem        Microsoft Edge Update Service (edge...
Stopped  embeddedmode       Mode incorporé
Stopped  EntAppSvc          Service de gestion des applications...
Stopped  EpicOnlineServices Epic Online Services
Stopped  Fax                Télécopie
Stopped  fhsvc              Service d’historique des fichiers
Stopped  FrameServerMonitor Moniteur de serveur de trame Caméra...
Stopped  GameInputSvc       GameInput Service
Stopped  GoogleChromeEle... Google Chrome Elevation Service (Go...
Stopped  GoogleUpdaterIn... Service interne de mise à jour Goog...
Stopped  GoogleUpdaterSe... Service de mise à jour Google (Goog...
Stopped  GraphicsPerfSvc    GraphicsPerfSvc
Stopped  icssvc             Service Point d'accès sans fil mobi...
Stopped  IKEEXT             Modules de génération de clés IKE e...
Stopped  Intel(R) Capabi... Intel(R) Capability Licensing Servi...
Stopped  Intel(R) SUR QC... Intel(R) SUR QC Software Asset Manager
Stopped  Intel(R) TPM Pr... Intel(R) TPM Provisioning Service
Stopped  InventorySvc       Service d’Appraisal inventaire et c...
Stopped  IpxlatCfgSvc       Service de configuration de convers...
Stopped  KtmRm              Service KtmRm pour Distributed Tran...
Stopped  lltdsvc            Mappage de découverte de topologie ...
Stopped  LxpSvc             Service d'expérience linguistique
Stopped  LxssManager        LxssManager
Stopped  MapsBroker         Gestionnaire des cartes téléchargées
Stopped  McpManagementSe... McpManagementService
Stopped  MessagingServic... MessagingService_1bcf56
Stopped  MicrosoftEdgeEl... Microsoft Edge Elevation Service (M...
Stopped  MixedRealityOpe... Service Windows Mixed Reality OpenXR
Stopped  MSDTC              Coordinateur de transactions distri...
Stopped  MSiSCSI            Service Initiateur iSCSI de Microsoft
Stopped  msiserver          Windows Installer
Stopped  NaturalAuthenti... Authentification naturelle
Stopped  NcaSvc             Assistant Connectivité réseau
Stopped  Netlogon           Netlogon
Stopped  Netman             Connexions réseau
Stopped  NetSetupSvc        Service Configuration du réseau
Stopped  NetTcpPortSharing  Service de partage de ports Net.Tcp
Stopped  NlaSvc             Connaissance des emplacements réseau
Stopped  p2pimsvc           Identity Manager réseau homologue
Stopped  p2psvc             Groupement de mise en réseau de pairs
Stopped  P9RdrService_1b... P9RdrService_1bcf56
Stopped  perceptionsimul... Service de simulation de perception...
Stopped  PerfHost           Hôte de DLL de compteur de performance
Stopped  pla                Journaux & alertes de performance
Stopped  PNRPAutoReg        Service de publication des noms d’o...
Stopped  PNRPsvc            Protocole PNRP
Stopped  PrintNotify        Extensions et notifications d’impri...
Stopped  PrintWorkflowUs... PrintWorkflow_1bcf56
Stopped  PushToInstall      Service PushToInstall de Windows
Stopped  RasAuto            Gestionnaire des connexions automat...
Stopped  RemoteAccess       Routage et accès distant
Stopped  RemoteRegistry     Registre à distance
Stopped  RetailDemo         Service de démo du magasin
Stopped  RpcLocator         Localisateur d’appels de procédure ...
Stopped  SCardSvr           Carte à puce
Stopped  ScDeviceEnum       Service d’énumération de périphériq...
Stopped  SCPolicySvc        Stratégie de retrait de la carte à ...
Stopped  SDRSVC             Sauvegarde Windows
Stopped  SEMgrSvc           Gestionnaires des paiements et des ...
Stopped  SensorDataService  Service Données de capteur
Stopped  SensorService      Service de capteur
Stopped  SensrSvc           Service de surveillance des capteurs
Stopped  SessionEnv         Configuration des services Bureau à...
Stopped  SgrmBroker         Service Broker du moniteur d'exécut...
Stopped  SharedRealitySvc   Service de données spatiales
Stopped  shpamsvc           Shared PC Account Manager
Stopped  smphost            SMP de l’Espace de stockages Microsoft
Stopped  SmsRouter          Service Routeur SMS Microsoft Windows.
Stopped  SNMPTrap           Interruption SNMP
Stopped  spectrum           Service de perception Windows
Stopped  sppsvc             Protection logicielle
Stopped  ssh-agent          OpenSSH Authentication Agent
Stopped  Steam Client Se... Steam Client Service
Stopped  svsvc              Vérificateur de points
Stopped  swprv              Fournisseur de cliché instantané de...
Stopped  TapiSrv            Téléphonie
Stopped  TermService        Services Bureau à distance
Stopped  TieringEngineSe... Gestion des niveaux de stockage
Stopped  TroubleshootingSvc Service de résolution des problèmes...
Stopped  TrustedInstaller   Programme d’installation pour les m...
Stopped  tzautoupdate       Programme de mise à jour automatiqu...
Stopped  uhssvc             Microsoft Update Health Service
Stopped  UmRdpService       Redirecteur de port du mode utilisa...
Stopped  upnphost           Hôte de périphérique UPnP
Stopped  USER_ESRV_SVC_Q... User Energy Server Service queencreek
Stopped  VacSvc             Service de composition audio volumé...
Stopped  VBoxSDS            VirtualBox system service
Stopped  vds                Disque virtuel
Stopped  vmicguestinterface Interface de services d’invité Hyper-V
Stopped  vmicheartbeat      Service Pulsation Microsoft Hyper-V
Stopped  vmickvpexchange    Service Échange de données Microsof...
Stopped  vmicrdv            Service de virtualisation Bureau à ...
Stopped  vmicshutdown       Service Arrêt de l’invité Microsoft...
Stopped  vmictimesync       Service Synchronisation date/heure ...
Stopped  vmicvmsession      Service Hyper-V PowerShell Direct
Stopped  vmicvss            Requête du service VSS Hyper-V
Stopped  VSInstallerElev... Visual Studio Installer Elevation S...
Stopped  VSS                Cliché instantané des volumes
Stopped  WaaSMedicSvc       WaaSMedicSvc
Stopped  WalletService      WalletService
Stopped  WarpJITSvc         Warp JIT Service
Stopped  wbengine           Service de moteur de sauvegarde en ...
Stopped  WbioSrvc           Service de biométrie Windows
Stopped  wcncsvc            Windows Connect Now - Registre de c...
Stopped  WdiServiceHost     Service hôte WDIServiceHost
Stopped  WebClient          WebClient
Stopped  webthreatdefsvc    Service Web Threat Defense
Stopped  Wecsvc             Collecteur d’événements de Windows
Stopped  WEPHOSTSVC         Service hôte du fournisseur de chif...
Stopped  wercplsupport      Prise en charge du Panneau de confi...
Stopped  WerSvc             Service de rapport d’erreurs Windows
Stopped  WiaRpc             Événements d’acquisition d’images f...
Stopped  WinRM              Gestion à distance de Windows (Gest...
Stopped  wisvc              Service Windows Insider
Stopped  wlidsvc            Assistant Connexion avec un compte ...
Stopped  wlpasvc            Service de l’Assistant de profil local
Stopped  WManSvc            Service de gestion de Windows
Stopped  wmiApSrv           Carte de performance WMI
Stopped  WMPNetworkSvc      Service de partage réseau du Lecteu...
Stopped  workfolderssvc     Dossiers de travail
Stopped  WpcMonSvc          Contrôle parental
Stopped  WPDBusEnum         Service Énumérateur d’appareil mobile
Stopped  WslInstaller       Sous-système Windows pour Linux
Stopped  wuauserv           Windows Update
Stopped  WwanSvc            Service de configuration automatiqu...
Stopped  XblGameSave        Jeu sauvegardé sur Xbox Live
Stopped  XboxGipSvc         Xbox Accessory Management Service
Stopped  XboxNetApiSvc      Service de mise en réseau Xbox Live

 ```

 ### 2. mémoire et CPU

  RAM
  
   ```powershell
  PS C:\Users\arthu> Get-CimInstance -ClassName Win32_ComputerSystem | Select-Object -Property TotalPhysicalMemory

TotalPhysicalMemory
-------------------
        16969424896
  ```

```powershell
PS C:\Users\arthu> Get-CimInstance -ClassName Win32_OperatingSystem | Select-Object -Property FreePhysicalMemory

FreePhysicalMemory
------------------
           7521196
```

CPU
```powershell
PS C:\Users\arthu> Get-CimInstance -ClassName Win32_PerfFormattedData_PerfOS_Processor | Where-Object {$_.Name -eq "_Total"} | Select-Object -Property PercentProcessorTime

PercentProcessorTime
--------------------
                   2
```

### 3.Stockage
 Périphériques

 ```powershell
 PS C:\Users\arthu> Get-CimInstance -ClassName Win32_DiskDrive | Select-Object -Property Model

Model
-----
WDC PC SN730 SDBPNTY-512G-1027
 ```

 je branche une clé USB

 ```powershell
 PS C:\Users\arthu> Get-CimInstance -ClassName Win32_DiskDrive | Select-Object -Property Model

Model
-----
WDC PC SN730 SDBPNTY-512G-1027
Philips USB Flash Drive USB Device
 ```
Partitions

```powershell
PS C:\Users\arthu> Get-Partition


   DiskPath : \\?\scsi#disk&ven_nvme&prod_wdc_pc_sn730_sdb#5&36e525db&0&000000#{53f56307-b6bf-11d0-94f2-00a0c91efb8b}

PartitionNumber  DriveLetter Offset                                                          Size Type
---------------  ----------- ------                                                          ---- ----
1                           1048576                                                       200 MB System
2                           210763776                                                      16 MB Reserved
3                C           227540992                                                     120 GB Basic
4                D           129076559872                                               337.23 GB Basic
5                           491171872768                                                  512 MB Recovery
6                           491708743680                                                   18 GB Recovery
7                           511036096512                                                    1 GB Recovery
```

Espace disque

```powershell
PS C:\Users\arthu> Get-Volume

DriveLetter FriendlyName FileSystemType DriveType HealthStatus OperationalStatus SizeRemaining      Size
----------- ------------ -------------- --------- ------------ ----------------- -------------      ----
D           Data         NTFS           Fixed     Healthy      OK                    255.49 GB 337.23 GB
            WINPE        FAT32          Fixed     Healthy      OK                    130.86 MB    508 MB
C           Windows      NTFS           Fixed     Healthy      OK                     13.71 GB    120 GB
            WinRE        NTFS           Fixed     Healthy      OK                    358.85 MB   1024 MB
            Onekey       NTFS           Fixed     Healthy      OK                      4.77 GB     18 GB
```
### 4. Réseau

Cartes réseau

```powershell
PS C:\Users\arthu> Get-NetAdapter

Name                      InterfaceDescription                    ifIndex Status       MacAddress             LinkSpeed
----                      --------------------                    ------- ------       ----------             ---------
Ethernet 2                VirtualBox Host-Only Ethernet Adapter        17 Up           0A-00-27-00-00-11         1 Gbps
Wi-Fi                     Intel(R) Wi-Fi 6 AX201 160MHz                13 Up           38-68-93-66-02-BF      57.8 Mbps
Connexion réseau Bluet... Bluetooth Device (Personal Area Netw...      12 Disconnected 38-68-93-66-02-C3         3 Mbps
```

Connexion réseau

```powershell
PS C:\Users\arthu> Get-NetTCPConnection -State Established

LocalAddress                        LocalPort RemoteAddress                       RemotePort State       AppliedSetting OwningProcess
------------                        --------- -------------                       ---------- -----       -------------- -------------
::1                                 49792     ::1                                 49787      Established Internet       13668
::1                                 49787     ::1                                 49792      Established Internet       2692
::1                                 49786     ::1                                 49773      Established Internet       2692
::1                                 49773     ::1                                 49786      Established Internet       13224
192.168.33.90                       60645     104.208.16.91                       443        Established Internet       26668
192.168.33.90                       60644     104.208.16.91                       443        Established Internet       26668
192.168.33.90                       60641     216.58.213.74                       443        Established Internet       26668
192.168.33.90                       60633     23.41.213.212                       443        Established Internet       26668
192.168.33.90                       60622     104.18.32.137                       443        Established Internet       26668
192.168.33.90                       60619     104.18.32.137                       443        Established Internet       26668
192.168.33.90                       60618     52.182.141.192                      443        Established Internet       24912
192.168.33.90                       60614     216.58.213.78                       443        Established Internet       26668
192.168.33.90                       60603     104.18.32.137                       443        Established Internet       26668
192.168.33.90                       60602     142.250.74.226                      443        Established Internet       26668
192.168.33.90                       60601     216.239.34.36                       443        Established Internet       26668
192.168.33.90                       60600     142.250.179.72                      443        Established Internet       26668
192.168.33.90                       60599     104.18.32.137                       443        Established Internet       26668
192.168.33.90                       60589     104.18.86.42                        443        Established Internet       26668
192.168.33.90                       60587     104.18.86.42                        443        Established Internet       26668
192.168.33.90                       60586     23.206.201.196                      443        Established Internet       26668
192.168.33.90                       60581     104.17.245.203                      443        Established Internet       26668
192.168.33.90                       60580     104.17.245.203                      443        Established Internet       26668
192.168.33.90                       60573     104.244.42.67                       443        Established Internet       26668
192.168.33.90                       60572     162.159.140.229                     443        Established Internet       26668
192.168.33.90                       60571     104.244.42.67                       443        Established Internet       26668
192.168.33.90                       60570     162.159.140.229                     443        Established Internet       26668
192.168.33.90                       60564     216.58.214.170                      443        Established Internet       26668
192.168.33.90                       60563     151.101.120.157                     443        Established Internet       26668
192.168.33.90                       60562     142.250.179.72                      443        Established Internet       26668
192.168.33.90                       60559     142.250.179.72                      443        Established Internet       26668
192.168.33.90                       60558     151.101.120.157                     443        Established Internet       26668
192.168.33.90                       60551     104.18.170.3                        443        Established Internet       26668
192.168.33.90                       60550     172.67.142.245                      443        Established Internet       26668
192.168.33.90                       60546     54.164.95.169                       443        Established Internet       26668
192.168.33.90                       60543     54.164.95.169                       443        Established Internet       26668
192.168.33.90                       60542     54.164.95.169                       443        Established Internet       26668
192.168.33.90                       60538     142.250.192.46                      443        Established Internet       26668
192.168.33.90                       60537     54.164.95.169                       443        Established Internet       26668
192.168.33.90                       60536     54.164.95.169                       443        Established Internet       26668
192.168.33.90                       60535     142.250.192.46                      443        Established Internet       26668
192.168.33.90                       60534     216.58.214.163                      443        Established Internet       26668
192.168.33.90                       60533     54.164.95.169                       443        Established Internet       26668
192.168.33.90                       60528     142.250.178.131                     443        Established Internet       26668
192.168.33.90                       60525     142.250.178.142                     443        Established Internet       26668
192.168.33.90                       60521     142.250.179.110                     443        Established Internet       26668
192.168.33.90                       60520     64.233.184.84                       443        Established Internet       26668
192.168.33.90                       60515     216.58.214.161                      443        Established Internet       26668
192.168.33.90                       60514     216.58.213.74                       443        Established Internet       26668
192.168.33.90                       60510     142.250.178.130                     443        Established Internet       26668
192.168.33.90                       60507     142.250.178.130                     443        Established Internet       26668
192.168.33.90                       60502     216.58.213.78                       443        Established Internet       26668
192.168.33.90                       60499     142.250.179.74                      443        Established Internet       26668
192.168.33.90                       60498     142.250.179.74                      443        Established Internet       26668
192.168.33.90                       60493     142.250.178.131                     443        Established Internet       26668
192.168.33.90                       60488     34.202.201.250                      443        Established Internet       26668
192.168.33.90                       60475     13.107.6.158                        443        Established Internet       24944
192.168.33.90                       60473     20.86.94.195                        443        Established Internet       24944
192.168.33.90                       60468     20.86.94.195                        443        Established Internet       24944
192.168.33.90                       60463     13.107.6.158                        443        Established Internet       24944
192.168.33.90                       60459     2.18.139.216                        443        Established Internet       13224
192.168.33.90                       60448     204.79.197.203                      443        Established Internet       9176
192.168.33.90                       60444     2.23.13.38                          443        Established Internet       9176
192.168.33.90                       60426     142.250.75.227                      443        Established Internet       26668
192.168.33.90                       60421     216.58.215.35                       443        Established Internet       26668
192.168.33.90                       60392     172.217.20.169                      443        Established Internet       26668
192.168.33.90                       60321     172.217.20.195                      443        Established Internet       26668
192.168.33.90                       60313     2.21.23.182                         443        Established Internet       26668
192.168.33.90                       60181     162.247.241.14                      443        Established Internet       14052
192.168.33.90                       59993     172.217.20.163                      443        Established Internet       26668
192.168.33.90                       59460     142.250.179.100                     443        Established Internet       26668
192.168.33.90                       59439     34.120.22.49                        443        Established Internet       26668
192.168.33.90                       59271     3.208.176.252                       9000       Established Internet       2692
192.168.33.90                       59025     52.5.133.239                        443        Established Internet       2692
192.168.33.90                       59001     50.16.105.34                        443        Established Internet       13224
192.168.33.90                       58764     50.17.106.94                        443        Established Internet       14052
192.168.33.90                       58608     54.209.178.35                       8095       Established Internet       14052
192.168.33.90                       58385     52.98.240.242                       443        Established Internet       1312
192.168.33.90                       57605     52.98.234.242                       443        Established Internet       10236
192.168.33.90                       57437     162.247.243.29                      443        Established Internet       14052
192.168.33.90                       56817     172.65.251.78                       443        Established Internet       26668
192.168.33.90                       56807     54.159.22.150                       443        Established Internet       26664
192.168.33.90                       56794     142.251.173.188                     5228       Established Internet       26668
192.168.33.90                       56793     20.250.77.142                       443        Established Internet       3840
192.168.33.90                       56780     162.159.133.234                     443        Established Internet       24352
192.168.33.90                       56767     20.199.120.151                      443        Established Internet       14308
192.168.33.90                       49429     20.199.120.151                      443        Established Internet       5132
192.168.33.90                       28252     192.168.33.168                      37966      Established Internet       4964

```

### 5.Utilisateurs

Lister les utilisateurs de la machine

```powershell
PS C:\Users\arthu> net user

comptes d’utilisateurs de \\LAPTOP-B7G8NR8E

-------------------------------------------------------------------------------
Administrateur           arthu                    DefaultAccount
Invité                   WDAGUtilityAccount
La commande s’est terminée correctement.

```

Heure de login
```powershell
PS C:\Users\arthu> (Get-WmiObject -Class Win32_LogonSession | Where-Object { $_.LogonType -eq 2 } | Sort-Object StartTime -Descending | Select-Object -First
 1).StartTime
20241029231702.752745+060

```

```powershell
PS C:\Users\arthu> Get-WmiObject -Class Win32_Process | ForEach-Object {
>>     $process = $_
>>     $owner = $process.GetOwner()
>>     [PSCustomObject]@{
>>         ProcessName = $process.Name
>>         ProcessID   = $process.ProcessId
>>         User        = "$($owner.Domain)\$($owner.User)"
>>     }
>> } | Format-Table -AutoSize

ProcessName                 ProcessID User
-----------                 --------- ----
System Idle Process                 0 \
System                              4 \
Secure System                     108 \
Registry                          144 \
smss.exe                          564 \
csrss.exe                         908 \
wininit.exe                      1000 \
csrss.exe                        1008 \
winlogon.exe                      912 \
services.exe                     1064 \
LsaIso.exe                       1088 \
lsass.exe                        1104 \
svchost.exe                      1220 \
fontdrvhost.exe                  1248 \
fontdrvhost.exe                  1256 \
WUDFHost.exe                     1276 \
svchost.exe                      1396 \
WUDFHost.exe                     1460 \
WUDFHost.exe                     1524 \
svchost.exe                      1584 \
dwm.exe                          1656 \
svchost.exe                      1748 \
svchost.exe                      1756 \
svchost.exe                      1764 \
svchost.exe                      1864 \
svchost.exe                      1872 \
svchost.exe                      1884 \
svchost.exe                      1892 \
svchost.exe                      2036 \
svchost.exe                      2044 \
svchost.exe                      2056 \
IntelCpHDCPSvc.exe               2084 \
svchost.exe                      2100 \
svchost.exe                      2136 \
svchost.exe                      2152 \
svchost.exe                      2184 \
svchost.exe                      2216 \
svchost.exe                      2280 \
svchost.exe                      2304 \
svchost.exe                      2412 \
svchost.exe                      2424 \
svchost.exe                      2560 \
svchost.exe                      2700 \
svchost.exe                      2864 \
igfxCUIServiceN.exe              2892 \
svchost.exe                      2984 \
svchost.exe                      2556 \
svchost.exe                      2472 \
svchost.exe                      2836 \
svchost.exe                      3088 \
svchost.exe                      3172 \
svchost.exe                      3180 \
Memory Compression               3252 \
svchost.exe                      3328 \
svchost.exe                      3616 \
svchost.exe                      3652 \
svchost.exe                      3788 \
svchost.exe                      3796 \
svchost.exe                      3868 \
svchost.exe                      3892 \
spoolsv.exe                      3940 \
svchost.exe                      4000 \
svchost.exe                      4040 \
svchost.exe                      4220 \
mDNSResponder.exe                4276 \
svchost.exe                      4292 \
svchost.exe                      4308 \
svchost.exe                      4320 \
OfficeClickToRun.exe             4328 \
DSAUpdateService.exe             4336 \
svchost.exe                      4344 \
DSAService.exe                   4356 \
svchost.exe                      4368 \
FMService64.exe                  4408 \
OneApp.IGCC.WinService.exe       4520 \
ArcControlService.exe            4536 \
svchost.exe                      4564 \
LCD_Service.exe                  4592 \
svchost.exe                      4620 \
PCManagerMainService.exe         4668 \
NahimicService.exe               4772 \
osdservice.exe                   4808 \
RtkAudUService64.exe             4824 \
esif_uf.exe                      4908 \
svchost.exe                      4916 \
SurSvc.exe                       4944 \
spacedeskService.exe             4964 \
svchost.exe                      5064 \
jhi_service.exe                  5084 \
SessionService.exe               4152 \
LMS.exe                          3996 \
svchost.exe                      5132 \
svchost.exe                      5160 \
wslservice.exe                   5264 \
svchost.exe                      5828 \
WmiPrvSE.exe                     6732 \
igfxextN.exe                     7152 \
svchost.exe                      5572 \
SearchIndexer.exe                3532 \
svchost.exe                      6796 \
svchost.exe                      4584 \
AggregatorHost.exe               3688 \
WUDFHost.exe                     3856 \
svchost.exe                      8184 \
svchost.exe                      4532 \
svchost.exe                      6552 \
svchost.exe                      8532 \
spacedeskServiceTray.exe         3580 LAPTOP-B7G8NR8E\arthu
MBAMessageCenter.exe             8492 \
MBAPersistentCenter.exe          7764 \
sihost.exe                       6632 LAPTOP-B7G8NR8E\arthu
svchost.exe                      6696 LAPTOP-B7G8NR8E\arthu
svchost.exe                      6624 LAPTOP-B7G8NR8E\arthu
DSATray.exe                      7540 LAPTOP-B7G8NR8E\arthu
svchost.exe                      8900 LAPTOP-B7G8NR8E\arthu
PresentationFontCache.exe        8960 \
svchost.exe                      6460 LAPTOP-B7G8NR8E\arthu
svchost.exe                      8664 \
taskhostw.exe                     680 LAPTOP-B7G8NR8E\arthu
igfxEMN.exe                      6532 LAPTOP-B7G8NR8E\arthu
explorer.exe                     1312 LAPTOP-B7G8NR8E\arthu
unsecapp.exe                     3952 \
RtkAudUService64.exe             9304 \
svchost.exe                      9896 LAPTOP-B7G8NR8E\arthu
SearchHost.exe                  10236 LAPTOP-B7G8NR8E\arthu
StartMenuExperienceHost.exe      4504 LAPTOP-B7G8NR8E\arthu
Widgets.exe                      9176 LAPTOP-B7G8NR8E\arthu
RuntimeBroker.exe                5016 LAPTOP-B7G8NR8E\arthu
RuntimeBroker.exe                8928 LAPTOP-B7G8NR8E\arthu
svchost.exe                      5092 LAPTOP-B7G8NR8E\arthu
WidgetService.exe                9640 LAPTOP-B7G8NR8E\arthu
dllhost.exe                     10468 LAPTOP-B7G8NR8E\arthu
UserOOBEBroker.exe              11784 LAPTOP-B7G8NR8E\arthu
SecurityHealthSystray.exe       12192 LAPTOP-B7G8NR8E\arthu
SecurityHealthService.exe       12212 \
svchost.exe                     12056 LAPTOP-B7G8NR8E\arthu
RtkAudUService64.exe            11900 LAPTOP-B7G8NR8E\arthu
ctfmon.exe                      11888 LAPTOP-B7G8NR8E\arthu
svchost.exe                     12372 \
svchost.exe                     12948 \
EABackgroundService.exe         13224 \
EADesktop.exe                    2692 LAPTOP-B7G8NR8E\arthu
EACefSubProcess.exe             13480 LAPTOP-B7G8NR8E\arthu
EALocalHostSvc.exe              13668 LAPTOP-B7G8NR8E\arthu
EACefSubProcess.exe             14040 LAPTOP-B7G8NR8E\arthu
EACefSubProcess.exe             14052 LAPTOP-B7G8NR8E\arthu
EACefSubProcess.exe             14172 LAPTOP-B7G8NR8E\arthu
EACefSubProcess.exe             14280 LAPTOP-B7G8NR8E\arthu
svchost.exe                     14612 \
WhatsApp.exe                    16112 LAPTOP-B7G8NR8E\arthu
IGCC.exe                        16176 LAPTOP-B7G8NR8E\arthu
RuntimeBroker.exe               16736 LAPTOP-B7G8NR8E\arthu
RuntimeBroker.exe               17304 LAPTOP-B7G8NR8E\arthu
svchost.exe                     15676 \
IGCCTray.exe                    17972 LAPTOP-B7G8NR8E\arthu
svchost.exe                     18396 \
svchost.exe                     16236 \
svchost.exe                     16988 \
svchost.exe                      1412 \
RuntimeBroker.exe               19008 LAPTOP-B7G8NR8E\arthu
svchost.exe                     19232 LAPTOP-B7G8NR8E\arthu
jusched.exe                     12388 LAPTOP-B7G8NR8E\arthu
ArcControl.exe                  18976 LAPTOP-B7G8NR8E\arthu
ArcControlAssist.exe            19480 LAPTOP-B7G8NR8E\arthu
ArcControlAssist.exe            19524 LAPTOP-B7G8NR8E\arthu
ArcControlAssist.exe            19556 LAPTOP-B7G8NR8E\arthu
svchost.exe                     13116 \
WUDFHost.exe                    14852 \
ArcControlAssist.exe             1216 LAPTOP-B7G8NR8E\arthu
ArcControlAssist.exe             9504 LAPTOP-B7G8NR8E\arthu
ArcControlAssist.exe            17036 LAPTOP-B7G8NR8E\arthu
TextInputHost.exe               17932 LAPTOP-B7G8NR8E\arthu
ApplicationFrameHost.exe         8712 LAPTOP-B7G8NR8E\arthu
svchost.exe                      6208 \
svchost.exe                      9832 LAPTOP-B7G8NR8E\arthu
svchost.exe                      9548 \
conhost.exe                     12656 \
esrv.exe                        16376 LAPTOP-B7G8NR8E\arthu
svchost.exe                     12016 LAPTOP-B7G8NR8E\arthu
svchost.exe                     16452 \
ShellExperienceHost.exe          4900 LAPTOP-B7G8NR8E\arthu
RuntimeBroker.exe               19488 LAPTOP-B7G8NR8E\arthu
jucheck.exe                      7344 LAPTOP-B7G8NR8E\arthu
svchost.exe                     12260 \
vmcompute.exe                   20996 \
msedgewebview2.exe               2244 LAPTOP-B7G8NR8E\arthu
msedgewebview2.exe                628 LAPTOP-B7G8NR8E\arthu
msedgewebview2.exe              14080 LAPTOP-B7G8NR8E\arthu
msedgewebview2.exe               6200 LAPTOP-B7G8NR8E\arthu
msedgewebview2.exe               4884 LAPTOP-B7G8NR8E\arthu
msedgewebview2.exe              14032 LAPTOP-B7G8NR8E\arthu
msedgewebview2.exe              26440 LAPTOP-B7G8NR8E\arthu
msedgewebview2.exe              26436 LAPTOP-B7G8NR8E\arthu
msedgewebview2.exe              24236 LAPTOP-B7G8NR8E\arthu
msedgewebview2.exe              26516 LAPTOP-B7G8NR8E\arthu
msedgewebview2.exe              12140 LAPTOP-B7G8NR8E\arthu
msedgewebview2.exe              27020 LAPTOP-B7G8NR8E\arthu
msedgewebview2.exe               7628 LAPTOP-B7G8NR8E\arthu
svchost.exe                     15704 \
XboxGameBarSpotify.exe          21160 LAPTOP-B7G8NR8E\arthu
XboxPcAppFT.exe                 16232 LAPTOP-B7G8NR8E\arthu
svchost.exe                      2108 \
dllhost.exe                     15992 LAPTOP-B7G8NR8E\arthu
taskhostw.exe                   20524 LAPTOP-B7G8NR8E\arthu
SystemSettingsBroker.exe         9112 LAPTOP-B7G8NR8E\arthu
EpicGamesLauncher.exe           26664 LAPTOP-B7G8NR8E\arthu
EpicWebHelper.exe               21012 LAPTOP-B7G8NR8E\arthu
EpicWebHelper.exe               16148 LAPTOP-B7G8NR8E\arthu
svchost.exe                      1680 \
svchost.exe                     13444 \
GameBarFTServer.exe              8224 LAPTOP-B7G8NR8E\arthu
msedgewebview2.exe              24400 LAPTOP-B7G8NR8E\arthu
XboxIdp.exe                     18948 LAPTOP-B7G8NR8E\arthu
RuntimeBroker.exe               16808 LAPTOP-B7G8NR8E\arthu
svchost.exe                     27532 \
svchost.exe                      2708 \
dasHost.exe                     18204 \
esrv_svc.exe                    11448 \
TabTip.exe                      12440 LAPTOP-B7G8NR8E\arthu
MpDefenderCoreService.exe       18704 \
MsMpEng.exe                      8460 \
NisSrv.exe                       2920 \
wlanext.exe                      1632 \
conhost.exe                     10048 \
Intel_PIE_Service.exe           10628 \
dllhost.exe                     11564 LAPTOP-B7G8NR8E\arthu
PhoneExperienceHost.exe         24944 LAPTOP-B7G8NR8E\arthu
backgroundTaskHost.exe          19080 LAPTOP-B7G8NR8E\arthu
RuntimeBroker.exe               24044 LAPTOP-B7G8NR8E\arthu
OneDrive.exe                    14308 LAPTOP-B7G8NR8E\arthu
Microsoft.SharePoint.exe        13648 LAPTOP-B7G8NR8E\arthu
FileCoAuth.exe                  16780 LAPTOP-B7G8NR8E\arthu
backgroundTaskHost.exe          20056 LAPTOP-B7G8NR8E\arthu
msedge.exe                      16004 LAPTOP-B7G8NR8E\arthu
msedge.exe                      14616 LAPTOP-B7G8NR8E\arthu
msedge.exe                       5844 LAPTOP-B7G8NR8E\arthu
msedge.exe                       3840 LAPTOP-B7G8NR8E\arthu
msedge.exe                      12232 LAPTOP-B7G8NR8E\arthu
Discord.exe                     24836 LAPTOP-B7G8NR8E\arthu
Discord.exe                     14948 LAPTOP-B7G8NR8E\arthu
Discord.exe                     14968 LAPTOP-B7G8NR8E\arthu
Discord.exe                     24352 LAPTOP-B7G8NR8E\arthu
Discord.exe                     26484 LAPTOP-B7G8NR8E\arthu
Discord.exe                     23688 LAPTOP-B7G8NR8E\arthu
chrome.exe                      10408 LAPTOP-B7G8NR8E\arthu
chrome.exe                      10792 LAPTOP-B7G8NR8E\arthu
chrome.exe                      10952 LAPTOP-B7G8NR8E\arthu
chrome.exe                      26668 LAPTOP-B7G8NR8E\arthu
chrome.exe                      24904 LAPTOP-B7G8NR8E\arthu
chrome.exe                       9840 LAPTOP-B7G8NR8E\arthu
chrome.exe                       6584 LAPTOP-B7G8NR8E\arthu
chrome.exe                      26000 LAPTOP-B7G8NR8E\arthu
chrome.exe                      10892 LAPTOP-B7G8NR8E\arthu
RuntimeBroker.exe                5644 LAPTOP-B7G8NR8E\arthu
svchost.exe                     23104 \
Notepad.exe                     23284 LAPTOP-B7G8NR8E\arthu
powershell.exe                  16528 LAPTOP-B7G8NR8E\arthu
conhost.exe                     18748 LAPTOP-B7G8NR8E\arthu
OpenConsole.exe                 18480 LAPTOP-B7G8NR8E\arthu
WindowsTerminal.exe              3040 LAPTOP-B7G8NR8E\arthu
chrome.exe                      25288 LAPTOP-B7G8NR8E\arthu
explorer.exe                    12808 LAPTOP-B7G8NR8E\arthu
chrome.exe                      24220 LAPTOP-B7G8NR8E\arthu
chrome.exe                      22572 LAPTOP-B7G8NR8E\arthu
LockApp.exe                     19868 LAPTOP-B7G8NR8E\arthu
RuntimeBroker.exe               25324 LAPTOP-B7G8NR8E\arthu
unsecapp.exe                    18348 \
chrome.exe                      26992 LAPTOP-B7G8NR8E\arthu
chrome.exe                      21836 LAPTOP-B7G8NR8E\arthu
chrome.exe                       9172 LAPTOP-B7G8NR8E\arthu
chrome.exe                      19888 LAPTOP-B7G8NR8E\arthu
chrome.exe                      11720 LAPTOP-B7G8NR8E\arthu
chrome.exe                      24644 LAPTOP-B7G8NR8E\arthu
chrome.exe                      21152 LAPTOP-B7G8NR8E\arthu
svchost.exe                       888 \
WmiPrvSE.exe                    19212 \
chrome.exe                       2116 LAPTOP-B7G8NR8E\arthu
chrome.exe                      12156 LAPTOP-B7G8NR8E\arthu
chrome.exe                      23096 LAPTOP-B7G8NR8E\arthu
Exception lors de l'appel de « GetOwner » : « Non trouvé  »
Au caractère Ligne:3 : 5
+     $owner = $process.GetOwner()
+     ~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : WMIMethodException

backgroundTaskHost.exe          14512 LAPTOP-B7G8NR8E\arthu
Exception lors de l'appel de « GetOwner » : « Non trouvé  »
Au caractère Ligne:3 : 5
+     $owner = $process.GetOwner()
+     ~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : WMIMethodException

RuntimeBroker.exe               11528 LAPTOP-B7G8NR8E\arthu
svchost.exe                      8128 \
svchost.exe                     20180 \
svchost.exe                     16668 \
WmiPrvSE.exe                    17440 \

```
