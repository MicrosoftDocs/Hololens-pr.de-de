---
title: Global zugewiesener Zugriff
description: Leitfaden für die Verwendung von Oma-URI für global zugewiesene Zugriff-Kioske
author: evmill
ms.author: v-evmill
ms.date: 7/13/2020
ms.topic: article
keywords: HoloLens, HoloLens 2, zugewiesener Zugriff, Kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ad7f75ccfcae9fb42974abb43d87f2f1ce1571f8
ms.sourcegitcommit: 3db43bc4a007b10901d8edb045f66e1e299c57a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882442"
---
# <span data-ttu-id="9bc33-104">Global zugewiesener Zugriff – Kiosk</span><span class="sxs-lookup"><span data-stu-id="9bc33-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="9bc33-105">Dieses Feature konfiguriert das Hololens 2-Gerät für den Multi-App-Kioskmodus, der auf Systemebene anwendbar ist, keine Affinität zu einer anderen Identität des Systems hat und für jeden gilt, der sich auf dem Gerät anmeldet.</span><span class="sxs-lookup"><span data-stu-id="9bc33-105">This feature configures Hololens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> 

> [!NOTE]
> <span data-ttu-id="9bc33-106">Dieses Feature ist derzeit nur in Windows-Insider-Builds verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9bc33-106">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="9bc33-107">Wenn Sie dieses Feature ausprobieren möchten, bevor es in HoloLens-Versionen allgemein verfügbar sein wird, lesen Sie weitere Informationen zu [Windows Insider-](hololens-insider.md)-Builds.</span><span class="sxs-lookup"><span data-stu-id="9bc33-107">If you would like to try this feature before it is generally avalible in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>
 
## <span data-ttu-id="9bc33-108">Wie verwende ich dies in InTune?</span><span class="sxs-lookup"><span data-stu-id="9bc33-108">How to use this in Intune?</span></span> 

> [!NOTE]
> <span data-ttu-id="9bc33-109">Bitte beachten Sie die mit "<!-" markierten Bereiche.</span><span class="sxs-lookup"><span data-stu-id="9bc33-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="9bc33-110">In diesen Bereichen müssen Sie Änderungen vornehmen, die Ihren Voreinstellungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9bc33-110">These areas will require you to make modifications based on your preferences.</span></span> 

