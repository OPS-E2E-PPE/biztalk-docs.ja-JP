---
title: BizTalk ESB Toolkit ユーティリティを使用する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2dc05ac-831a-44e1-bd44-e41398552ab1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97fcea7d2d7818b59ffae75754d04f5102e5f91c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396423"
---
# <a name="using-the-biztalk-esb-toolkit-utilities"></a><span data-ttu-id="4b813-102">BizTalk ESB Toolkit ユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b813-102">Using the BizTalk ESB Toolkit Utilities</span></span>
<span data-ttu-id="4b813-103">このセクションの一部として含まれているさまざまなユーティリティの説明、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4b813-103">This section describes various utilities included as part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="4b813-104">**ESB スケジュール オンランプ Import ユーティリティ**</span><span class="sxs-lookup"><span data-stu-id="4b813-104">**ESB Itinerary Import Utility**</span></span>  
  
 <span data-ttu-id="4b813-105">このユーティリティが \bin ディレクトリの下にある、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] EsbImportUtil.exe という名前です。</span><span class="sxs-lookup"><span data-stu-id="4b813-105">This utility is located under the \bin directory of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and is named EsbImportUtil.exe.</span></span> <span data-ttu-id="4b813-106">このユーティリティは、発行またはデプロイ ESBItineraryDB データベースに旅行プラン XML を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b813-106">This utility can be used to publish or deploy the itinerary XML into the ESBItineraryDB database.</span></span>  
  
 <span data-ttu-id="4b813-107">ユーティリティの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4b813-107">The syntax for the utility is as follows:</span></span>  
  
```  
>EsbImportUtil <Parameter1> <Value> <parameter2> <Value>...  
```  
  
 <span data-ttu-id="4b813-108">次に示します、さまざまなパラメーターを受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="4b813-108">The various parameters it can accept are the following:</span></span>  
  
 <span data-ttu-id="4b813-109">/?:\<パラメーターのヘルプを表示します。\></span><span class="sxs-lookup"><span data-stu-id="4b813-109">/?: \<Show the parameters help\></span></span>  
  
 <span data-ttu-id="4b813-110">/f:\<スケジュール オンランプ xml ファイルのパス\></span><span class="sxs-lookup"><span data-stu-id="4b813-110">/f: \<Itinerary xml file path\></span></span>  
  
 <span data-ttu-id="4b813-111">c:\<発行&#124;展開\></span><span class="sxs-lookup"><span data-stu-id="4b813-111">/c: \<published &#124; deployed\></span></span>  
  
 <span data-ttu-id="4b813-112">/n:\<既定のスケジュール名\></span><span class="sxs-lookup"><span data-stu-id="4b813-112">/n: \<Default Itinerary name\></span></span>  
  
 <span data-ttu-id="4b813-113">/v:\<既定のスケジュールのバージョン ('major.minor' 形式)\></span><span class="sxs-lookup"><span data-stu-id="4b813-113">/v: \<Default Itinerary version (format 'major.minor')\></span></span>  
  
 <span data-ttu-id="4b813-114">/o:\<サイレントの上書き\></span><span class="sxs-lookup"><span data-stu-id="4b813-114">/o: \<Silent overwrite\></span></span>  
  
 <span data-ttu-id="4b813-115">このユーティリティを使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4b813-115">The following are examples of how to use this utility.</span></span>  
  
 <span data-ttu-id="4b813-116">行程データベースを発行します。</span><span class="sxs-lookup"><span data-stu-id="4b813-116">To publish to the Itinerary database:</span></span>  
  
```  
>EsbImportUtil /f:myitinerary.xml /c:published  
```  
  
 <span data-ttu-id="4b813-117">行程データベースを展開します。</span><span class="sxs-lookup"><span data-stu-id="4b813-117">To deploy to the Itinerary database:</span></span>  
  
```  
>EsbImportUtil  /f:myitinerary.xml /c:deployed  
```  
  
 <span data-ttu-id="4b813-118">**SSO 構成ユーティリティを永続化します。**</span><span class="sxs-lookup"><span data-stu-id="4b813-118">**SSO Configuration Persist Utility**</span></span>  
  
 <span data-ttu-id="4b813-119">このユーティリティが \bin ディレクトリの下にある、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Microsoft.Practices.ESB.PersistConfigurationTool.exe という名前です。</span><span class="sxs-lookup"><span data-stu-id="4b813-119">This utility is located under the \bin directory of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and is named Microsoft.Practices.ESB.PersistConfigurationTool.exe.</span></span> <span data-ttu-id="4b813-120">このユーティリティは、BizTalk SSO データベースに、ESB の構成情報を永続化に使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b813-120">This utility can be used to persist the ESB configuration information into the BizTalk SSO database.</span></span> <span data-ttu-id="4b813-121">これは、構成情報を表示および SSO データベースから構成情報を削除するも使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b813-121">This can also be used to view configuration information and remove the configuration information from the SSO database.</span></span>  
  
 <span data-ttu-id="4b813-122">ユーティリティの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4b813-122">The syntax for the utility is as follows:</span></span>  
  
 <span data-ttu-id="4b813-123">**構成セクションを追加するには。**</span><span class="sxs-lookup"><span data-stu-id="4b813-123">**To add a configuration section:**</span></span>  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /P /F:app.config /S:SectionName /A:ApplicationName  
```  
  
> [!NOTE]
>  <span data-ttu-id="4b813-124">/S が指定されていない場合、次のセクションが追加されます: connectionStrings、esb、esb.resolver および cachingConfiguration します。</span><span class="sxs-lookup"><span data-stu-id="4b813-124">If /S is not provided, the following sections will be added: connectionStrings, esb, esb.resolver and cachingConfiguration.</span></span>  
  
 <span data-ttu-id="4b813-125">**セクションを削除するには。**</span><span class="sxs-lookup"><span data-stu-id="4b813-125">**To remove a section:**</span></span>  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /R /S:SectionName  
```  
  
 <span data-ttu-id="4b813-126">既存のセクションを表示するには、/V スイッチを使用して、アプリケーションとセクション スイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b813-126">To view an existing section, use the application and section switches with the /V switch.</span></span>  
  
 <span data-ttu-id="4b813-127">管理者グループ名を設定するには、AG:AdminGroupName スイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b813-127">To set the administrator group name, use the AG:AdminGroupName switch.</span></span>  
  
 <span data-ttu-id="4b813-128">ユーザー グループの名前を設定するには、UG:UserGroupName スイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b813-128">To set the user group name, use the UG:UserGroupName switch.</span></span>