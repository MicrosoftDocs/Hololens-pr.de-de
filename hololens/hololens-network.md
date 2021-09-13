---
title: Verbinden von HoloLens mit einem Netzwerk
description: Hier erhalten Sie Informationen dazu, wie Sie HoloLens einrichten, eine Verbindung mit dem Internet herstellen, und die IP-Adresse des Geräts identifizieren.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, WLAN, kabellos, Internet, IP, IP-Adresse
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: fe1c47de48e413a6f45921ba1e247016873ca996
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034393"
---
# <a name="connect-hololens-to-a-network"></a>Verbinden von HoloLens mit einem Netzwerk

Für die Durchführung der meisten Aufgaben auf Ihrer HoloLens müssen Sie mit einem Netzwerk verbunden sein. HoloLens enthält ein 802.11ac-fähigen, 2x2 WLAN-Funk. Das Herstellen einer Verbindung mit einem Netzwerk ähnelt dem Verbinden eines Windows 10-Desktop- oder mobilen Geräts mit einem WLAN-Netzwerk. Dieses Handbuch wird Ihnen helfen:

- Herstellen einer Verbindung mit einem Netzwerk über WLAN oder nur für HoloLens 2, Wi-Fi Direkt oder Ethernet über USB-C
- Deaktivieren und erneutes Aktivieren von WLAN

Erfahren Sie mehr über die [Offline-Verwendung der HoloLens](hololens-offline.md).

## <a name="connecting-for-the-first-time"></a>Erstmaliges Herstellen einer Verbindung

Bei der ersten Verwendung von HoloLens werden Sie beim Herstellen einer Verbindung mit einem WLAN-Netzwerk angeleitet. Wenn während des Einrichtens Probleme beim Herstellen einer WLAN-Verbindung auftreten, stellen Sie sicher, dass es sich entweder um ein offenes, kennwortgeschütztes Netzwerk oder um ein Captive-Portalnetzwerk handelt. Stellen Sie außerdem sicher, dass für das Netzwerk kein Zertifikat zum Herstellen einer Verbindung benötigt wird. Nach dem Einrichten können Sie eine Verbindung zu anderen Arten von WLAN-Netzwerken herstellen.

