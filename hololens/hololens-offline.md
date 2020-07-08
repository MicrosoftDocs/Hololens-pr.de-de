---
title: Verwalten von Verbindungsendpunkten für HoloLens
description: Um HoloLens einzurichten, müssen Sie die Verbindung zu einem WLAN-Netzwerk herstellen.
keywords: HoloLens offline Windows-Willkommensseite
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
ms.openlocfilehash: f40d5adec0a8c0dc4bde5583a080ceedc0950fdb
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828368"
---
# Verwalten von Verbindungsendpunkten für HoloLens

Einige HoloLens -Komponenten, -Apps und zugehörige Dienste übertragen Daten an Microsoft-Netzwerkendpunkte. In diesem Artikel werden verschiedene Endpunkte und URLs aufgelistet, die in Ihrer Netzwerkkonfiguration (z. b. Proxy oder Firewall) zulässig sein müssen, damit diese Komponenten funktionsfähig sind.    

## Near-Offline-Setup

HoloLens unterstützt eine begrenzte Anzahl von Offline-Erlebnissen für Kunden, die Netzwerk-Umgebungsbeschränkungen aufweisen. Allerdings benötigt HoloLens eine Netzwerkverbindung, um die Einrichtung des anfänglichen Geräts zu durchlaufen, und die folgenden URLs müssen aktiviert sein:

