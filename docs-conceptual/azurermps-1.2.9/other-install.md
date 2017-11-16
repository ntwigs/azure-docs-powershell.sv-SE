---
title: "Andra sätt att installera Azure PowerShell | Microsoft Docs"
description: "Så här installerar du Azure PowerShell med hjälp av MSI-paketet eller installationsprogrammet för webbplattformen."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/06/2017
ms.openlocfilehash: 73c099375cecc8abdd5d6179109513946e7e793b
ms.sourcegitcommit: b256bf48e15ee98865de0fae50e7b81878b03a54
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2017
---
# <a name="other-installation-methods"></a><span data-ttu-id="93d3d-103">Andra installationsmetoder</span><span class="sxs-lookup"><span data-stu-id="93d3d-103">Other installation methods</span></span>

<span data-ttu-id="93d3d-104">Azure PowerShell har flera olika installationsmetoder.</span><span class="sxs-lookup"><span data-stu-id="93d3d-104">Azure PowerShell has multiple installation methods.</span></span> <span data-ttu-id="93d3d-105">Vi rekommenderar att du använder PowerShellGet med PowerShell-galleriet.</span><span class="sxs-lookup"><span data-stu-id="93d3d-105">Using PowerShellGet with the PowerShell Gallery is the preferred method.</span></span> <span data-ttu-id="93d3d-106">Azure PowerShell kan installeras på Windows med installationsprogram för webbplattformen (WebPI) eller med hjälp av MSI-filen som är tillgänglig från GitHub.</span><span class="sxs-lookup"><span data-stu-id="93d3d-106">Azure PowerShell can be installed on Windows using the Web Platform Installer (WebPI) or by using the MSI file available from GitHub.</span></span> <span data-ttu-id="93d3d-107">Azure PowerShell kan även installeras i en Docker-behållare.</span><span class="sxs-lookup"><span data-stu-id="93d3d-107">Azure PowerShell can also be installed in a Docker container.</span></span>

## <a name="install-on-windows-using-the-web-platform-installer"></a><span data-ttu-id="93d3d-108">Installera på Windows med hjälp av installationsprogrammet för webbplattformen</span><span class="sxs-lookup"><span data-stu-id="93d3d-108">Install on Windows using the Web Platform Installer</span></span>

