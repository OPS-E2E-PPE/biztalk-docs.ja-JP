---
title: "オーケストレーション (BizTalk Server Samples フォルダ) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- SDK examples
ms.assetid: f70f8d67-763f-4e3c-b233-c7156026b514
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2a018f52985e54f72749903aef58f40236d0618
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="orchestrations-biztalk-server-samples-folder"></a><span data-ttu-id="0d6a0-102">オーケストレーション (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="0d6a0-102">Orchestrations (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="0d6a0-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のソフトウェア開発キット (SDK) には、オーケストレーションのサンプルがいくつか付属しています。</span><span class="sxs-lookup"><span data-stu-id="0d6a0-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes several orchestration samples in its software development kit (SDK).</span></span> <span data-ttu-id="0d6a0-104">ここでは、付属のオーケストレーション サンプルで示される機能に関する詳細情報、サンプルのビルドや実行の手順、および予期される結果について説明します。</span><span class="sxs-lookup"><span data-stu-id="0d6a0-104">This section provides detailed information about the functionality demonstrated by these orchestration samples, instructions for building and running the samples, and the results you can expect.</span></span> <span data-ttu-id="0d6a0-105">次に、これらのサンプルを複雑な順に示します。HelloWorld は最も基本的なサンプルであり、</span><span class="sxs-lookup"><span data-stu-id="0d6a0-105">The samples listed below are sorted by complexity, that is, HelloWorld is the most basic sample in the list.</span></span> <span data-ttu-id="0d6a0-106">後に示すサンプルは、それより前のサンプルで紹介している機能を基にしている場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d6a0-106">Samples later in the list might be based upon functionalities shown in samples earlier in the list.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0d6a0-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0d6a0-107">In This Section</span></span>  
  
-   <span data-ttu-id="0d6a0-108">[HelloWorld (BizTalk Server サンプル)](../core/helloworld-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="0d6a0-108">[HelloWorld (BizTalk Server Sample)](../core/helloworld-biztalk-server-sample.md).</span></span> <span data-ttu-id="0d6a0-109">BizTalk オーケストレーションとマップを使用して、XML メッセージを関連する別の種類の XML メッセージに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0d6a0-109">Demonstrates how to process XML messages into related, but distinct, types of XML messages by using BizTalk orchestrations and maps.</span></span>  
  
-   <span data-ttu-id="0d6a0-110">[MethodCall (BizTalk Server サンプル)](../core/methodcall-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="0d6a0-110">[MethodCall (BizTalk Server Sample)](../core/methodcall-biztalk-server-sample.md).</span></span> <span data-ttu-id="0d6a0-111">BizTalk Server オーケストレーションから .NET ベースのメソッドを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0d6a0-111">Demonstrates how to call a .NET-based method from a BizTalk orchestration.</span></span>  
  
-   <span data-ttu-id="0d6a0-112">[CallOrchestration (BizTalk Server サンプル)](../core/callorchestration-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="0d6a0-112">[CallOrchestration (BizTalk Server Sample)](../core/callorchestration-biztalk-server-sample.md).</span></span> <span data-ttu-id="0d6a0-113">BizTalk オーケストレーションを別のオーケストレーションから呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0d6a0-113">Demonstrates how to call a BizTalk orchestration from another orchestration.</span></span>  
  
-   <span data-ttu-id="0d6a0-114">[補正 (BizTalk Server サンプル)](../core/compensation-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="0d6a0-114">[Compensation (BizTalk Server Sample)](../core/compensation-biztalk-server-sample.md).</span></span> <span data-ttu-id="0d6a0-115">使用する方法を示します、**補正**オーケストレーションの図形です。</span><span class="sxs-lookup"><span data-stu-id="0d6a0-115">Demonstrates how to use the **Compensate** shape in an orchestration.</span></span>  
  
-   <span data-ttu-id="0d6a0-116">[PartyResolution (BizTalk Server サンプル)](../core/partyresolution-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="0d6a0-116">[PartyResolution (BizTalk Server Sample)](../core/partyresolution-biztalk-server-sample.md).</span></span> <span data-ttu-id="0d6a0-117">パーティの解決で BizTalk オーケストレーションを使用してインスタンス メッセージをルーティングする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0d6a0-117">Demonstrates how to use BizTalk orchestrations with party resolution to route instance messages.</span></span>  
  
-   <span data-ttu-id="0d6a0-118">[BPEL インポート (BizTalk Server サンプル)](../core/bpel-import-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="0d6a0-118">[BPEL Import (BizTalk Server Sample)](../core/bpel-import-biztalk-server-sample.md).</span></span> <span data-ttu-id="0d6a0-119">BPEL (Business Process Execution Language) のプロセス説明と関連アイテムを基にオーケストレーションを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0d6a0-119">Demonstrates how to create an orchestration from a Business Process Execution Language (BPEL) description of a process and related artifacts.</span></span>