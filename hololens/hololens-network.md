---
title: HoloLens mit einem Netzwerk verbinden
description: Hier erhalten Sie Informationen dazu, wie Sie HoloLens einrichten, eine Verbindung mit dem Internet herstellen, und die IP-Adresse des Geräts identifizieren.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, WLAN, drahtlos, Internet, IP, IP-Adresse
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: f1968afe7d450425776bac24532f2d84c4dc3c62
ms.sourcegitcommit: 9f79ed9f76b930b8ceb97844d5f9eace9316b8a3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442591"
---
# <a name="connect-hololens-to-a-network"></a>HoloLens mit einem Netzwerk verbinden

Für die Durchführung der meisten Aufgaben auf Ihrer HoloLens müssen Sie mit einem Netzwerk verbunden sein. HoloLens enthält ein 802.11ac-fähiges, 2x2 WLAN-Funk. Das Herstellen einer Verbindung mit einem Netzwerk ähnelt dem Verbinden eines Windows 10-Desktop- oder mobilen Geräts mit einem WLAN-Netzwerk. Dieses Handbuch hilft Ihnen bei Folgendem:

- Herstellen einer Verbindung mit einem Netzwerk über WLAN oder (nur für HoloLens 2) Ethernet über USB-C
- Deaktivieren und erneutes Aktivieren von WLAN

Weitere Informationen finden Sie unter [Verwenden von HoloLens Offline](hololens-offline.md).

## <a name="connecting-for-the-first-time"></a>Erstmaliges Herstellen einer Verbindung

Bei der ersten Verwendung von HoloLens werden Sie beim Herstellen einer Verbindung mit einem WLAN-Netzwerk angeleitet. Wenn beim Einrichten Probleme beim Herstellen einer Verbindung zu WLAN auftreten, stellen Sie sicher, dass es sich um ein offenes, kennwortgeschütztes Netzwerk oder ein Captive-Portalnetzwerk handelt. Stellen Sie sicher, dass für das Netzwerk kein Zertifikat zum Herstellen einer Verbindung benötigt wird. Nach dem Einrichten können Sie eine Verbindung zu anderen Arten von WLAN-Netzwerken herstellen.