<span data-ttu-id="93d3d-109">Att installera den senaste versionen av Azure PowerShell från WebPI går till på samma sätt som det gjorde för tidigare versioner.</span><span class="sxs-lookup"><span data-stu-id="93d3d-109">Installing the latest Azure PowerShell from WebPI is the same as it was for previous versions.</span></span>
<span data-ttu-id="93d3d-110">Hämta [Azure PowerShell WebPI-paketet](http://aka.ms/webpi-azps) och starta installationen.</span><span class="sxs-lookup"><span data-stu-id="93d3d-110">Download the [Azure PowerShell WebPI package](http://aka.ms/webpi-azps) and start the install.</span></span>

> [!NOTE]
> <span data-ttu-id="93d3d-111">Om du tidigare har installerat Azure-moduler från PowerShell-galleriet så kommer installationsprogrammet automatiskt att ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="93d3d-111">If you have previously installed Azure modules from the PowerShell Gallery, the installer automatically removes them.</span></span> <span data-ttu-id="93d3d-112">Detta förenklar din miljö genom att se till att endast en version av Azure PowerShell är installerad.</span><span class="sxs-lookup"><span data-stu-id="93d3d-112">This simplifies your environment by ensuring that only one version of Azure PowerShell is installed.</span></span> <span data-ttu-id="93d3d-113">Det finns dock scenarier där du kan behöva flera versioner installerade på samma gång.</span><span class="sxs-lookup"><span data-stu-id="93d3d-113">However, there are scenarios where you may need multiple versions installed at the same time.</span></span>
>
> <span data-ttu-id="93d3d-114">PowerShell-galleriets moduler installerar moduler i `$env:ProgramFiles\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="93d3d-114">PowerShell Gallery modules install modules in `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span> <span data-ttu-id="93d3d-115">WebPI-installationsprogrammet däremot installerar Azure moduler i `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.</span><span class="sxs-lookup"><span data-stu-id="93d3d-115">In contrast, the WebPI installer installs the Azure modules in `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.</span></span>
>
> <span data-ttu-id="93d3d-116">Om ett fel inträffar under installationen kan du ta bort Azure*-mapparna manuellt i din `$env:ProgramFiles\WindowsPowerShell\Modules`-mapp och försöka installera igen.</span><span class="sxs-lookup"><span data-stu-id="93d3d-116">If an error occurs during install, you can manually remove the Azure* folders in your `$env:ProgramFiles\WindowsPowerShell\Modules` folder, and try the installation again.</span></span>

<span data-ttu-id="93d3d-117">När installationen är färdig bör din `$env:PSModulePath`-inställning inkludera de kataloger som innehåller Azure PowerShell-cmdletarna.</span><span class="sxs-lookup"><span data-stu-id="93d3d-117">Once the installation completes, your `$env:PSModulePath` setting should include the directories containing the Azure PowerShell cmdlets.</span></span> <span data-ttu-id="93d3d-118">Följande kommando kan användas för att kontrollera att Azure PowerShell är korrekt installerad.</span><span class="sxs-lookup"><span data-stu-id="93d3d-118">The following command can be used to verify that the Azure PowerShell is installed properly.</span></span>

```powershell
# To make sure the Azure PowerShell module is available after you install
Get-Module -ListAvailable Azure* | Select-Object Name, Version, Path
```

> [!NOTE]
> <span data-ttu-id="93d3d-119">Det finns ett känt problem som kan uppstå när du installerar från WebPI.</span><span class="sxs-lookup"><span data-stu-id="93d3d-119">There is a known issue that can occur when installing from WebPI.</span></span> <span data-ttu-id="93d3d-120">Om datorn kräver en omstart på grund av systemuppdateringar eller andra installationer kan det göra att uppdateringarna för `$env:PSModulePath` inte inkluderar sökvägen där Azure PowerShell är installerat.</span><span class="sxs-lookup"><span data-stu-id="93d3d-120">If your computer requires a restart due to system updates or other installations, it may cause updates to `$env:PSModulePath` to fail to include the path where Azure PowerShell is installed.</span></span>

<span data-ttu-id="93d3d-121">När du försöker läsa in eller köra cmdletar efter installationen kan du få följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="93d3d-121">When attempting to load or execute cmdlets after installation, you can receive the following error message:</span></span>

```
PS C:\> Login-AzureRmAccount
Login-AzureRmAccount : The term 'Login-AzureRmAccount' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:1
+ Login-AzureRmAccount
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Login-AzureRmAccount:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="93d3d-122">Det här felet kan korrigeras genom att starta om datorn eller importera modulen med den fullständigt kvalificerade sökvägen.</span><span class="sxs-lookup"><span data-stu-id="93d3d-122">This error can be corrected by restarting the machine or importing the module using the fully qualified path.</span></span> <span data-ttu-id="93d3d-123">Exempel:</span><span class="sxs-lookup"><span data-stu-id="93d3d-123">For example:</span></span>

```powershell
Import-Module "$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\AzureRM.psd1"
```

## <a name="install-on-windows-using-the-msi-package"></a><span data-ttu-id="93d3d-124">Installera på Windows med hjälp av MSI-paketet</span><span class="sxs-lookup"><span data-stu-id="93d3d-124">Install on Windows using the MSI Package</span></span>

<span data-ttu-id="93d3d-125">Azure PowerShell kan installeras med hjälp av MSI-filen som är tillgänglig från [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="93d3d-125">Azure PowerShell can be installed using the MSI file available from [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span></span> <span data-ttu-id="93d3d-126">Om du har installerat tidigare versioner av Azure-moduler så kommer installationsprogrammet automatiskt att ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="93d3d-126">If you have installed previous versions of Azure modules, the installer automatically removes them.</span></span> <span data-ttu-id="93d3d-127">MSI-paketet installerar moduler i `$env:ProgramFiles\WindowsPowerShell\Modules` men skapar inte versionsspecifika mappar.</span><span class="sxs-lookup"><span data-stu-id="93d3d-127">The MSI package installs modules in `$env:ProgramFiles\WindowsPowerShell\Modules` but does not create version-specific folders.</span></span>

## <a name="install-in-a-docker-container"></a><span data-ttu-id="93d3d-128">Installera i en Docker-behållare</span><span class="sxs-lookup"><span data-stu-id="93d3d-128">Install in a Docker container</span></span>

<span data-ttu-id="93d3d-129">Vi underhåller en Docker-avbildning som är förkonfigurerad med Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93d3d-129">We maintain a Docker image preconfigured with Azure PowerShell.</span></span>

<span data-ttu-id="93d3d-130">Kör behållaren med `docker run`.</span><span class="sxs-lookup"><span data-stu-id="93d3d-130">Run the container with `docker run`.</span></span>

```powershell
docker run azuresdk/azure-powershell
```

<span data-ttu-id="93d3d-131">Dessutom underhåller vi en delmängd cmdletar som PowerShell Core-behållare.</span><span class="sxs-lookup"><span data-stu-id="93d3d-131">In addition, we maintain a subset of cmdlets as a PowerShell Core container.</span></span>

<span data-ttu-id="93d3d-132">Använd `latest`-avbildningen för Mac/Linux.</span><span class="sxs-lookup"><span data-stu-id="93d3d-132">For Mac/Linux, use the `latest` image.</span></span>

```bash
docker run azuresdk/azure-powershell-core:latest
```

<span data-ttu-id="93d3d-133">Använd `nanoserver`-avbildningen för Windows.</span><span class="sxs-lookup"><span data-stu-id="93d3d-133">For Windows, use the `nanoserver` image.</span></span>

```powershell
docker run azuresdk/azure-powershell-core:nanoserver
```

<span data-ttu-id="93d3d-134">Azure PowerShell är installerat på avbildningen via `Install-Module` från [PowerShell-galleriet](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="93d3d-134">Azure PowerShell is installed on the image via `Install-Module` from the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>