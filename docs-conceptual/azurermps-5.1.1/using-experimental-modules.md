---
title: "Använda experimentella Azure PowerShell-moduler"
description: "Förstå filosofin och användningen av experimentella Azure PowerShell-moduler."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/05/2017
ms.openlocfilehash: c11e4503c07b0a0c4a71021bc511da723098188e
ms.sourcegitcommit: 42bfd513fe646494d3d9eb0cfc35b049f7e1fbb7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2017
---
# <a name="using-experimental-azure-powershell-modules"></a><span data-ttu-id="f9409-103">Använda experimentella Azure PowerShell-moduler</span><span class="sxs-lookup"><span data-stu-id="f9409-103">Using experimental Azure PowerShell modules</span></span>

<span data-ttu-id="f9409-104">Med betoning på utvecklarverktyg (i synnerhet CLI:er) i Azure experimenterar Azure PowerShell-teamet med många förbättringar av Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9409-104">With the emphasis on developer tools (especially CLIs) in Azure, the Azure PowerShell team is experimenting with many improvements to the Azure PowerShell experience.</span></span>

## <a name="experimentation-methodology"></a><span data-ttu-id="f9409-105">Metodik</span><span class="sxs-lookup"><span data-stu-id="f9409-105">Experimentation methodology</span></span>

<span data-ttu-id="f9409-106">För att underlätta experimenteringen skapar vi nya Azure PowerShell-moduler som implementerar befintliga Azure SDK-funktioner på nya, mer lättanvända sätt.</span><span class="sxs-lookup"><span data-stu-id="f9409-106">To facilitate experimentation, we are creating new Azure PowerShell modules that implement existing Azure SDK functionality in new, easier to use ways.</span></span> <span data-ttu-id="f9409-107">I de flesta fall speglar cmdletar exakt befintliga cmdletar.</span><span class="sxs-lookup"><span data-stu-id="f9409-107">In most cases, the cmdlets exactly mirror existing cmdlets.</span></span> <span data-ttu-id="f9409-108">Experimentella cmdletar tillhandahåller däremot snabba kommentarer och smartare standardvärden som gör det enklare att skapa och hantera Azure-resurser.</span><span class="sxs-lookup"><span data-stu-id="f9409-108">However, the experimental cmdlets provide a shorthand notation and smarter default values that make it easier to create and manage Azure resources.</span></span>

<span data-ttu-id="f9409-109">Dessa moduler kan vara installerade sida vid sida med befintliga Azure PowerShell-moduler.</span><span class="sxs-lookup"><span data-stu-id="f9409-109">These modules can be installed side-by-side with existing Azure PowerShell modules.</span></span> <span data-ttu-id="f9409-110">Cmdlet-namnen har kortats ned för att få kortare namn och undvika namnkonflikter med befintliga, icke-experimentella cmdletar.</span><span class="sxs-lookup"><span data-stu-id="f9409-110">The cmdlet names have been shortened to provide shorter names and avoid name conflicts with existing, non-experimental cmdlets.</span></span>

<span data-ttu-id="f9409-111">De experimentella modulerna använder följande namngivningskonvention: `AzureRM.*.Experiments`.</span><span class="sxs-lookup"><span data-stu-id="f9409-111">The experimental modules use the following naming convention: `AzureRM.*.Experiments`.</span></span> <span data-ttu-id="f9409-112">Namngivningskonventionen liknar namngivningen i förhandsversionsmoduler: `AzureRM.*.Preview`.</span><span class="sxs-lookup"><span data-stu-id="f9409-112">This naming convention is similar to the naming of Preview modules: `AzureRM.*.Preview`.</span></span> <span data-ttu-id="f9409-113">Förhandsversionsmoduler skiljer sig från experimentella moduler.</span><span class="sxs-lookup"><span data-stu-id="f9409-113">Preview modules differ from experimental modules.</span></span> <span data-ttu-id="f9409-114">Förhandsversionsmoduler implementerar nya funktioner i Azure-tjänster som endast är tillgängliga som en förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="f9409-114">Preview modules implement new functionality of Azure services that is only available as a Preview offering.</span></span> <span data-ttu-id="f9409-115">Förhandsversionsmoduler ersätter befintliga Azure PowerShell-moduler och använder samma cmdlet- och parameternamn.</span><span class="sxs-lookup"><span data-stu-id="f9409-115">Preview modules replace existing Azure PowerShell modules and use the same cmdlet and parameter names.</span></span>