Auf HoloLens 2-Geräten kann ein Benutzer auch über einen [USB-C-zu-Ethernet-Adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) eine direkte Verbindung zu WLAN herstellen, um die Einrichtung des Geräts zu unterstützen. Sobald das Gerät eingerichtet wurde, kann ein Benutzer den Adapter entweder weiter verwenden oder das Gerät vom Adapter trennen und [nach dem Einrichten eine Verbindung zum WLAN herstellen](hololens-network.md#connecting-to-wi-fi-after-setup). 

## <a name="connecting-to-wi-fi-after-setup"></a>Herstellen einer Verbindung zum WLAN nach dem Einrichten

1. Führen Sie die **Startgeste** aus, und wählen Sie **Einstellungen** aus. Die Einstellungs-App wird automatisch vor Ihnen platziert.
1. Wählen Sie **Netzwerk und Internet** > **WLAN** aus. Stellen Sie sicher, dass WLAN aktiviert ist. Wenn Ihr Netzwerk nicht angezeigt wird, scrollen Sie die Liste nach unten.
1. Wählen Sie ein Netzwerk und dann **Verbinden** aus.
1. Wenn Sie zur Eingabe eines Netzwerkkennworts aufgefordert werden, geben Sie es ein, und wählen Sie dann **Weiter** aus.

![WLAN-Einstellungen für HoloLens](./images/hololens-2-wifi-settings.jpg)

Um zu bestätigen, dass Sie mit einem WLAN verbunden sind, überprüfen Sie den WLAN-Status im **Startmenü** :

1. Öffnen Sie das **Startmenü**.
1. Suchen Sie oben links im **Startmenü** nach dem WLAN-Status. Der Status von WLAN und die SSID des verbundenen Netzwerks werden angezeigt.

> [!TIP]
> Wenn kein WLAN verfügbar ist, können Sie sich auch mit [Mobilen- und 5G-Netzwerken verbinden](https://docs.microsoft.com/hololens/hololens-cellular).

> [!IMPORTANT]
> Standardmäßig können Benutzer das WLAN-Roamingverhalten der HoloLens 2 nicht optimieren – **die einzige Möglichkeit zum Aktualisieren der WLAN-Liste besteht im Ein- und Ausschalten des WLANs**. Dadurch werden viele Probleme verhindert, z. B. wenn ein Gerät bei einem Zugriffspunkt „hängenbleibt“, sobald dieser außer Reichweite ist.

## <a name="troubleshooting-your-connection-to-wi-fi"></a>Behandeln von Problemen mit Ihrer WLAN-Verbindung

Wenn Sie Probleme beim Herstellen einer WLAN-Verbindung haben, lesen Sie [Ich kann keine WLAN-Verbindung herstellen](./hololens-faq.md#i-cant-connect-to-wi-fi).

Melden Sie sich mit dem Gerät bei einem Unternehmens- oder Organisationskonto an, kann auch die Richtlinie für die mobile Geräteverwaltung (Mobile Device Management, MDM) gelten, wenn die Richtlinie von Ihrem IT-Administrator konfiguriert wurde.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>HoloLens mit Enterprise WLAN-Netzwerk verbinden

Enterprise WLAN-Profile verwenden das Extensible Authentication Protocol (EAP) zur Authentifizierung von WLAN-Verbindungen. Das HoloLens Enterprise WLAN-Profil kann über MDM oder ein mit [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) erstelltes Bereitstellungspaket konfiguriert werden.

Konfigurationsanweisungen für das von Microsoft Intune verwaltete Gerät finden Sie unter [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile).

Um ein WLAN-Bereitstellungspaket in WCD zu erstellen, ist eine vorkonfigurierte WLAN-Profil-XML-Datei erforderlich. Hier ist ein Beispiel für ein WLAN-Profil für WPA2-Enterprise mit EAP-TLS-Authentifizierung:

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


Je nach EAP-Typ müssen möglicherweise das Server-Root-CA-Zertifikat und das Client-Zertifikat auf dem Gerät bereitgestellt werden.

Weitere Ressourcen:

- WLANv1Profil-Schema: [[MS-GPWL]: Schema des WLAN-Profils v1 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS-Schema: [[MS-GPWL]: Microsoft EAP TLS-Schema | Microsoft Docs ](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

### <a name="eap-troubleshooting"></a>EAP-Problembehandlung

1. Überprüfen Sie noch einmal, ob das WLAN-Profil die richtigen Einstellungen hat:
   1. EAP-Typ ist ordnungsgemäß konfiguriert, allgemeine EAP-Typen: EAP-TLS (13), EAP-TTLS (21) und PEAP (25).
   1. Der WLAN-SSID-Name ist richtig und stimmt mit der HEX-Zeichenfolge überein.
   1. Für EAP-TLS enthält TrustedRootCA den SHA-1-Hash des Zertifikats der vertrauenswürdigen Stammzertifizierungsstelle von Server&#39;. Auf Windows-PC zeigt der Befehl &quot;certutil.exe -dump cert\_file\_name&quot; eine SHA-1-Hash-Zeichenfolge des Zertifikats&#39;s SHA-1.
1. Sammeln Sie die Erfassung von Netzwerkpaketen auf den Protokollen des Access Points oder des Controllers oder des AAA-Servers, um herauszufinden, wo die EAP-Sitzung fehlschlägt.
   1. Wenn die von HoloLens bereitgestellte EAP-Identität nicht erwartet wird, prüfen Sie, ob die Identität über das WLAN-Profil oder das Client-Zertifikat korrekt bereitgestellt wurde.
   1. Wenn der Server das HoloLens-Client-Zertifikat ablehnt, prüfen Sie, ob das erforderliche Client-Zertifikat auf dem Gerät bereitgestellt wurde.
   1. Wenn HoloLens das Server-Zertifikat ablehnt, prüfen Sie, ob das Root-CA-Zertifikat des Servers auf HoloLens bereitgestellt wurde.
1. Wenn das Enterprise-Profil über ein WLAN-Bereitstellungspaket bereitgestellt wird, wenden Sie das Bereitstellungspaket auf einem Windows 10-PC an. Wenn es auch auf einem Windows 10 PC fehlschlägt, befolgen Sie die [Anleitung zur Problembehandlung bei der Windows-Client 802.1X-Authentifizierung](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).
1. Senden Sie uns Feedback über den [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).

### <a name="additional-resources"></a>Weitere Ressourcen:
- [WLAN-Einstellungen von einem Windows-Gerät exportieren](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="vpn"></a>VPN
Eine VPN-Verbindung kann Ihnen dabei helfen, eine sicherere Verbindung herzustellen sowie auf das Netzwerk Ihres Unternehmens und das Internet zuzugreifen. HoloLens 2 unterstützt den integrierten VPN-Client und das VPN-Plug-In Universelle Windows-Plattform (UWP). 

Unterstützte integrierte VPN-Protokolle:
- IKEv2
- L2TP
- PPTP

Wenn für die Authentifizierung des integrierten VPN-Clients ein Zertifikat verwendet wird, muss das erforderliche Clientzertifikat zum Benutzerzertifikatspeicher hinzugefügt werden. Wenn Sie herausfinden möchten, ob das VPN-Plug-In eines Drittanbieters HoloLens 2 unterstützt, wechseln Sie zu „Speicher“, um die VPN-App zu suchen, und überprüfen Sie, ob HoloLens als unterstütztes Gerät aufgeführt ist und ob die App auf der Seite „Systemanforderungen“ die ARM- oder ARM64-Architektur unterstützt. HoloLens unterstützt nur Universelle Windows-Plattform-Anwendungen für VPN von Drittanbietern.

 VPN kann durch MDM über [Einstellungen/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) verwaltet und über die Richtlinie [Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp) festgelegt werden.

Weitere Informationen zum [Konfigurieren von VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) finden Sie in [diesen Handbüchern](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).  

### <a name="vpn-via-ui"></a>VPN über die Benutzeroberfläche

VPN ist standardmäßig nicht aktiviert, kann aber durch Öffnen der App **Einstellungen** und Navigieren zu **„Netzwerk und Internet“ –> „VPN“** manuell aktiviert werden.
1. Wählen Sie einen VPN-Anbieter aus.
1. Erstellen Sie einen Verbindungsnamen. 
1. Geben Sie Ihren Servernamen oder Ihre Adresse ein.
1. Wählen Sie den VPN-Typ aus.
1. Wählen Sie die Anmeldeinformationen aus. 
1. Fügen Sie optional Benutzername und Kennwort hinzu.
1. Wenden Sie die VPN-Einstellungen an. 

![HoloLens VPN-Einstellungen](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>VPN über Bereitstellungspaket einstellen

> [!TIP] 
> In der Windows Holographic Version 20H2 haben wir ein Problem mit der Proxy-Konfiguration für die VPN-Verbindung behoben. Wenn Sie diesen Datenstrom verwenden möchten, aktualisieren Sie Geräte auf diesen Build.

1. Starten Sie den Windows Configuration Designer.
1. Klicken Sie auf **HoloLens-Geräte bereitstellen** und wählen Sie dann das Zielgerät aus und klicken dann auf **Weiter**.
1. Geben Sie Paketname und Pfad ein.
1. Klicken Sie auf **Zum erweiterten Editor wechseln**.
1. Öffnen Sie die **Laufzeiteinstellungen**  -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.
1. VPNProfileName konfigurieren
1. Profiltyp auswählen: **Nativ ** oder **Drittanbieter**.
    1. Wählen Sie unter Natives Profil die Option **NativeProtocolType** und konfigurieren Sie dann Server, Routing-Richtlinie, Authentifizierungstyp und andere Einstellungen.
    1. Konfigurieren Sie für Drittanbieter-Profile Server-URL, VPN-Plug-in-App-Paket Familienname (nur 3 vordefiniert) und benutzerdefinierte Konfigurationen.
1. Exportieren Sie Ihr Paket.
1. Schließen Sie HoloLens an und kopieren Sie die .ppkg-Datei auf das Gerät. 
1. Um auf HoloLens das VPN.ppkg anzuwenden, öffnen Sie im Startmenü **Einstellungen** -> ** Konto** -> **Zugriff Arbeit oder Schule** -> **Bereitstellungspaket hinzufügen oder entfernen** -> Wählen Sie Ihr VPN-Paket aus.


### <a name="setting-up-vpn-via-intune"></a>VPN über Intune einrichten
Folgen Sie zunächst der Intune-Anleitung. Beachten Sie bei der Durchführung dieser Schritte die eingebauten VPN-Protokolle, die HoloLens-Geräte unterstützen. 

[VPN-Profile zur Verbindung mit VPN-Servern in Intune erstellen](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).

[Windows 10 und Windows Holographic-Geräteeinstellungen zum Hinzufügen von VPN-Verbindungen mit Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).

Wenn Sie fertig sind, denken Sie daran, [das Profil zuzuweisen](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).

### <a name="vpn-via-3rd-party-mdm-solutions"></a>VPN über die MDM-Lösungen von Drittanbietern
Beispiel für eine VPN-Verbindung von Drittanbietern:
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

Natives IKEv2-VPN-Beispiel:
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>WLAN auf HoloLens (1. Generation) deaktivieren

### <a name="using-the-settings-app-on-hololens"></a>Verwenden der Einstellungs-App auf HoloLens

1. Öffnen Sie das **Startmenü**.
1. Wählen Sie die **Einstellungs**-App im **Startmenü** oder in der Liste **Alle Apps** auf der rechten Seite des **Startmenüs** aus. Die **Einstellungs**-App wird automatisch vor Ihnen platziert.
1. Wählen Sie **Netzwerk und Internet** aus.
1. Wählen Sie den WLAN-Schieberegler aus, um ihn in die Position **Off** (Aus) zu verschieben. Dadurch werden die HF-Komponenten des WLAN-Funkanschlusses ausgeschaltet und alle WLAN-Funktionen von HoloLens deaktiviert.

    > [!WARNING]
    > Wenn der WLAN-Funkanschluss deaktiviert ist, kann HoloLens Ihre [Räume](hololens-spaces.md) nicht automatisch laden.

1. Schieben Sie den Schieberegler in die Stellung **On** (Ein), um das WLAN zu aktivieren und die WLAN-Funktion auf Microsoft HoloLens wiederherzustellen. Der ausgewählte WLAN-Funkstatus (**Ein** oder **Aus**) bleibt bei einem Neustart erhalten.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Identifizieren der IP-Adresse Ihrer HoloLens im WLAN-Netzwerk

### <a name="by-using-the-settings-app"></a>Mithilfe der Einstellungs-App

1. Öffnen Sie das **Startmenü**.
1. Wählen Sie die **Einstellungs**-App im **Startmenü** oder in der Liste **Alle Apps** auf der rechten Seite des **Startmenüs** aus. Die **Einstellungs**-App wird automatisch vor Ihnen platziert.
1. Wählen Sie **Netzwerk und Internet** aus.
1. Scrollen Sie nach unten unter die Liste der verfügbaren WLAN-Netzwerke und wählen Sie **Hardwareeigenschaften** aus.

    ![Hardwareeigenschaften in WLAN-Einstellungen](./images/wifi-hololens-hwdetails.jpg)

   Die IP-Adresse wird neben **IPv4-Adresse** angezeigt.

### <a name="by-using-voice-commands"></a>Mithilfe von Sprachbefehlen

Je nach dem Build Ihres Geräts können Sie entweder mithilfe von integrierten Sprachbefehlen oder Cortana Ihre IP-Adresse anzeigen. Sprechen Sie bei Builds nach [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) „Wie lautet meine IP-Adresse?“ Dann wird sie angezeigt. Sagen Sie bei früheren Builds oder HoloLens (1. Generation)„Hey Cortana, wie lautet meine IP-Adresse?”. und Cortana wird Ihre IP-Adresse anzeigen und vorlesen.

### <a name="by-using-windows-device-portal"></a>Mithilfe des Windows-Geräteportals

1. Öffnen Sie in einem Webbrowser auf Ihrem PC das [Geräteportal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Navigieren Sie zum Abschnitt **Netzwerk**.  
   In diesem Abschnitt werden Ihre IP-Adresse und andere Netzwerkinformationen angezeigt. Mithilfe dieser Methode können Sie die IP-Adresse auf Ihren Entwicklungscomputer kopieren und einfügen.
