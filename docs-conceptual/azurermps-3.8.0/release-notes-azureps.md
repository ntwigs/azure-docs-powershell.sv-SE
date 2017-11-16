---
title: "Ändringslogg för Azure PowerShell | Microsoft Docs"
description: "Det här är en historik över de ändringar som gjorts i den senaste versionen av Azure PowerShell."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.service: azure-powershell
ms.product: azure
ms.devlang: powershell
ms.topic: conceptual
ms.workload: 
ms.date: 05/18/2017
ms.openlocfilehash: 04f89e8d47d0825d46cb1b8817efbcc0cafa0acd
ms.sourcegitcommit: b256bf48e15ee98865de0fae50e7b81878b03a54
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2017
---
# <a name="release-notes"></a><span data-ttu-id="52685-103">Viktig information</span><span class="sxs-lookup"><span data-stu-id="52685-103">Release notes</span></span>

<span data-ttu-id="52685-104">Det här är en lista över ändringar som har gjorts i Azure PowerShell i den här versionen.</span><span class="sxs-lookup"><span data-stu-id="52685-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <a name="version-380"></a><span data-ttu-id="52685-105">Version 3.8.0</span><span class="sxs-lookup"><span data-stu-id="52685-105">Version 3.8.0</span></span>
* <span data-ttu-id="52685-106">Compute</span><span class="sxs-lookup"><span data-stu-id="52685-106">Compute</span></span>
  - <span data-ttu-id="52685-107">Fel i Get-*-cmdletar har åtgärdats så att det går att hämta flera sidor med data (mer än 120 objekt)</span><span class="sxs-lookup"><span data-stu-id="52685-107">Fix bug in Get-* cmdlets, to allow retrieving multiple pages of data (more than 120 items)</span></span>
* <span data-ttu-id="52685-108">DataLakeAnalytics</span><span class="sxs-lookup"><span data-stu-id="52685-108">DataLakeAnalytics</span></span>
  - <span data-ttu-id="52685-109">Hjälpen för vissa kommandon har åtgärdats så att den innehåller rätt ord och exempel.</span><span class="sxs-lookup"><span data-stu-id="52685-109">Fix help for some commands to have the proper verbage and examples.</span></span>
* <span data-ttu-id="52685-110">DataLakeStore</span><span class="sxs-lookup"><span data-stu-id="52685-110">DataLakeStore</span></span>
  - <span data-ttu-id="52685-111">Tillagt stöd för start och slut för `Get-AzureRMDataLakeStoreItemContent`-cmdleten.</span><span class="sxs-lookup"><span data-stu-id="52685-111">Add support for head and tail to the `Get-AzureRMDataLakeStoreItemContent` cmdlet.</span></span> <span data-ttu-id="52685-112">Detta gör att de översta N eller sista N nya radavgränsade raderna visas.</span><span class="sxs-lookup"><span data-stu-id="52685-112">This enables returning the top N or last N new line delimited rows to be displayed.</span></span>
* <span data-ttu-id="52685-113">HDInsight</span><span class="sxs-lookup"><span data-stu-id="52685-113">HDInsight</span></span>
  - <span data-ttu-id="52685-114">Stöd för RServer-klustertypen har lagts till</span><span class="sxs-lookup"><span data-stu-id="52685-114">Added support for RServer cluster type</span></span>
    + <span data-ttu-id="52685-115">Edgenode VM-storlek kan anges för RServer-kluster i New-AzureRmHDInsightCluster eller New-AzureRmHDInsightClusterConfig</span><span class="sxs-lookup"><span data-stu-id="52685-115">Edgenode VM size can be specified for RServer cluster in New-AzureRmHDInsightCluster or New-AzureRmHDInsightClusterConfig</span></span>
    + <span data-ttu-id="52685-116">RServer är nu ett konfigurationsalternativ i Add-AzureRmHDInsightConfigValues.</span><span class="sxs-lookup"><span data-stu-id="52685-116">RServer is now a configuration option in Add-AzureRmHDInsightConfigValues.</span></span> <span data-ttu-id="52685-117">Det gör att RStudio-flaggan kan anges för att indikera att R Studio måste installeras.</span><span class="sxs-lookup"><span data-stu-id="52685-117">It allows for RStudio flag to be set to indicate that R Studio installation should be done.</span></span>
* <span data-ttu-id="52685-118">LogicApp</span><span class="sxs-lookup"><span data-stu-id="52685-118">LogicApp</span></span>
  - <span data-ttu-id="52685-119">Cmdletarna Set-AzureRmIntegrationAccountSchema och Set-AzureRmIntegrationAccountMap har åtgärdats angående ett contentlink-problem (både content och contentlink angavs vilket resulterade i ett uppdateringsfel).</span><span class="sxs-lookup"><span data-stu-id="52685-119">Set-AzureRmIntegrationAccountSchema and Set-AzureRmIntegrationAccountMap cmdlets are fixed for the contentlink issue(Both content and contentlink were set resulting in update failure).</span></span>