## <a name="how-to-install-an-experimental-module"></a><span data-ttu-id="f9409-116">Så här installerar du en experimentell modul</span><span class="sxs-lookup"><span data-stu-id="f9409-116">How to install an experimental module</span></span>

<span data-ttu-id="f9409-117">Experimentella moduler publiceras i PowerShell-galleriet precis som de befintliga Azure PowerShell-modulerna.</span><span class="sxs-lookup"><span data-stu-id="f9409-117">Experimental modules are published to the PowerShell Gallery just like the existing Azure PowerShell modules.</span></span> <span data-ttu-id="f9409-118">Om du vill se en lista med experimentella moduler kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="f9409-118">To see a list of experimental modules, run the following command:</span></span>

```powershell
Find-Module AzureRM.*.Experiments
```

```Output
Version Name                         Repository Description
------- ----                         ---------- -----------
1.0.25  AzureRM.Compute.Experiments  PSGallery  Azure Compute experiments for VM creation
1.0.0   AzureRM.Websites.Experiments PSGallery  Create and deploy web applications using Azure App Services.
```

<span data-ttu-id="f9409-119">Om du vill installera den experimentella modulen ska du använda följande kommandon från en upphöjd PowerShell-session:</span><span class="sxs-lookup"><span data-stu-id="f9409-119">To install the experimental module, use the following commands from an elevated PowerShell session:</span></span>

```powershell
Install-Module AzureRM.Compute.Experiments
Install-Module AzureRM.Websites.Experiments
```

### <a name="documentation-and-support"></a><span data-ttu-id="f9409-120">Dokumentation och support</span><span class="sxs-lookup"><span data-stu-id="f9409-120">Documentation and support</span></span>