Auf HoloLens 2 Geräten kann ein Benutzer auch einen [USB-C-zu-Ethernet-Adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) verwenden, um eine direkte Verbindung mit WLAN herzustellen, um die Einrichtung des Geräts zu unterstützen. Sobald das Gerät eingerichtet wurde, kann ein Benutzer den Adapter entweder weiter verwenden oder das Gerät vom Adapter trennen und [nach der Einrichtung mit dem WLAN verbinden](hololens-network.md#connecting-to-wi-fi-after-setup). 

## <a name="connecting-to-wi-fi-after-setup"></a>Herstellen einer Verbindung zum WLAN nach dem Einrichten

1. Führen Sie die **Startgeste** aus und wählen Sie **Einstellungen**. Die Einstellungen-App wird automatisch vor Ihnen platziert.
1. Wählen Sie **Netzwerk & Internet** > **WLAN** aus. Stellen Sie sicher, dass WLAN aktiviert ist. Wenn Ihr Netzwerk nicht angezeigt wird, scrollen Sie in der Liste nach unten.
1. Wählen Sie ein Netzwerk und dann **Verbinden** aus.
1. Wenn Sie zur Eingabe eines Netzwerkkennworts aufgefordert werden, geben Sie es ein, und wählen Sie dann **Weiter** aus.

![WLAN-Einstellungen für HoloLens.](./images/hololens-2-wifi-settings.jpg)

Um zu bestätigen, dass Sie mit einem WLAN verbunden sind, überprüfen Sie den WLAN-Status im **Startmenü**:

1. Öffnen Sie das Menü **Start**.
1. Suchen Sie oben links im **Startmenü** nach dem WLAN-Status. Der Status von WLAN und die SSID des verbundenen Netzwerks werden angezeigt.

> [!TIP]
> Wenn Wi-Fi nicht verfügbar ist, können Sie auch eine [Verbindung mit Mobilfunk- und 5G-Netzwerken](hololens-cellular.md) herstellen.

> [!IMPORTANT]
> Die Benutzer können das WLAN-Roaming-Verhalten des HoloLens 2 absichtlich nicht optimieren.  **Die einzige Möglichkeit zum Aktualisieren der WLAN-Liste besteht im An- und Ausschalten des WLANs**. Dadurch werden viele Probleme verhindert, z. B. wenn ein Gerät bei einem Zugriffspunkt „hängenbleibt“, sobald dieser außer Reichweite ist.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>Verbinden von HoloLens mit einem Enterprise WLAN-Netzwerk

WLAN-Profile von Unternehmen verwenden das Extensible Authentication Protocol (EAP) zur Authentifizierung von WLAN-Verbindungen. Das HoloLens Enterprise WLAN-Profil kann über MDM oder mit einem Bereitstellungspaket das von [Windows Konfigurationsdesigner](/windows/configuration/provisioning-packages/provisioning-packages) erstellt wurde konfiguriert werden.

Konfigurationsanweisungen für das von Microsoft Intune verwaltete Gerät finden Sie unter [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile).

Um ein WLAN-Bereitstellungspaket in WCD zu erstellen, ist eine vorkonfigurierte WLAN-Profil.XML-Datei erforderlich. Hier ist ein Beispiel für ein WLAN-Profil für ein Unternehmens-WPA2 mit EAP-TLS-Authentifizierung:

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

Zusätzliche Ressourcen:

- WLANv1Profile Schema: [[MS-GPWL]: Kabellose LAN Profile v1 Schema | Microsoft-Dokumentation](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS-Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft-Dokumentation](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

Lesen Sie unsere Seite [Problembehandlung](hololens2-enterprise-troubleshooting.md#), wenn Beim Herstellen einer Verbindung mit Ihrem WLAN Probleme auftreten.

## <a name="configure-network-proxy"></a>Konfigurieren des Netzwerkproxys

In diesem Abschnitt wird der Netzwerkproxy für das HoloLens-Betriebssystem und UWP-Apps (Universelle Windows-Plattform) mit Windows HTTP-Stapel behandelt. Anwendungen, die nicht Windows HTTP-Stapel verwenden, verfügen möglicherweise über eine eigene Proxykonfiguration und -verarbeitung. 

### <a name="proxy-configurations"></a>Proxykonfigurationen 

- Proxy Autokonfigurationsskript (PAC): Eine [PAC-Datei](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (öffnet eine Nicht-Microsoft-Website) enthält eine JavaScript-Funktion FindProxyForURL(url, host). 
- Statischer Proxy: in Form von Server:Port.  
- WebProxy Auto-Discovery Protocol (WPAD): Geben Sie die URL der Proxykonfigurationsdatei über DHCP oder DNS an. 

### <a name="proxy-provisioning-methods"></a>Bereitstellungsmethoden für Proxys 
Es gibt drei Möglichkeiten zum Bereitstellen von Proxys:

 

1.  **Benutzeroberfläche „Einstellungen“:** 
    1. Proxy pro Benutzer (20H2 oder früher):
        1. Öffnen Sie das Startmenü und wählen Sie „Einstellungen“ aus.
        2. Wählen Sie „Netzwerk & Internet“ und dann „Proxy“ aus dem linken Menü.
        3. Scrollen Sie nach unten zu „Manuelle Proxyeinrichtung“, und klicken Sie bei „Proxyserver verwenden“ auf „Ein“.
        4. Geben Sie die IP-Adresse des Proxyservers ein.
        5. Geben Sie die Portnummer ein.
        6. Klicken Sie auf Speichern.
      1. WLAN-Proxy (21H1 oder höher):
          1. Öffnen Sie das Startmenü, und wechseln Sie zur Seite der WLAN-Eigenschaften Ihres Netzwerks.
          1. Scrollen Sie nach unten zu Proxy
          1. Wechseln Sie zu Manuelles Setup
          1. Geben Sie die IP-Adresse des Proxyservers ein.
          1. Geben Sie die Portnummer ein.
          1. Klicken Sie auf „Übernehmen“.
        
 2. **MDM** 
     1. Intune: Verwenden Sie diese [Schritte](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile), um den Proxy in Intune zu konfigurieren. Sie müssen im Abschnitt nach unten scrollen.
     1. Andere MDM-Lösungen von Drittanbietern: Verwenden Sie einen [WLAN-CSP](/windows/client-management/mdm/wifi-csp).

3. **PPKG** 
    1. Öffnen Sie den Windows-Konfigurationsdesigner
    1. Klicken Sie auf Erweiterte Bereitstellung, geben Sie den Namen für Ihr neues Project ein und klicken Sie auf „Weiter“.
    1. Wählen Windows Holographic (HoloLens 2) aus, und klicken Sie auf „Weiter“.
    1. Importieren Sie Ihr PPKG (optional), und klicken Sie auf „Fertig stellen“.
    1. Erweitern Sie Laufzeiteinstellungen -> Verbindungsprofile -> WLAN -> WLAN-Proxy.
    1. Geben Sie die SSID Ihres WLAN-Netzwerks ein, und klicken Sie auf „Hinzufügen“.
    1. Wählen Sie Ihr WLAN-Netzwerk in dem linken Fenster aus, und geben Sie Ihre gewünschten Anpassungen ein. Die aktivierten Anpassungen werden im linken Menü in Fettschrift angezeigt.
    1. Klicken Sie auf „Speichern und Schließen“.
    1. [Anwenden](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) des Bereitstellungspakets auf HoloLens.

[CSPs](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) liegen vielen der Verwaltungsaufgaben und Richtlinien für Windows 10 in Microsoft Intune und Microsoft-fremden MDM-Dienstanbietern zugrunde. Sie können auch den [Windows-Konfigurationsdesigner](/windows/configuration/provisioning-packages/provisioning-install-icd) verwenden, um ein [Bereitstellungspaket](/windows/configuration/provisioning-packages/provisioning-packages) zu erstellen und es auf HoloLens 2 anwenden.
Die wahrscheinlichsten CSPs, die auf Ihre HoloLens 2 angewendet werden, sind:

- [WLAN-CSP](/windows/client-management/mdm/wifi-csp): Pro Profil WLAN-Proxy 

[Andere in HoloLens-Geräten unterstützte CSPs](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
Eine VPN-Verbindung kann Ihnen dabei helfen, eine sicherere Verbindung herzustellen sowie auf das Netzwerk Ihres Unternehmens und das Internet zuzugreifen. HoloLens 2 unterstützt den integrierten VPN-Client und das VPN-Plug-In Universelle Windows-Plattform (UWP). 

Unterstützt integrierte VPN-Protokolle:
- IKEv2
- L2TP
- PPTP

Wenn für die Authentifizierung des integrierten VPN-Clients ein Zertifikat verwendet wird, muss das erforderliche Clientzertifikat zum Benutzerzertifikatspeicher hinzugefügt werden. Wenn Sie herausfinden möchten, ob das VPN-Plug-In eines Drittanbieters HoloLens 2 unterstützt, wechseln Sie zu „Speicher“, um die VPN-App zu suchen, und überprüfen Sie, ob HoloLens als unterstütztes Gerät aufgeführt ist und ob die App auf der Seite „Systemanforderungen“ die ARM- oder ARM64-Architektur unterstützt. HoloLens unterstützt nur Universelle Windows-Plattform-Anwendungen für VPN von Drittanbietern.

 VPN kann von der MDM über [Einstellungen/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) verwaltet und über die [Vpnv2-csp-Richtlinie](/windows/client-management/mdm/vpnv2-csp) festgelegt werden.

Erfahren Sie mehr über das [Konfigurieren eines VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) mit [ diesen Leitfäden](/windows/security/identity-protection/vpn/vpn-guide).  

### <a name="vpn-via-ui"></a>VPN über die Benutzeroberfläche

VPN ist standardmäßig nicht aktiviert, kann aber durch Öffnen der App **Einstellungen** und Navigieren zu **Netzwerk & Internet -> VPN** manuell aktiviert werden.
1. Auswählen eines VPN-Anbieters.
1. Erstellen eines Verbindungsnamen. 
1. Eingeben Ihres Servernamen oder Ihrer Adresse ein.
1. Auswählen des VPN-Typs.
1. Auswählen der Anmeldeinformationen. 
1. Fügen Sie optional Benutzername und Kennwort hinzu.
1. Anwenden der VPN-Einstellungen. 

![HoloLens VPN-Einstellungen.](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>VPN über Bereitstellungspaket einstellen

> [!TIP] 
> In unserer Windows Holographic Version 20H2 haben wir ein Problem mit der Proxy-Konfiguration für die VPN-Verbindung behoben. Wenn Sie diesen Datenstrom verwenden möchten, aktualisieren Sie Ihre Geräte bitte auf diesen Build.

1. Starten Sie den Windows Konfigurationsdesigner.
1. Klicken Sie auf **Bereitstellung von HoloLens Geräten**, wählen Sie dann Zielgerät und **Weiter** aus.
1. Geben Sie den Paketnamen und Pfad ein.
1. Klicken Sie auf **Wechseln zum erweiterten Editor**.
1. Öffnen Sie **Laufzeiteinstellungen** -> **Verbindungsprofile** ->  **VPN** -> **VPN-Einstellungen**.
1. Configure VPNProfileName
1. Wählen Sie den Profiltyp aus: **Nativ** oder **Drittanbieter**.
    1. Wählen Sie unter Natives Profil die Option **NativeProtocolType** und konfigurieren Sie dann Server, Routing-Richtlinie, Authentifizierungstyp und andere Einstellungen.
    1. Konfigurieren Sie für „Drittanbieter“-Profile Server-URL, VPN-Plug-in-App-Paket Familienname (es sind nur 3 vordefiniert) und benutzerdefinierte Konfigurationen.
1. Exportieren Sie Ihr Paket.
1. Verbinden Sie Ihr HoloLens und kopieren Sie die .ppkg-Datei auf das Gerät. 
1. Wenden Sie die VPN-.ppkg auf der HoloLens an, indem Sie das Startmenü öffnen und **Einstellungen** -> **Konto** -> **Geschäfts- oder Schulzugang** -> **Bereitstellungspaket hinzufügen oder entfernen** -> „Wählen Sie Ihr VPN Paket“ auswählen.


### <a name="setting-up-vpn-via-intune"></a>Einrichten eines VPN über Intune
Folgen Sie einfach der Intune-Anleitung um anzufangen. Beachten Sie bei der Durchführung dieser Schritte die eingebauten VPN-Protokolle, die HoloLens-Geräte unterstützen. 

[Erstellen von VPN-Profilen zum Herstellen einer Verbindung mit VPN-Servern in Intune](/mem/intune/configuration/vpn-settings-configure).

[Geräteeinstellungen für Windows 10 und Windows Holographic zum Hinzuzufügen von VPN-Verbindungen mit Intune](/mem/intune/configuration/vpn-settings-windows-10).

Wenn Sie fertig sind, denken Sie bitte daran, das Sie das [Profil zuweisen](/mem/intune/configuration/device-profile-assign).

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

### <a name="using-the-settings-app-on-hololens"></a>Verwenden der Einstellungen-App auf HoloLens

1. Öffnen Sie das Menü **Start**.
1. Wählen Sie die App **Einstellungen** unter **Start** oder aus der Liste **Alle Apps** rechts im **Startmenü** aus. Die App **Einstellungen** wird automatisch vor Ihnen platziert.
1. Wählen Sie **Netzwerk & Internet** aus.
1. Wählen Sie den WLAN-Schieberegler aus, schieben Sie ihn auf **Aus**. Dadurch werden die HF-Komponenten des WLAN-Funks ausgeschaltet und alle WLAN-Funktionen von HoloLens deaktiviert.

    > [!WARNING]
    > Wenn der WLAN-Funk deaktiviert ist, kann HoloLens Ihre [Räume](hololens-spaces.md) nicht automatisch laden.

1. Schieben Sie den Schieberegler in die Stellung **Ein**, um das WLAN zu aktivieren und die WLAN-Funktion auf Microsoft HoloLens wiederherzustellen. Der ausgewählte WLAN-Funkstatus (**Ein** oder **Aus**) bleibt bei einem Neustart erhalten.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Identifizieren der IP-Adresse Ihrer HoloLens im WLAN-Netzwerk

### <a name="by-using-the-settings-app"></a>Mit der Einstellungen-App

1. Öffnen Sie das Menü **Start**.
1. Wählen Sie die App **Einstellungen** unter **Start** oder aus der Liste **Alle Apps** rechts im **Startmenü** aus. Die App **Einstellungen** wird automatisch vor Ihnen platziert.
1. Wählen Sie **Netzwerk & Internet** aus.
1. Scrollen Sie nach unten unter die Liste der verfügbaren WLAN-Netzwerke und wählen Sie **Hardwareeigenschaften** aus.

    ![Hardwareeigenschaften in WLAN-Einstellungen.](./images/wifi-hololens-hwdetails.jpg)

   Die IP-Adresse wird neben der **IPv4-Adresse** angezeigt.

### <a name="by-using-voice-commands"></a>Mit Sprachbefehlen

Je nach Ihrem Geräte-Build können Sie entweder mit integrierten Sprachbefehlen oder Cortana Ihre IP-Adresse anzeigen. Bei Builds nach [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) sagen Sie „Wie lautet meine IP-Adresse?“ und sie wird angezeigt. Sagen Sie bei früheren Builds oder HoloLens (1. Generation): „Hey Cortana, wie lautet meine IP-Adresse?“, und Cortana wird Ihre IP-Adresse anzeigen und vorlesen.

### <a name="by-using-windows-device-portal"></a>Mit dem Windows-Geräteportals

1. Öffnen Sie in einem Webbrowser auf Ihrem PC das [Geräteportal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Navigieren Sie zum Abschnitt **Netzwerk**.  
   In diesem Abschnitt werden Ihre IP-Adresse und andere Netzwerkinformationen angezeigt. Mit dieser Methode können Sie die IP-Adresse auf Ihren Entwicklungs-PC kopieren und einfügen.

## <a name="change-ip-address-to-static-address"></a>IP-Adresse auf statische Adresse ändern
### <a name="by-using-settings"></a>Mit Einstellungen
 
1. Öffnen Sie das Menü **Start**.
1. Wählen Sie die App **Einstellungen** unter **Start** oder aus der Liste **Alle Apps** rechts im **Startmenü** aus. Die App **Einstellungen** wird automatisch vor Ihnen platziert.
1. Wählen Sie **Netzwerk & Internet** aus.
1. Scrollen Sie nach unten unter die Liste der verfügbaren WLAN-Netzwerke und wählen Sie **Hardwareeigenschaften** aus.
1. Ändern Sie das erste Feld auf **Manuell** im Fenster **IP-Einstellungen bearbeiten**.
1. Geben Sie die gewünschte IP-Konfiguration in die verbleibenden Felder ein und klicken Sie dann auf **Speichern**.

### <a name="by-using-windows-device-portal"></a>Mit dem Windows-Geräteportals

1. Öffnen Sie in einem Webbrowser auf Ihrem PC das [Geräteportal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Navigieren Sie zum Abschnitt **Netzwerk**.
1. Wählen Sie die Schaltfläche **IPv4-Konfiguration** aus.
1. Wählen Sie **Verwenden der folgenden IP-Adresse** aus und geben Sie die gewünschte TCP/IP-Konfiguration ein.
1. Wählen **Verwenden der folgenden DNS-Serveradressen** aus und geben Sie bei Bedarf die bevorzugten und alternativen DNS-Serveradressen ein.
1. Klicken Sie auf **Speichern**. 
