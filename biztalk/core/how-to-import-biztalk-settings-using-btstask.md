---
title: インポートまたは BTSTask を使用して BizTalk の設定のエクスポート |Microsoft Docs
description: ImportSettings または ExportSettings BTSTask コマンドを使用して環境から BizTalk Server 内の別の設定を移動します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3fdd8c9-3534-4c11-8acc-6cb6f5bf0989
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19143ff1f5da248b3924ce87d7dc2e686bdd80d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384964"
---
# <a name="use-btstask-to-import-or-export-biztalk-settings"></a><span data-ttu-id="ddb4e-103">BTSTask を使用して、インポートまたは BizTalk の設定をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="ddb4e-103">Use BTSTask to import or export BizTalk settings</span></span>

## <a name="overview"></a><span data-ttu-id="ddb4e-104">概要</span><span class="sxs-lookup"><span data-stu-id="ddb4e-104">Overview</span></span>
<span data-ttu-id="ddb4e-105">BTSTask コマンド ライン ユーティリティを使用してから、設定をエクスポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境別にインポートすることと[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、全体的なソリューションに時間が減少します。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-105">Using the BTSTask command-line utility, you can export the settings from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment and import them to another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, thereby reducing the overall time-to-solution.</span></span> <span data-ttu-id="ddb4e-106">これは、管理者が調整しようとした位置のシナリオで特に役立ちます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス、運用環境に設定をインポートできます、ステージング環境では、目的の結果を実現するために、します。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-106">This is especially useful in scenarios where the administrators try to tune [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance in a staging environment, and upon achieving the desired results, they can import the settings into a production environment.</span></span> 

<span data-ttu-id="ddb4e-107">このトピックでは、インポートまたはを使用して 1 つの環境から BizTalk Server 設定をエクスポートする手順を示します**BTSTask.exe**します。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-107">This topic lists the steps to import or export the BizTalk Server settings from one environment to another using **BTSTask.exe**.</span></span>  


## <a name="import-biztalk-settings"></a><span data-ttu-id="ddb4e-108">BizTalk の設定のインポート</span><span class="sxs-lookup"><span data-stu-id="ddb4e-108">Import BizTalk settings</span></span> 
> [!IMPORTANT]
>  <span data-ttu-id="ddb4e-109">特定の環境から BizTalk 設定をインポートするには、必要がありますが既にエクスポートして XML ファイルにこれらの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-109">To import the BizTalk settings from a certain environment, you should have already exported and saved those settings in an XML file.</span></span> <span data-ttu-id="ddb4e-110">設定のエクスポートの詳細については、次を参照してください。[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)または**BTSTask を使用して BizTalk の設定のエクスポート**(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-110">For more information about exporting the settings, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) or **Export BizTalk Settings Using BTSTask** (in this topic).</span></span>  
  
 <span data-ttu-id="ddb4e-111">XML ファイルをインポートすることによって、ターゲット コンピューターで必要な BizTalk Server 設定をレプリケートできます。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-111">By importing the XML file, you can replicate the required BizTalk Server settings on the target machine.</span></span> <span data-ttu-id="ddb4e-112">使用して、 **BTSTask.exe**グループ、ホスト、およびホスト インスタンスの設定をインポートし、そのプロパティを相互にマップします。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-112">Using the **BTSTask.exe**, you can import the Group, Host, and Host Instance settings and map the properties of one to another.</span></span> <span data-ttu-id="ddb4e-113">以下は、設定をインポートするための必要な前提条件です。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-113">Following are the necessary assumptions for importing the settings:</span></span>  
  
-   <span data-ttu-id="ddb4e-114">同様のトポロジ間で BizTalk Server 設定をインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-114">You can import the BizTalk Server settings across similar topologies.</span></span>  
  
-   <span data-ttu-id="ddb4e-115">送信先の対応するソース ホストとホスト インスタンスにマップできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-115">You should be able to map the source Host and Host Instances to the destination counterparts.</span></span>  
  
-   <span data-ttu-id="ddb4e-116">移行先の環境に似たハードウェア (同じ) かソース環境。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-116">The destination environment has hardware similar (if not identical) to the source environment.</span></span> <span data-ttu-id="ddb4e-117">これは、基になるハードウェアに依存して、設定の一部は非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-117">This is essential as some of the settings depend on the underlying hardware.</span></span>  
  
### <a name="importsettings-command"></a><span data-ttu-id="ddb4e-118">ImportSettings コマンド</span><span class="sxs-lookup"><span data-stu-id="ddb4e-118">ImportSettings command</span></span> 
 <span data-ttu-id="ddb4e-119">使用することができます、 **ImportSettings**ソース環境から送信先の環境に BizTalk Server の設定をインポートする BTSTask コマンド。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-119">You can use the **ImportSettings** BTSTask command to import BizTalk Server settings from the source environment to destination environment.</span></span> <span data-ttu-id="ddb4e-120">参照してください[ImportSettings コマンド](../core/importsettings-command.md)に関する特定の詳細。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-120">See [ImportSettings Command](../core/importsettings-command.md) for specific details.</span></span>  
  
 <span data-ttu-id="ddb4e-121">移行先ホストにソース ホストまたはソース ホストのインスタンスから示すように、宛先ホスト インスタンスへのマッピングを定義できます。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-121">You can define the mapping from a source host to a destination host and/or a source host instance to a destination host instance as shown:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SettingsMap>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <HostMappings>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="BizTalkServerApplication">  
  <DestinationHosts>BizTalkServerApplication</DestinationHosts>   
  </SourceHost>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="BizTalkServerIsolatedHost">  
  <DestinationHosts>BizTalkServerIsolatedHost</DestinationHosts>   
  </SourceHost>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="Host1">  
  <DestinationHosts>Host2</DestinationHosts>   
  </SourceHost>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="Host2">  
  <DestinationHosts>Host1;Host3;Host4;Host5</DestinationHosts>   
  </SourceHost>  
  </HostMappings>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <HostInstanceMappings>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHostInstance Name="BizTalkServerApplication:COMPUTER_NAME1">  
  <DestinationHostInstances>BizTalkServerApplication:COMPUTER_NAME2</DestinationHostInstances>   
  </SourceHostInstance>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHostInstance Name="Host1:COMPUTER_NAME1">  
  <DestinationHostInstances>Host2:COMPUTER_NAME2;Host3:COMPUTER_NAME3;Host4:COMPUTER_NAME4;Host5:COMPUTER_NAME5</DestinationHostInstances>   
  </SourceHostInstance>  
  </HostInstanceMappings>  
  </SettingsMap>  
  
```  
  
 <span data-ttu-id="ddb4e-122">マップ ファイルの場合は、"hostname:machinename"のホスト インスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-122">In a map file, enter a host instance as 'HostName:MachineName'.</span></span> <span data-ttu-id="ddb4e-123">例 :"Host1:Server1"ホスト"Host1 が実行されている (または提示) コンピューターのインスタンスを意味する ' Server1"。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-123">For example: "Host1:Server1" means the instance of host 'Host1' which is running (or present) on machine 'Server1".</span></span>  
  
 <span data-ttu-id="ddb4e-124">1: n のソース宛先へのマッピングからを入力するには、セミコロンで区切ったリストを使用します。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-124">To enter 1:n source to destination mappings, use a semicolon-separated list.</span></span> <span data-ttu-id="ddb4e-125">例 :</span><span class="sxs-lookup"><span data-stu-id="ddb4e-125">For example:</span></span>  
  
```  
SourceHost Name="SourceHost1"   
......DestinationHosts   
............DestHost1;DestHost2;DestHost3   
....../DestinationHosts   
/SourceHost  
```  
  
 <span data-ttu-id="ddb4e-126">対応するホスト マッピングも作成され、ホストのインスタンスのみをマップできます。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-126">Only those host-instances can be mapped for which the corresponding host mapping has also been created.</span></span> <span data-ttu-id="ddb4e-127">SourceHost1"は、ホスト マッピングで DestinationHost1"にマップされているが場合、DestinationHost1 のインスタンス (ある場合) が SourceHost1"のインスタンス (ある場合) にのみマップできます。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-127">If 'SourceHost1' has been mapped to 'DestinationHost1' in host mappings, the instances (if any) of 'DestinationHost1' can be mapped only to the instances (if any) of 'SourceHost1'.</span></span> <span data-ttu-id="ddb4e-128">この制約の UI のインポート ウィザードによって行われます。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-128">The UI Import Wizard takes care of this constraint.</span></span> <span data-ttu-id="ddb4e-129">マップ ファイルで明示的に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-129">You would need to explicitly write it in the map file.</span></span>  


## <a name="export-biztalk-settings"></a><span data-ttu-id="ddb4e-130">BizTalk 設定をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-130">Export BizTalk settings</span></span>  

<span data-ttu-id="ddb4e-131">複数の BizTalk 設定をエクスポートする方法があります。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-131">There are a couple of ways to export the BizTalk settings:</span></span> 

1. <span data-ttu-id="ddb4e-132">使用して、 **ExportSettings**ソース環境の BizTalk Server 設定を XML ファイルにエクスポートに BTSTask コマンド。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-132">Use the **ExportSettings** BTSTask command to export the BizTalk Server settings of the source environment to an XML file.</span></span> <span data-ttu-id="ddb4e-133">参照してください[ExportSettings コマンド](../core/exportsettings-command.md)の詳細。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-133">See [ExportSettings Command](../core/exportsettings-command.md) for more details.</span></span>  

2.  <span data-ttu-id="ddb4e-134">BizTalk Server 管理の設定ダッシュ ボードを使用します。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-134">Use the Settings Dashboard in BizTalk Server Administration.</span></span> <span data-ttu-id="ddb4e-135">参照してください[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)手順については、します。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-135">See [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) for the steps.</span></span>

 
> [!TIP]
>  <span data-ttu-id="ddb4e-136">XML ファイルに BizTalk Server の設定がターゲット環境に適用する方法については、次を参照してください。[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)します。</span><span class="sxs-lookup"><span data-stu-id="ddb4e-136">For information about how the BizTalk Server settings in an XML file are applied to the target environment, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ddb4e-137">参照</span><span class="sxs-lookup"><span data-stu-id="ddb4e-137">See Also</span></span>  
 [<span data-ttu-id="ddb4e-138">BizTalk Server パフォーマンス チューニングの自動化</span><span class="sxs-lookup"><span data-stu-id="ddb4e-138">Automate BizTalk Server Performance Tuning</span></span>](../core/automating-biztalk-server-performance-tuning.md)