<span data-ttu-id="f9409-121">Dokumentation som ingår i installationspaketet och som du får åtkomst till med cmdlet `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="f9409-121">Documentation is included in the install package and is accessed using the `Get-Help` cmdlet.</span></span> <span data-ttu-id="f9409-122">Ingen officiell dokumentation publiceras för experimentella moduler.</span><span class="sxs-lookup"><span data-stu-id="f9409-122">No official documentation is published for experimental modules.</span></span>

<span data-ttu-id="f9409-123">Vi uppmuntrar dig att testa dessa moduler.</span><span class="sxs-lookup"><span data-stu-id="f9409-123">We encourage you to test these modules.</span></span> <span data-ttu-id="f9409-124">Din feedback gör att vi kan förbättra användbarhet och svara på dina behov.</span><span class="sxs-lookup"><span data-stu-id="f9409-124">Your feedback allows us to improve usability and respond to your needs.</span></span> <span data-ttu-id="f9409-125">Men eftersom modulerna är experimentella är supporten för dem begränsad.</span><span class="sxs-lookup"><span data-stu-id="f9409-125">However, being experimental, support for these modules is limited.</span></span> <span data-ttu-id="f9409-126">Frågor eller problem rapporter kan skickas genom att skapa ett [problem](https://github.com/Azure/azure-powershell/issues) i GitHub-lagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="f9409-126">Questions or problem reports can be submitted by creating an [issue](https://github.com/Azure/azure-powershell/issues) in the GitHub repository.</span></span>

## <a name="experiments-and-areas-of-improvement"></a><span data-ttu-id="f9409-127">Experiment och förbättringsområden</span><span class="sxs-lookup"><span data-stu-id="f9409-127">Experiments and areas of improvement</span></span>

<span data-ttu-id="f9409-128">Dessa förbättringar har valts ut baserat på viktiga skillnaderna i konkurrerande produkter.</span><span class="sxs-lookup"><span data-stu-id="f9409-128">These improvements were selected based on key differentiators in competing products.</span></span> <span data-ttu-id="f9409-129">Azure CLI 2.0 är det till exempel viktigt att kommandon baseras på _scenarier_ snarare än _API-ytan_.</span><span class="sxs-lookup"><span data-stu-id="f9409-129">For example, Azure CLI 2.0 has made a point of basing commands on _scenarios_ rather than _API surface area_.</span></span>
<span data-ttu-id="f9409-130">I Azure CLI 2.0 används ett antal smarta standardvärden som förenklar kom-igång-scenarier för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="f9409-130">Azure CLI 2.0 use a number of smart defaults that make "getting started" scenarios easier for end users.</span></span>

### <a name="core-improvements"></a><span data-ttu-id="f9409-131">Grundläggande förbättringar</span><span class="sxs-lookup"><span data-stu-id="f9409-131">Core improvements</span></span>

<span data-ttu-id="f9409-132">Grundläggande förbättringar räknas som ”sunt förnuft” och lite experimenterande krävs för att gå vidare och implementera uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="f9409-132">The core improvements are regarded as "common sense", and little experimentation is needed to move forward in implementing these updates.</span></span>

- <span data-ttu-id="f9409-133">Scenario-baserade cmdletar – **All*-cmdletar bör utformas runt scenarier, inte Azure REST-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f9409-133">Scenario-based Cmdlets - **All*- cmdlets should be designed around scenarios, not the Azure REST service.</span></span>

- <span data-ttu-id="f9409-134">Kortare namn – Omfattar namnen på cmdletar (till exempel `New-AzureRmVM` => `New-AzVm`) och parameternamnen (till exempel `-ResourceGroupName` => `-Rg`).</span><span class="sxs-lookup"><span data-stu-id="f9409-134">Shorter Names - Includes the names of cmdlets (for example, `New-AzureRmVM` => `New-AzVm`) and the names of parameters (for example, `-ResourceGroupName` => `-Rg`).</span></span> <span data-ttu-id="f9409-135">Använd alias för kompatibilitet med ”gamla” cmdletar.</span><span class="sxs-lookup"><span data-stu-id="f9409-135">Use aliases for compatibility with "old" cmdlets.</span></span> <span data-ttu-id="f9409-136">Tillhandahåll _bakåtkompatibla_ parameteruppsättningar.</span><span class="sxs-lookup"><span data-stu-id="f9409-136">Provide _backwards compatible_ parameter sets.</span></span>

- <span data-ttu-id="f9409-137">Smarta standardvärden – Skapa smarta standardvärden för att fylla i ”obligatorisk” information.</span><span class="sxs-lookup"><span data-stu-id="f9409-137">Smart Defaults - Create smart defaults to fill in "required" information.</span></span> <span data-ttu-id="f9409-138">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="f9409-138">For example:</span></span>
  - <span data-ttu-id="f9409-139">Resursgrupp</span><span class="sxs-lookup"><span data-stu-id="f9409-139">Resource Group</span></span>
  - <span data-ttu-id="f9409-140">Plats</span><span class="sxs-lookup"><span data-stu-id="f9409-140">Location</span></span>
  - <span data-ttu-id="f9409-141">Beroende resurser</span><span class="sxs-lookup"><span data-stu-id="f9409-141">Dependent resources</span></span>

### <a name="experimental-improvements"></a><span data-ttu-id="f9409-142">Experimentella förbättringar</span><span class="sxs-lookup"><span data-stu-id="f9409-142">Experimental improvements</span></span>

<span data-ttu-id="f9409-143">Experimentella förbättringar presenterat en betydande förändring som teamet vill validera via experimentering.</span><span class="sxs-lookup"><span data-stu-id="f9409-143">The experimental improvements present a significant change that the team wants to validate via experimentation.</span></span>

- <span data-ttu-id="f9409-144">Enkla typer – Skapa-scenarier bör komma bort från komplexa typer och konfigurationsobjekt.</span><span class="sxs-lookup"><span data-stu-id="f9409-144">Simple types - Create scenarios should move away from complex types and config objects.</span></span> <span data-ttu-id="f9409-145">Förenkla konfigurationen till en eller två parametrar.</span><span class="sxs-lookup"><span data-stu-id="f9409-145">Simplify the configuration down to one or two parameters.</span></span>

- <span data-ttu-id="f9409-146">”Smart Create” – Alla skapa-scenarier som implementerar ”Smart Create” skulle inte ha _någon_ obligatorisk parameter: all nödvändig information skulle väljas av Azure PowerShell på ett smart sätt.</span><span class="sxs-lookup"><span data-stu-id="f9409-146">"Smart Create" - All create scenarios implementing "Smart Create" would have _no_ required parameters: all necessary information would be chosen by Azure PowerShell in an opinionated fashion.</span></span>

- <span data-ttu-id="f9409-147">Grå parametrar – I många fall skulle vissa parametrar kunna vara ”grå” eller delvis valfria.</span><span class="sxs-lookup"><span data-stu-id="f9409-147">Gray Parameters - In many cases, some parameters could be "gray" or semi-optional.</span></span> <span data-ttu-id="f9409-148">Om parametern inte anges, ska användarna tillfrågas om de vill den parameter som genererats åt dem.</span><span class="sxs-lookup"><span data-stu-id="f9409-148">If the parameter is not specified, the user is asked if they want the parameter generated for them.</span></span> <span data-ttu-id="f9409-149">Det vore också rimligt att grå parametrar med användarens medgivande skulle härleda ett värde utifrån sammanhanget.</span><span class="sxs-lookup"><span data-stu-id="f9409-149">It also makes sense for gray parameters to infer a value based on context with the user's consent.</span></span>
  <span data-ttu-id="f9409-150">Exempelvis kunde det vara klokt att den grå parametern föreslår det senast använda värdet.</span><span class="sxs-lookup"><span data-stu-id="f9409-150">For example, it may make sense to have the gray parameter suggest the most recently used value.</span></span>

- <span data-ttu-id="f9409-151">Switchen `-Auto` – Switchen `-Auto` skulle göra det möjligt för användare att välja _standardvärden på allt_ samtidigt som obligatoriska parametrars integritet bevaras i huvudspåret.</span><span class="sxs-lookup"><span data-stu-id="f9409-151">`-Auto` Switch - The `-Auto` switch would provide an "opt-in" way for users to _default all the things_ while maintaining the integrity of required parameters in the mainline path.</span></span>

### <a name="feature-specific-switches"></a><span data-ttu-id="f9409-152">Funktionsspecifika switchar</span><span class="sxs-lookup"><span data-stu-id="f9409-152">Feature-specific switches</span></span>

<span data-ttu-id="f9409-153">Scenariet ”Skapa webbapp” skulle till exempel kunna ha en `-Git`- eller `-AddRemote`-switch som automatiskt skulle lägga till en ”azure” fjärrlagringsplats till en befintlig git-lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="f9409-153">For example, the "Create web app" scenario might have a `-Git` or `-AddRemote` switch that would automatically add an "azure" remote to an existing git repository.</span></span>

- <span data-ttu-id="f9409-154">Inställningsbara standardvärden – Användare bör ha möjlighet att ange vissa allmänt förekommande parametrar som standardvärden, `-ResourceGroupName` och `-Location`.</span><span class="sxs-lookup"><span data-stu-id="f9409-154">Settable Defaults - Users should have the ability to default certain ubiquitous parameters like `-ResourceGroupName` and `-Location`.</span></span>

- <span data-ttu-id="f9409-155">Storleksstandard – Resursers ”storlekar” kan vara förvirrande för användarna eftersom många resursproviders använder olika namn (till exempel ”Standard\_DS1\_v2” eller ”S1”).</span><span class="sxs-lookup"><span data-stu-id="f9409-155">Size Defaults - Resource "sizes" can be confusing to users since many Resource Providers use different names (for example, "Standard\_DS1\_v2" or "S1").</span></span> <span data-ttu-id="f9409-156">Dock är de flesta användare mer intresserade av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="f9409-156">However, most users care more about cost.</span></span> <span data-ttu-id="f9409-157">Därför vore det praktiskt att definiera ”universella” storlekar utifrån ett prissättningsschema.</span><span class="sxs-lookup"><span data-stu-id="f9409-157">Therefore, it makes sense to define "universal" sizes based on a pricing schedule.</span></span> <span data-ttu-id="f9409-158">Användare kan välja en viss storlek eller låta Azure PowerShell välja det _bästa alternativet_ utifrån resursbudgeten.</span><span class="sxs-lookup"><span data-stu-id="f9409-158">Users can choose a specific size or let Azure PowerShell choose the _best option_ based on the resource the budget.</span></span>

- <span data-ttu-id="f9409-159">Utdataformat – Azure PowerShell returnerar för närvarande `PSObject` och det finns lite konsolutdata.</span><span class="sxs-lookup"><span data-stu-id="f9409-159">Output Format - Azure PowerShell currently returns `PSObject`s and there is little console output.</span></span> <span data-ttu-id="f9409-160">Azure PowerShell kanske behöver visa en del information för användaren om vilka ”smarta standardvärden” som används.</span><span class="sxs-lookup"><span data-stu-id="f9409-160">Azure PowerShell may need to display some information to the user regarding the "smart defaults" used.</span></span>