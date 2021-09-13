---
title: Verwalten von Verbindungsendpunkten für HoloLens
description: Hier erfahren Sie, wie Sie HoloLens über ein WLAN einrichten, während Sie Verbindungsendpunkte verwalten und konfigurieren.
keywords: HoloLens, offline, Begrüßungsseite
audience: ITPro
ms.date: 07/01/2019
ms.assetid: b86f603c-d25f-409b-b055-4bbc6edcd301
author: Teresa-Motiv
ms.author: v-tea
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: jarrettr
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f2d9faafac2f84b727b1e10be83d4d1b53a707b4
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034382"
---
# <a name="manage-connection-endpoints-for-hololens"></a>Verwalten von Verbindungsendpunkten für HoloLens

Einige HoloLens -Komponenten, -Apps und zugehörige Dienste übertragen Daten an Microsoft-Netzwerkendpunkte. In diesem Artikel werden verschiedene Endpunkte und URLs aufgelistet, die in Ihrer Netzwerkkonfiguration zugelassen sein müssen (z. B. Proxy oder Firewall), damit diese Komponenten funktionsfähig sind.    

## <a name="near-offline-setup"></a>Fast-Offline-Einrichtung

HoloLens unterstützt eine begrenzte Anzahl von Offline-Erlebnissen für Kunden, die über eingeschränkte Netzwerkumgebungen verfügen. Allerdings benötigt HoloLens eine Netzwerkverbindung, um die Ersteinrichtung des Geräts zu durchlaufen, und die folgenden URLs müssen aktiviert sein:

| Zweck | URL |
|------|------|
| IDPS | https://sdx.microsoft.com/frx/idps |
| [NCSI](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| AAD Pin | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| MSA | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| MSA Pin | https://account.live.com/msangc?fl=enroll |

## <a name="endpoint-configuration"></a>Endpunktkonfiguration

Um die HoloLens-Funktionalität in vollem Umfang nutzen zu können, müssen in Ihrer Netzwerkkonfiguration die folgenden Endpunkte zusätzlich zur oben aufgeführten Liste aktiviert sein.


| Zweck | URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |
|                                                     | ris-prod-atm.trafficmanager.net                                     |
|                                                     | validation-v2.sls.trafficmanager.net                                |
| Azure AD Multi-Factor Authentication                | https://secure.aadcdn.microsoftonline-p.com                         |
| Intune- und MDM-Konfigurationen                       | activation-v2.sls.microsoft.com/*                                   |
|                                                     | cdn.onenote.net                                                     |
|                                                     | client.wns.windows.com                                              |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ctldl.windowsupdate.com                                             |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | dm3p.wns.windows.com                                                |
|                                                     | *microsoft.com/pkiops/*                                             |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | r.manage.microsoft.com                                              |
|                                                     | tile-service.weather.microsoft.com                                  |
|                                                     | settings-win.data.microsoft.com                                     |
| Zertifikate                                        | activation-v2.sls.microsoft.com/*                                   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | https://www.microsoft.com/pkiops/*                                          |
| Cortana und Suche                                  | store-images.*microsoft.com                                         |
|                                                     | www.bing.com/client                                                 |
|                                                     | www.bing.com                                                        |
|                                                     | www.bing.com/proactive                                              |
|                                                     | www.bing.com/threshold/xls.aspx                                     |
|                                                     | exo-ring.msedge.net                                                 |
|                                                     | fp.msedge.net                                                       |
|                                                     | fp-vp.azureedge.net                                                 |
|                                                     | odinvzc.azureedge.net                                               |
|                                                     | spo-ring.msedge.net                                                 |
| Geräteauthentifizierung                               | login.live.com*                                                     |
| Gerätemetadaten                                     | dmd.metaservices.microsoft.com                                      |
| Speicherort                                            | inference.location.live.net                                         |
|                                                     | location-inference-westus.cloudapp.net                              |
| Diagnosedaten                                     | v10.events.data.microsoft.com                                       |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |
|                                                     | https://www.microsoft.com                                                   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |
|                                                     | cs11.wpc.v0cdn.net                                                  |
|                                                     | cs1137.wpc.gammacdn.net                                             |
|                                                     | modern.watson.data.microsoft.com*                                   |
|                                                     | watson.telemetry.microsoft.com                                      |
| Lizenzierung                                           | licensing.mp.microsoft.com                                          |
| Microsoft-Konto                                   | login.msa.akadns6.net                                               |
|                                                     | us.configsvc1.live.com.akadns.net                                   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |
| Microsoft-Umleitungsdienst für Vorwärts-Verknüpfungen (FWLink) | go.microsoft.com                                                    |
| Microsoft Store                                     | *.wns.windows.com                                                   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |
|                                                     | img-prod-cms-rt-microsoft-com*                                      |
|                                                     | store-images.microsoft.com                                          |
|                                                     | .md.mp.microsoft.com                                                |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | pti.store.microsoft.com                                             |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |
|                                                     | markets.books.microsoft.com                                         |
|                                                     | share.microsoft.com                                                 |
| Netzwerkverbindungs-Statusanzeige (NCSI)          | www.msftconnecttest.com*                                            |
| Office                                              | *.c-msedge.net                                                      |
|                                                     | *.e-msedge.net                                                      |
|                                                     | *.s-msedge.net                                                      |
|                                                     | nexusrules.officeapps.live.com                                      |
|                                                     | ocos-office365-s2s.msedge.net                                       |
|                                                     | officeclient.microsoft.com                                          |
|                                                     | outlook.office365.com                                               |
|                                                     | client-office365-tas.msedge.net                                     |
|                                                     | https://www.office.com                                                      |
|                                                     | onecollector.cloudapp.aria                                          |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |
|                                                     | self.events.data.microsoft.com                                      |
|                                                     | to-do.microsoft.com                                                 |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |
|                                                     | msagfx.live.com                                                     |
|                                                     | oneclient.sfx.ms                                                    |
| Fotos-App                                          | evoke-windowsservices-tas.msedge.net                                |
| Einstellungen                                            | cy2.settings.data.microsoft.com.akadns.net                          |
|                                                     | settings.data.microsoft.com                                         |
|                                                     | settings-win.data.microsoft.com                                     |
| Windows Defender                                    | wdcp.microsoft.com                                                  |
|                                                     | definitionupdates.microsoft.com                                     |
|                                                     | go.microsoft.com                                                    |
|                                                     | *smartscreen.microsoft.com                                          |
|                                                     | smartscreen-sn3p.smartscreen.microsoft.com                          |
|                                                     | unitedstates.smartscreen-prod.microsoft.com                         |
| Windows-Blickpunkt                                   | *.search.msn.com                                                    |
|                                                     | arc.msn.com                                                         |
|                                                     | g.msn.com*                                                          |
|                                                     | query.prod.cms.rt.microsoft.com                                     |
|                                                     | ris.api.iris.microsoft.com                                          |
| Windows-Update                                      | *.prod.do.dsp.mp.microsoft.com                                      |
|                                                     | cs9.wac.phicdn.net                                                  |
|                                                     | emdl.ws.microsoft.com                                               |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |
|                                                     | *.windowsupdate.com                                                 |
|                                                     | *.delivery.mp.microsoft.com                                         |
|                                                     | *.update.microsoft.com                                              |



## <a name="references"></a>Referenzen

> [!NOTE]
> Wenn Sie D365 Remote Assist bereitstellen, müssen Sie die Endpunkte aktivieren, die für SharePoint Online und OneDrive for Business in [Office 365 URLs und IP-Adressbereichen](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)aufgeführt sind.

- [Konfigurieren von Windows-Diagnosedaten in Ihrer Organisation](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [Verwalten von Verbindungsendpunkten für Windows 10 Enterprise, Version 1903](/windows/privacy/manage-windows-1903-endpoints)
- [Verwalten von Verbindungen zwischen Windows 10-Betriebssystemkomponenten und Microsoft-Diensten](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [Verwalten von Verbindungen zwischen Windows 10-Betriebssystemkomponenten und Microsoft-Diensten mit Microsoft Intune MDM-Server](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Bandbreiten- und andere Anforderungen an die Netzwerkkonfiguration für Intune](/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Netzwerkendpunkte für Microsoft Intune](/intune/fundamentals/intune-endpoints)
- [URLs und IP-Adressbereiche für Office 365](/office365/enterprise/urls-and-ip-address-ranges)
- [Voraussetzungen für Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## <a name="hololens-limitations"></a>HoloLens-Einschränkungen

Nachdem Ihre HoloLens eingerichtet wurde, können Sie diese ohne eine WLAN-Verbindung verwenden, aber Apps, die Internetverbindungen verwenden, bieten nur eingeschränkte Funktionen, wenn Sie HoloLens offline verwenden.