* <span data-ttu-id="52685-120">Nätverk</span><span class="sxs-lookup"><span data-stu-id="52685-120">Network</span></span>
  - <span data-ttu-id="52685-121">Stöd för nya funktioner för brandvägg för webbaserade program har lagts till i Application Gateways</span><span class="sxs-lookup"><span data-stu-id="52685-121">Added support for new web application firewall features to Application Gateways</span></span>
    + <span data-ttu-id="52685-122">New-AzureRmApplicationGatewayFirewallDisabledRuleGroupConfig har lagts till</span><span class="sxs-lookup"><span data-stu-id="52685-122">Added New-AzureRmApplicationGatewayFirewallDisabledRuleGroupConfig</span></span>
    + <span data-ttu-id="52685-123">Get-AzureRmApplicationGatewayAvailableWafRuleSets har lagts till (alias: List-AzureRmApplicationGatewayAvailableWafRuleSets)</span><span class="sxs-lookup"><span data-stu-id="52685-123">Added Get-AzureRmApplicationGatewayAvailableWafRuleSets (Alias: List-AzureRmApplicationGatewayAvailableWafRuleSets)</span></span>
    + <span data-ttu-id="52685-124">New-AzureRmApplicationGatewayWebApplicationFirewallConfiguration har uppdaterats: Parametrarna -RuleSetType, -RuleSetVersion och -DisabledRuleGroups har lagts till</span><span class="sxs-lookup"><span data-stu-id="52685-124">Updated New-AzureRmApplicationGatewayWebApplicationFirewallConfiguration: Added parameter -RuleSetType -RuleSetVersion and -DisabledRuleGroups</span></span>
    + <span data-ttu-id="52685-125">Set-AzureRmApplicationGatewayWebApplicationFirewallConfiguration har uppdaterats: Parametrarna -RuleSetType, -RuleSetVersion och -DisabledRuleGroups har lagts till</span><span class="sxs-lookup"><span data-stu-id="52685-125">Updated Set-AzureRmApplicationGatewayWebApplicationFirewallConfiguration: Added parameter -RuleSetType -RuleSetVersion and -DisabledRuleGroups</span></span>
  - <span data-ttu-id="52685-126">Stöd för IPSec-principer har lagts till i gatewayanslutningar för virtuella nätverk</span><span class="sxs-lookup"><span data-stu-id="52685-126">Added support for IPSec policies to Virtual Network Gateway Connections</span></span>
  - <span data-ttu-id="52685-127">New-AzureRmIpsecPolicy har lagts till</span><span class="sxs-lookup"><span data-stu-id="52685-127">Added New-AzureRmIpsecPolicy</span></span>
  - <span data-ttu-id="52685-128">New-AzureRmVirtualNetworkGatewayConnection har uppdaterats: Parametrarna -IpsecPolicies och -UsePolicyBasedTrafficSelectors har lagts till</span><span class="sxs-lookup"><span data-stu-id="52685-128">Updated New-AzureRmVirtualNetworkGatewayConnection: Added parameter -IpsecPolicies and -UsePolicyBasedTrafficSelectors</span></span>
* <span data-ttu-id="52685-129">Profil</span><span class="sxs-lookup"><span data-stu-id="52685-129">Profile</span></span>
  - <span data-ttu-id="52685-130">*Föråldrad*: Save-AzureRmProfile har bytt namn till Save-AzureRmContext. Det finns ett alias till det gamla cmdletnamnet och det kommer att tas bort i nästa version.</span><span class="sxs-lookup"><span data-stu-id="52685-130">*Obsolete*: Save-AzureRmProfile is renamed to Save-AzureRmContext, there is an alias to the old cmdlet name, the alias will be removed in the next release.</span></span>
  - <span data-ttu-id="52685-131">*Föråldrad*: Select-AzureRmProfile har bytt namn till Import-AzureRmContext. Det finns ett alias till det gamla cmdletnamnet och det kommer att tas bort i nästa version.</span><span class="sxs-lookup"><span data-stu-id="52685-131">*Obsolete*: Select-AzureRmProfile is renamed to Import-AzureRmContext, there is an alias to the old cmdlet name, the alias will be removed in the next release.</span></span>
  - <span data-ttu-id="52685-132">Utdatatyperna PSAzureContext och PSAzureProfile för profil-cmdletar kommer att ändras i nästa version.</span><span class="sxs-lookup"><span data-stu-id="52685-132">The PSAzureContext and PSAzureProfile output types of profile cmdlets will be changed in the next release.</span></span>
  - <span data-ttu-id="52685-133">Cmdleten Save-AzureRmContext kommer inte att ha någon OutputType i nästa version.</span><span class="sxs-lookup"><span data-stu-id="52685-133">The Save-AzureRmContext cmdlet will have no OutputType in the next release.</span></span>
  - <span data-ttu-id="52685-134">Ett fel har åtgärdats i gemensam cmdlet-kod för att använda en FIPS-kompatibel algoritm för datahashvärden: https://github.com/Azure/azure-powershell/issues/3651</span><span class="sxs-lookup"><span data-stu-id="52685-134">Fix bug in cmdlet common code to use FIPS-compliant algorithm for data hashes: https://github.com/Azure/azure-powershell/issues/3651</span></span>
