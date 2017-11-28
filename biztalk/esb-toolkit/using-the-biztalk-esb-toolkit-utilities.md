---
title: "BizTalk ESB Toolkit ユーティリティを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2dc05ac-831a-44e1-bd44-e41398552ab1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36902e2c5e90ce1b02f40f6994f150fa4c421c7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-biztalk-esb-toolkit-utilities"></a><span data-ttu-id="ccff8-102">BizTalk ESB Toolkit ユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="ccff8-102">Using the BizTalk ESB Toolkit Utilities</span></span>
<span data-ttu-id="ccff8-103">このセクションの一部として含まれているさまざまなユーティリティの説明、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ccff8-103">This section describes various utilities included as part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="ccff8-104">**ESB Itinerary インポート ユーティリティ**</span><span class="sxs-lookup"><span data-stu-id="ccff8-104">**ESB Itinerary Import Utility**</span></span>  
  
 <span data-ttu-id="ccff8-105">このユーティリティは、\bin ディレクトリの下にある、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] EsbImportUtil.exe という名前です。</span><span class="sxs-lookup"><span data-stu-id="ccff8-105">This utility is located under the \bin directory of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and is named EsbImportUtil.exe.</span></span> <span data-ttu-id="ccff8-106">このユーティリティを使用して、発行または ESBItineraryDB データベースに XML 旅程をデプロイすることができます。</span><span class="sxs-lookup"><span data-stu-id="ccff8-106">This utility can be used to publish or deploy the itinerary XML into the ESBItineraryDB database.</span></span>  
  
 <span data-ttu-id="ccff8-107">ユーティリティの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ccff8-107">The syntax for the utility is as follows:</span></span>  
  
```  
>EsbImportUtil <Parameter1> <Value> <parameter2> <Value>...  
```  
  
 <span data-ttu-id="ccff8-108">さまざまなパラメーターを受け入れる次に示します。</span><span class="sxs-lookup"><span data-stu-id="ccff8-108">The various parameters it can accept are the following:</span></span>  
  
 <span data-ttu-id="ccff8-109">/?:\<パラメーターのヘルプを表示 ></span><span class="sxs-lookup"><span data-stu-id="ccff8-109">/?: \<Show the parameters help></span></span>  
  
 <span data-ttu-id="ccff8-110">/f:\<行程 xml ファイルのパス ></span><span class="sxs-lookup"><span data-stu-id="ccff8-110">/f: \<Itinerary xml file path></span></span>  
  
 <span data-ttu-id="ccff8-111">展開/c\<発行 &#124; 展開 ></span><span class="sxs-lookup"><span data-stu-id="ccff8-111">/c: \<published &#124; deployed></span></span>  
  
 <span data-ttu-id="ccff8-112">/n:\<行程の既定の名前 ></span><span class="sxs-lookup"><span data-stu-id="ccff8-112">/n: \<Default Itinerary name></span></span>  
  
 <span data-ttu-id="ccff8-113">/v:\<行程の既定のバージョン ('<major.minor' の形式) ></span><span class="sxs-lookup"><span data-stu-id="ccff8-113">/v: \<Default Itinerary version (format 'major.minor')></span></span>  
  
 <span data-ttu-id="ccff8-114">/o:\<サイレント上書き ></span><span class="sxs-lookup"><span data-stu-id="ccff8-114">/o: \<Silent overwrite></span></span>  
  
 <span data-ttu-id="ccff8-115">このユーティリティを使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ccff8-115">The following are examples of how to use this utility.</span></span>  
  
 <span data-ttu-id="ccff8-116">行程データベースに発行します。</span><span class="sxs-lookup"><span data-stu-id="ccff8-116">To publish to the Itinerary database:</span></span>  
  
```  
>EsbImportUtil /f:myitinerary.xml /c:published  
```  
  
 <span data-ttu-id="ccff8-117">行程データベースを展開します。</span><span class="sxs-lookup"><span data-stu-id="ccff8-117">To deploy to the Itinerary database:</span></span>  
  
```  
>EsbImportUtil  /f:myitinerary.xml /c:deployed  
```  
  
 <span data-ttu-id="ccff8-118">**SSO の構成ユーティリティを永続化します。**</span><span class="sxs-lookup"><span data-stu-id="ccff8-118">**SSO Configuration Persist Utility**</span></span>  
  
 <span data-ttu-id="ccff8-119">このユーティリティは、\bin ディレクトリの下にある、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Microsoft.Practices.ESB.PersistConfigurationTool.exe という名前です。</span><span class="sxs-lookup"><span data-stu-id="ccff8-119">This utility is located under the \bin directory of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and is named Microsoft.Practices.ESB.PersistConfigurationTool.exe.</span></span> <span data-ttu-id="ccff8-120">このユーティリティを使用して、BizTalk SSO データベースに ESB の構成情報を保持することができます。</span><span class="sxs-lookup"><span data-stu-id="ccff8-120">This utility can be used to persist the ESB configuration information into the BizTalk SSO database.</span></span> <span data-ttu-id="ccff8-121">これは、構成情報を表示および SSO データベースから構成情報を削除するも使用できます。</span><span class="sxs-lookup"><span data-stu-id="ccff8-121">This can also be used to view configuration information and remove the configuration information from the SSO database.</span></span>  
  
 <span data-ttu-id="ccff8-122">ユーティリティの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ccff8-122">The syntax for the utility is as follows:</span></span>  
  
 <span data-ttu-id="ccff8-123">**構成セクションを追加します。**</span><span class="sxs-lookup"><span data-stu-id="ccff8-123">**To add a configuration section:**</span></span>  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /P /F:app.config /S:SectionName /A:ApplicationName  
```  
  
> [!NOTE]
>  <span data-ttu-id="ccff8-124">/S が指定されていない場合は、以下のセクションが追加されます: connectionStrings、esb、esb.resolver および cachingConfiguration です。</span><span class="sxs-lookup"><span data-stu-id="ccff8-124">If /S is not provided, the following sections will be added: connectionStrings, esb, esb.resolver and cachingConfiguration.</span></span>  
  
 <span data-ttu-id="ccff8-125">**セクションを削除します。**</span><span class="sxs-lookup"><span data-stu-id="ccff8-125">**To remove a section:**</span></span>  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /R /S:SectionName  
```  
  
 <span data-ttu-id="ccff8-126">既存のセクションを表示するには、/V スイッチを使用してアプリケーションとセクション スイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="ccff8-126">To view an existing section, use the application and section switches with the /V switch.</span></span>  
  
 <span data-ttu-id="ccff8-127">管理者グループ名を設定するには、AG:AdminGroupName スイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="ccff8-127">To set the administrator group name, use the AG:AdminGroupName switch.</span></span>  
  
 <span data-ttu-id="ccff8-128">ユーザー グループ名を設定するには、UG:UserGroupName スイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="ccff8-128">To set the user group name, use the UG:UserGroupName switch.</span></span>