| Zweck | URL |
|------|------|
| IDPS | https://sdx.microsoft.com/frx/idps |
| [NCSI](https://docs.microsoft.com/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| Aad-PIN | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| MSA | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| MSA Pin | https://account.live.com/msangc?fl=enroll |

## Endpunktkonfigurationen

Um die HoloLens-Funktionalität in vollem Umfang nutzen zu können, müssen die folgenden Endpunkte zusätzlich zur oben aufgeführten Liste in Ihrer Netzwerkkonfiguration aktiviert sein.


| Zweck | URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |   |   |   
|                                                     | ris-prod-atm.trafficmanager.net                                     |   |   |   |
|                                                     | validation-v2.sls.trafficmanager.net                                |   |   |   |
| Mehrstufige Azure AD-Authentifizierung                | https://secure.aadcdn.microsoftonline-p.com                         |   |   |   |
| InTune-und MDM-Konfigurationen                       | activation-v2.sls.microsoft.com/*                                   |   |   |   |
|                                                     | cdn.onenote.net                                                     |   |   |   |
|                                                     | client.wns.windows.com                                              |   |   |   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |   |   |   |
|                                                     | ctldl.windowsupdate.com                                             |   |   |   |
|                                                     | *displaycatalog.mp.microsoft.com                                    |   |   |   |
|                                                     | dm3p.wns.windows.com                                                |   |   |   |
|                                                     | *\*microsoft.com/pkiops/\**                                             |   |   |   |
|                                                     | ocsp.digicert.com/*                                                 |   |   |   |
|                                                     | r.manage.microsoft.com                                              |   |   |   |
|                                                     | tile-service.weather.microsoft.com                                  |   |   |   |
|                                                     | settings-win.data.microsoft.com                                     |   |   |   |
| Zertifikate                                        | activation-v2.sls.microsoft.com/*                                   |   |   |   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |   |   |   |
|                                                     | ocsp.digicert.com/*                                                 |   |   |   |
|                                                     | https://www.microsoft.com/pkiops/*                                          |   |   |   |
| Cortana und Suche                                  | store-images.*microsoft.com                                         |   |   |   |
|                                                     | www.bing.com/client                                                 |   |   |   |
|                                                     | www.bing.com                                                        |   |   |   |
|                                                     | www.bing.com/proactive                                              |   |   |   |
|                                                     | www.bing.com/threshold/xls.aspx                                     |   |   |   |
|                                                     | exo-ring.msedge.net                                                 |   |   |   |
|                                                     | fp.msedge.net                                                       |   |   |   |
|                                                     | fp-vp.azureedge.net                                                 |   |   |   |
|                                                     | odinvzc.azureedge.net                                               |   |   |   |
|                                                     | spo-ring.msedge.net                                                 |   |   |   |
| Geräteauthentifizierung                               | login.live.com*                                                     |   |   |   |
| Gerätemetadaten                                     | dmd.metaservices.microsoft.com                                      |   |   |   |
| Pfad                                            | Inference.Location.Live.NET                                         |   |   |   |
|                                                     | location-inference-westus.cloudapp.net                              |   |   |   |
| Diagnosedaten                                     | v10.events.data.microsoft.com                                       |   |   |   |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |   |   |   |
|                                                     | https://www.microsoft.com                                                   |   |   |   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |   |   |   |
|                                                     | cs11.wpc.v0cdn.net                                                  |   |   |   |
|                                                     | cs1137.wpc.gammacdn.net                                             |   |   |   |
|                                                     | modern.watson.data.microsoft.com*                                   |   |   |   |
|                                                     | watson.telemetry.microsoft.com                                      |   |   |   |
| Lizenzierung                                           | licensing.mp.microsoft.com                                          |   |   |   |
| Microsoft-Konto                                   | login.msa.akadns6.net                                               |   |   |   |
|                                                     | US.configsvc1.Live.com.akadns.NET                                   |   |   |   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |   |   |   |
| Microsoft-Umleitungsdienst für Weiterleitungsverknüpfungen (FWLink) | go.microsoft.com                                                    |   |   |   |
| Microsoft Store                                     | *.wns.windows.com                                                   |   |   |   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |   |   |   |
|                                                     | img-prod-cms-rt-microsoft-com*                                      |   |   |   |
|                                                     | store-images.microsoft.com                                          |   |   |   |
|                                                     | .md.mp.microsoft.com                                                |   |   |
|                                                     | *displaycatalog.mp.microsoft.com                                    |   |   |   |
|                                                     | pti.store.microsoft.com                                             |   |   |   |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |   |   |   |
|                                                     | markets.books.microsoft.com                                         |   |   |   |
|                                                     | share.microsoft.com                                                 |   |   |   |
| Netzwerkverbindungs-Statusanzeige (NCSI)          | www.msftconnecttest.com*                                            |   |   |   |
| Office                                              | *.c-msedge.net                                                      |   |   |   |
|                                                     | *.e-msedge.net                                                      |   |   |   |
|                                                     | *.s-msedge.net                                                      |   |   |   |
|                                                     | nexusrules.officeapps.Live.com                                      |   |   |   |
|                                                     | ocos-office365-s2s.msedge.net                                       |   |   |   |
|                                                     | officeclient.Microsoft.com                                          |   |   |   |
|                                                     | outlook.office365.com                                               |   |   |   |
|                                                     | client-office365-tas.msedge.net                                     |   |   |   |
|                                                     | https://www.office.com                                                      |   |   |   |
|                                                     | onecollector.cloudapp.aria                                          |   |   |   |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |   |   |   |
|                                                     | self.events.data.microsoft.com                                      |   |   |   |
|                                                     | Um do.microsoft.com                                                 |   |   |   |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |   |   |   |
|                                                     | msagfx.live.com                                                     |   |   |   |
|                                                     | oneclient.sfx.ms                                                    |   |   |   |
| Fotos-App                                          | evoke-windowsservices-tas.msedge.net                                |   |   |   |
| Einstellungen                                            | cy2.settings.data.microsoft.com.akadns.net                          |   |   |   |
|                                                     | settings.data.microsoft.com                                         |   |   |   |
|                                                     | settings-win.data.microsoft.com                                     |   |   |   |
| Windows Defender                                    | wdcp.microsoft.com                                                  |   |   |   |
|                                                     | definitionupdates.microsoft.com                                     |   |   |   |
|                                                     | go.microsoft.com                                                    |   |   |   |
|                                                     | *smartscreen.microsoft.com                                          |   |   |   |
|                                                     | smartscreen-sn3p.smartscreen.microsoft.com                          |   |   |   |
|                                                     | unitedstates.smartscreen-prod.microsoft.com                         |   |   |   |
| Windows-Blickpunkt                                   | *.search.msn.com                                                    |   |   |   |
|                                                     | arc.msn.com                                                         |   |   |   |
|                                                     | g.msn.com*                                                          |   |   |   |
|                                                     | query.prod.cms.rt.microsoft.com                                     |   |   |   |
|                                                     | ris.api.iris.microsoft.com                                          |   |   |   |
| Windows Update                                      | *.prod.do.dsp.mp.microsoft.com                                      |   |   |   |
|                                                     | cs9.wac.phicdn.net                                                  |   |   |   |
|                                                     | emdl.ws.microsoft.com                                               |   |   |   |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |   |   |   |
|                                                     | *.windowsupdate.com                                                 |   |   |   |
|                                                     | *.delivery.mp.microsoft.com                                         |   |   |   |
|                                                     | *.update.microsoft.com                                              |   |   |   |



## Verweise

> [!NOTE]
> Wenn Sie die Bereitstellung von D365 Remote Assist durchführen, müssen Sie die Endpunkte in dieser [Liste aktivieren](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) 
- [Konfigurieren von Windows-Diagnosedaten in Ihrer Organisation](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [Verwalten von Verbindungsendpunkten für Windows 10 Enterprise, Version 1903](https://docs.microsoft.com/windows/privacy/manage-windows-1903-endpoints)
- [Verwalten von Verbindungen zwischen Windows 10-Betriebssystemkomponenten und Microsoft-Diensten](https://docs.microsoft.com/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [Verwalten von Verbindungen zwischen Windows 10-Betriebssystemkomponenten und Microsoft-Diensten mit Microsoft Intune MDM-Server](https://docs.microsoft.com/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Intune-Netzwerk Konfigurationsanforderungen und Bandbreite](https://docs.microsoft.com/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Netzwerkendpunkte für Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/intune-endpoints)
- [Office 365-URLs und -IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)
- [Voraussetzungen für Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## HoloLens Beschränkungen

Nachdem Ihre HoloLens eingerichtet wurde, können Sie diese ohne eine WLAN-Verbindung verwenden, aber Apps, die Internetverbindungen verwenden, verfügen über eingeschränkte Funktionen, wenn Sie HoloLens offline verwenden.