* <span data-ttu-id="52685-135">SQL</span><span class="sxs-lookup"><span data-stu-id="52685-135">Sql</span></span>
  - <span data-ttu-id="52685-136">Fel har åtgärdats för cmdletar för Azure-redundansgrupper</span><span class="sxs-lookup"><span data-stu-id="52685-136">Bug fixes on Azure Failover Group Cmdlets</span></span>
  - <span data-ttu-id="52685-137">Korrigering för åtgärdsavsökning</span><span class="sxs-lookup"><span data-stu-id="52685-137">Fix for operation polling</span></span>
  - <span data-ttu-id="52685-138">GracePeriodWithDataLossHour-värdet har åtgärdats när Manuell anges för FailoverPolicy</span><span class="sxs-lookup"><span data-stu-id="52685-138">Fix GracePeriodWithDataLossHour value when setting FailoverPolicy to Manual</span></span>
* <span data-ttu-id="52685-139">TrafficManager</span><span class="sxs-lookup"><span data-stu-id="52685-139">TrafficManager</span></span>
  - <span data-ttu-id="52685-140">Stöd för trafikroutningsmetoden Geographic</span><span class="sxs-lookup"><span data-stu-id="52685-140">Support for the Geographic traffic routing method</span></span>
    + <span data-ttu-id="52685-141">Nytt värde (Geographic) för parametern TrafficRoutingMethod i New-AzureRmTrafficManagerProfile</span><span class="sxs-lookup"><span data-stu-id="52685-141">New value 'Geographic' for the TrafficRoutingMethod parameter of New-AzureRmTrafficManagerProfile</span></span>
    + <span data-ttu-id="52685-142">Ny parameter (GeoMapping) för New-AzureRmTrafficManagerEndpoint och Add-AzureRmTrafficManagerEndpointConfig</span><span class="sxs-lookup"><span data-stu-id="52685-142">New parameter 'GeoMapping' for the New-AzureRmTrafficManagerEndpoint and Add-AzureRmTrafficManagerEndpointConfig</span></span>
    + <span data-ttu-id="52685-143">Omdirigering har åtgärdats för Get-AzureRmTrafficManagerProfile när den returnerar en samling profiler</span><span class="sxs-lookup"><span data-stu-id="52685-143">Fix piping for Get-AzureRmTrafficManagerProfile when it returns a collection of profiles</span></span>
* <span data-ttu-id="52685-144">ServiceManagement</span><span class="sxs-lookup"><span data-stu-id="52685-144">ServiceManagement</span></span>
  - <span data-ttu-id="52685-145">Restart-AzureVM: Parametern InitiateMaintenance har lagts till för att utföra underhåll under omstart av virtuella datorer.</span><span class="sxs-lookup"><span data-stu-id="52685-145">Restart-AzureVM: Added InitiateMaintenance parameter for performing maintenance during VM restart.</span></span>
  - <span data-ttu-id="52685-146">Get-AzureVM: Fält för underhållsstatus har lagts till.</span><span class="sxs-lookup"><span data-stu-id="52685-146">Get-AzureVM: Added Maintenance Status field.</span></span>
  - <span data-ttu-id="52685-147">Nya cmdletar har lagts till för uppgradering av Recovery Services-valv</span><span class="sxs-lookup"><span data-stu-id="52685-147">Added new cmdlets to support Recovery Services vault upgrade</span></span>
    + <span data-ttu-id="52685-148">Test-AzureRecoveryServicesVaultUpgrade</span><span class="sxs-lookup"><span data-stu-id="52685-148">Test-AzureRecoveryServicesVaultUpgrade</span></span>
    + <span data-ttu-id="52685-149">Invoke-AzureRecoveryServicesVaultUpgrade</span><span class="sxs-lookup"><span data-stu-id="52685-149">Invoke-AzureRecoveryServicesVaultUpgrade</span></span>