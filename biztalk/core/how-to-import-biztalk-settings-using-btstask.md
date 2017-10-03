---
title: "インポートまたは BTSTask を使用して BizTalk の設定をエクスポート |Microsoft ドキュメント"
description: "ImportSettings または ExportSettings BTSTask コマンドを使用して、環境から BizTalk Server 内の別の設定を移動します。"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3fdd8c9-3534-4c11-8acc-6cb6f5bf0989
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99aecaea767133fc5f3cb77d38dc174b09733674
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-btstask-to-import-or-export-biztalk-settings"></a><span data-ttu-id="58273-103">BTSTask を使用して、インポートまたは BizTalk の設定をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="58273-103">Use BTSTask to import or export BizTalk settings</span></span>

## <a name="overview"></a><span data-ttu-id="58273-104">概要</span><span class="sxs-lookup"><span data-stu-id="58273-104">Overview</span></span>
<span data-ttu-id="58273-105">BTSTask コマンドライン ユーティリティを使用して、1 つの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境から設定をエクスポートし、その設定を別の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境にインポートすることによって、ソリューションにかかる時間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="58273-105">Using the BTSTask command-line utility, you can export the settings from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment and import them to another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, thereby reducing the overall time-to-solution.</span></span> <span data-ttu-id="58273-106">これは、管理者がステージング環境で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパフォーマンスを調整し、適正な結果が得られた時点で設定を実稼働環境にインポートする場合、特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="58273-106">This is especially useful in scenarios where the administrators try to tune [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance in a staging environment, and upon achieving the desired results, they can import the settings into a production environment.</span></span> 

<span data-ttu-id="58273-107">このトピックの内容をインポートまたは 1 つの環境から BizTalk Server 設定を使用して別にエクスポートする手順について説明**BTSTask.exe**です。</span><span class="sxs-lookup"><span data-stu-id="58273-107">This topic lists the steps to import or export the BizTalk Server settings from one environment to another using **BTSTask.exe**.</span></span>  


## <a name="import-biztalk-settings"></a><span data-ttu-id="58273-108">BizTalk 設定をインポートします。</span><span class="sxs-lookup"><span data-stu-id="58273-108">Import BizTalk settings</span></span> 
> [!IMPORTANT]
>  <span data-ttu-id="58273-109">特定の環境から BizTalk 設定をインポートするには、その設定をエクスポートして XML ファイルに保存しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="58273-109">To import the BizTalk settings from a certain environment, you should have already exported and saved those settings in an XML file.</span></span> <span data-ttu-id="58273-110">設定のエクスポートの詳細については、次を参照してください。[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)または**BTSTask を使用して BizTalk の設定のエクスポート**(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="58273-110">For more information about exporting the settings, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) or **Export BizTalk Settings Using BTSTask** (in this topic).</span></span>  
  
 <span data-ttu-id="58273-111">XML ファイルをインポートすることで、対象コンピューターで必要な BizTalk Server 設定をレプリケートできます。</span><span class="sxs-lookup"><span data-stu-id="58273-111">By importing the XML file, you can replicate the required BizTalk Server settings on the target machine.</span></span> <span data-ttu-id="58273-112">使用して、 **BTSTask.exe**グループ、ホスト、およびホスト インスタンス設定をインポートして、そのプロパティを相互にマップできます。</span><span class="sxs-lookup"><span data-stu-id="58273-112">Using the **BTSTask.exe**, you can import the Group, Host, and Host Instance settings and map the properties of one to another.</span></span> <span data-ttu-id="58273-113">次に設定をインポートする際に必要な前提条件を示します。</span><span class="sxs-lookup"><span data-stu-id="58273-113">Following are the necessary assumptions for importing the settings:</span></span>  
  
-   <span data-ttu-id="58273-114">BizTalk Server 設定は同様のトポロジ間でインポートできます。</span><span class="sxs-lookup"><span data-stu-id="58273-114">You can import the BizTalk Server settings across similar topologies.</span></span>  
  
-   <span data-ttu-id="58273-115">送信元のホストとホスト インスタンスを送信先の対応するホストとホスト インスタンスにマップできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="58273-115">You should be able to map the source Host and Host Instances to the destination counterparts.</span></span>  
  
-   <span data-ttu-id="58273-116">インポート先環境には、インポート元環境と (同じかまたは) 似たハードウェアがあります。</span><span class="sxs-lookup"><span data-stu-id="58273-116">The destination environment has hardware similar (if not identical) to the source environment.</span></span> <span data-ttu-id="58273-117">一部の設定は基礎となるハードウェアに依存しているため、これは重要です。</span><span class="sxs-lookup"><span data-stu-id="58273-117">This is essential as some of the settings depend on the underlying hardware.</span></span>  
  
### <a name="importsettings-command"></a><span data-ttu-id="58273-118">ImportSettings コマンド</span><span class="sxs-lookup"><span data-stu-id="58273-118">ImportSettings command</span></span> 
 <span data-ttu-id="58273-119">使用することができます、 **ImportSettings**を送信先の環境に、ソース環境から BizTalk Server の設定をインポートする BTSTask コマンド。</span><span class="sxs-lookup"><span data-stu-id="58273-119">You can use the **ImportSettings** BTSTask command to import BizTalk Server settings from the source environment to destination environment.</span></span> <span data-ttu-id="58273-120">参照してください[ImportSettings コマンド](../core/importsettings-command.md)詳細です。</span><span class="sxs-lookup"><span data-stu-id="58273-120">See [ImportSettings Command](../core/importsettings-command.md) for specific details.</span></span>  
  
 <span data-ttu-id="58273-121">送信元ホストから送信先ホストおよび送信元ホスト インスタンスから送信先ホスト インスタンスへのマッピングは、次のように定義できます。</span><span class="sxs-lookup"><span data-stu-id="58273-121">You can define the mapping from a source host to a destination host and/or a source host instance to a destination host instance as shown:</span></span>  
  
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
  
 <span data-ttu-id="58273-122">マップ ファイルには、"hostname:machinename"ホスト インスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="58273-122">In a map file, enter a host instance as 'HostName:MachineName'.</span></span> <span data-ttu-id="58273-123">たとえば、"Host1:Server1" は、コンピューター "Server1" で実行中の (または存在している) ホスト "Host1" を意味します。</span><span class="sxs-lookup"><span data-stu-id="58273-123">For example: "Host1:Server1" means the instance of host 'Host1' which is running (or present) on machine 'Server1".</span></span>  
  
 <span data-ttu-id="58273-124">1: n のソースを移行先のマッピングを入力するには、セミコロンで区切ったリストを使用します。</span><span class="sxs-lookup"><span data-stu-id="58273-124">To enter 1:n source to destination mappings, use a semicolon-separated list.</span></span> <span data-ttu-id="58273-125">例:</span><span class="sxs-lookup"><span data-stu-id="58273-125">For example:</span></span>  
  
```  
SourceHost Name="SourceHost1"   
......DestinationHosts   
............DestHost1;DestHost2;DestHost3   
....../DestinationHosts   
/SourceHost  
```  
  
 <span data-ttu-id="58273-126">ホスト インスタンスをマップするには、対応するホスト マッピングも作成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="58273-126">Only those host-instances can be mapped for which the corresponding host mapping has also been created.</span></span> <span data-ttu-id="58273-127">ホスト マッピングで "SourceHost1" が "DestinationHost1" にマップされている場合、"DestinationHost1" のインスタンス (ある場合) は "SourceHost1" のインスタンス (ある場合) にのみマップできます。</span><span class="sxs-lookup"><span data-stu-id="58273-127">If 'SourceHost1' has been mapped to 'DestinationHost1' in host mappings, the instances (if any) of 'DestinationHost1' can be mapped only to the instances (if any) of 'SourceHost1'.</span></span> <span data-ttu-id="58273-128">この制約は UI インポート ウィザードにより処理されます。</span><span class="sxs-lookup"><span data-stu-id="58273-128">The UI Import Wizard takes care of this constraint.</span></span> <span data-ttu-id="58273-129">マップ ファイルにはこのことを明示的に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58273-129">You would need to explicitly write it in the map file.</span></span>  


## <a name="export-biztalk-settings"></a><span data-ttu-id="58273-130">BizTalk 設定をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="58273-130">Export BizTalk settings</span></span>  

<span data-ttu-id="58273-131">BizTalk の設定をエクスポートする方法はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="58273-131">There are a couple of ways to export the BizTalk settings:</span></span> 

1. <span data-ttu-id="58273-132">使用して、 **ExportSettings** XML ファイルをソース環境の BizTalk Server の設定をエクスポートする BTSTask コマンド。</span><span class="sxs-lookup"><span data-stu-id="58273-132">Use the **ExportSettings** BTSTask command to export the BizTalk Server settings of the source environment to an XML file.</span></span> <span data-ttu-id="58273-133">参照してください[ExportSettings コマンド](../core/exportsettings-command.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="58273-133">See [ExportSettings Command](../core/exportsettings-command.md) for more details.</span></span>  

2.  <span data-ttu-id="58273-134">BizTalk Server 管理コンソールで、設定ダッシュ ボードを使用します。</span><span class="sxs-lookup"><span data-stu-id="58273-134">Use the Settings Dashboard in BizTalk Server Administration.</span></span> <span data-ttu-id="58273-135">参照してください[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)手順については、します。</span><span class="sxs-lookup"><span data-stu-id="58273-135">See [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) for the steps.</span></span>

 
> [!TIP]
>  <span data-ttu-id="58273-136">ターゲット環境に XML ファイルに BizTalk Server の設定を適用する方法については、次を参照してください。[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)です。</span><span class="sxs-lookup"><span data-stu-id="58273-136">For information about how the BizTalk Server settings in an XML file are applied to the target environment, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="58273-137">参照</span><span class="sxs-lookup"><span data-stu-id="58273-137">See Also</span></span>  
 [<span data-ttu-id="58273-138">BizTalk Server の自動化のパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="58273-138">Automate BizTalk Server Performance Tuning</span></span>](../core/automating-biztalk-server-performance-tuning.md)