1.  <span data-ttu-id="9bc33-111">Erstellen Sie ein benutzerdefiniertes Konfigurationsprofil für OMA-URI-Geräte wie folgt, und wenden Sie es auf die HoloLens-Gerätegruppe an: ![Global zugewiesene Zugriff Oma-URI in InTune</span><span class="sxs-lookup"><span data-stu-id="9bc33-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group: ![Global Assigned Access OMA-URI in Intune</span></span>](images/global-assigned-access-omauri.png)

2.  <span data-ttu-id="9bc33-112">Für Wert, aktualisieren und einfügen des folgenden Inhalts:</span><span class="sxs-lookup"><span data-stu-id="9bc33-112">For value, update and paste following content:</span></span> 

    ```xml
    <?xml version="1.0" encoding="utf-8" ?> 
    <AssignedAccessConfiguration 
        xmlns="http://schemas.microsoft.com/AssignedAccess/2017/config" 
        xmlns:v2="http://schemas.microsoft.com/AssignedAccess/201810/config" 
        xmlns:v3="http://schemas.microsoft.com/AssignedAccess/2020/config" 
        xmlns:rs5="http://schemas.microsoft.com/AssignedAccess/201810/config" 
    > 
        <Profiles> 
            <Profile Id="{8739C257-184F-45DD-8657-C235819172A3}"> 
                <AllAppsList> 
                    <AllowedApps>                     
                        <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch=”true” /> --> 
                         <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.settingn_8wekyb3d8bbwe!MicrosoftEdge" /> --> 
                     </AllowedApps> 
                </AllAppsList> 
                <StartLayout> 
                    <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"> 
                          <LayoutOptions StartTileGroupCellWidth="6" /> 
                          <DefaultLayoutOverride> 
                            <StartLayoutCollection> 
                              <defaultlayout:StartLayout GroupCellWidth="6"> 
                                <start:Group Name="Life at a glance"> 
                                  <!—This AUMID can be of any app and is not used on Hololens but is required for parity, so you can leave it as is. --> 
                                  <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" />                               
                                </start:Group> 
                              </defaultlayout:StartLayout> 
                            </StartLayoutCollection> 
                          </DefaultLayoutOverride> 
                        </LayoutModificationTemplate> 
                    ]]> 
                </StartLayout> 
                <Taskbar ShowTaskbar="true"/> 
            </Profile> 
        </Profiles> 
        <Configs> 
            <v3:GlobalProfile Id="{8739C257-184F-45DD-8657-C235819172A3}"/> 
        </Configs> 
    </AssignedAccessConfiguration> 
    ```

## <span data-ttu-id="9bc33-113">Wie verwende ich das im Windows Konfigurations-Designer?</span><span class="sxs-lookup"><span data-stu-id="9bc33-113">How to use this in Windows Configuration Designer?</span></span> 
 
1.  <span data-ttu-id="9bc33-114">Aktualisieren und speichern Sie den oben erwähnten XML-BLOB als XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="9bc33-114">Update and save XML blob mentioned above as XML file.</span></span> 

2.  <span data-ttu-id="9bc33-115">Führen Sie die Schritte in [Verwenden eines Bereitstellungspakets aus, um einen Single-App- oder Multi-App-Kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)einzurichten, insbesondere den Abschnitt Prov.</span><span class="sxs-lookup"><span data-stu-id="9bc33-115">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="9bc33-116">Paket, Schritt 2 – Fügen Sie die Kiosk-Konfigurations-XML-Datei zu einem Bereitstellungspaket hinzu und verweisen Sie auf die XML-Datei, die im vorherigen Schritt gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="9bc33-116">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span> 

## <span data-ttu-id="9bc33-117">Kann ich eine Konfiguration erstellen, bei der Global für alle Personen mit Ausnahme des 1 AAD-Kontos oder der AAD-Gruppe gilt?</span><span class="sxs-lookup"><span data-stu-id="9bc33-117">Can I create a configuration where global applies to everyone except 1 AAD account or AAD group?</span></span> 

<span data-ttu-id="9bc33-118">Ja, weitere Informationen dazu finden Sie im folgenden Beispiel-XML-BLOB.</span><span class="sxs-lookup"><span data-stu-id="9bc33-118">Yes, please refer to the example XML blob below.</span></span> <span data-ttu-id="9bc33-119">Das global zugewiesene Zugriff-Profil wird auf HoloLens angewendet, wenn ein bestimmtes Profil für den angemeldeten Benutzer nicht gefunden wird. Daher ist dies die Standardkonfiguration für den Kioskmodus für angemeldete Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9bc33-119">Global Assigned Access profile is applied on Hololens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span> <span data-ttu-id="9bc33-120">Hier ist ein Beispiel für die Verwendung von XML-BLOB:</span><span class="sxs-lookup"><span data-stu-id="9bc33-120">Here is an example of XML blob to be used:</span></span> 

> [!NOTE]
> <span data-ttu-id="9bc33-121">Bitte beachten Sie die mit <! Markierten Bereiche. In diesen Bereichen müssen Sie Änderungen vornehmen, die Ihren Voreinstellungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9bc33-121">Please be aware of the areas marked with <!-  these areas will require you to make modifications based on your preferences.</span></span> 

```xml
<?xml version="1.0" encoding="utf-8" ?> 
<AssignedAccessConfiguration xmlns="http://schemas.microsoft.com/AssignedAccess/2017/config" 
    xmlns:v2="http://schemas.microsoft.com/AssignedAccess/201810/config" 
    xmlns:v3="http://schemas.microsoft.com/AssignedAccess/2020/config" 
    xmlns:rs5="http://schemas.microsoft.com/AssignedAccess/201810/config"> 
    <Profiles> 
        <Profile Id="{9A2A490F-10F6-4764-974A-43B19E722C23}"> 
            <!—specify AUMIDs and other nodes as used in example above --> 
        </Profile> 
        <Profile Id="{8739C257-184F-45DD-8657-C235819172A3}"> 
            <!—specify AUMIDs and other nodes as used in example above --> 
        </Profile> 
    </Profiles> 
    <Configs> 
        <v3:GlobalProfile Id="{8739C257-184F-45DD-8657-C235819172A3}"/> 
        <Config> 
           <Account>AzureAD\<!-fully qualified AAD account name></Account> 
           <DefaultProfile Id="{9A2A490F-10F6-4764-974A-43B19E722C23}"/> 
        </Config> 
    </Configs> 
</AssignedAccessConfiguration> 
```
