---
title: "チュートリアル: BizTalk アダプターを使用して JD Edwards OneWorld の |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e13a648-7eaf-40c4-a71b-b66999087a69
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab54a0fe0f4a036e0045938951cf44337087853b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld"></a><span data-ttu-id="cc59d-102">チュートリアル: BizTalk アダプターを使用して JD Edwards OneWorld の</span><span class="sxs-lookup"><span data-stu-id="cc59d-102">Tutorial: Using the BizTalk Adapter for JD Edwards OneWorld</span></span>
<span data-ttu-id="cc59d-103">以下は、BizTalk コンテキスト プロパティを使用して、j. d. を制御するには</span><span class="sxs-lookup"><span data-stu-id="cc59d-103">The following demonstrates using BizTalk Context Properties to control the J.D.</span></span> <span data-ttu-id="cc59d-104">オーケストレーションで Edwards OneWorld セッションです。</span><span class="sxs-lookup"><span data-stu-id="cc59d-104">Edwards OneWorld session in your orchestration.</span></span> <span data-ttu-id="cc59d-105">このチュートリアルでは、j. d. for Microsoft BizTalk アダプターにバインドされた送信ポートに BeginDoc、EditLine、および EndDoc 呼び出しを送信するオーケストレーションがある前提としています</span><span class="sxs-lookup"><span data-stu-id="cc59d-105">The tutorial assumes you have an orchestration that sends BeginDoc, EditLine and EndDoc calls to a send port bound to the Microsoft BizTalk Adapter for J.D.</span></span> <span data-ttu-id="cc59d-106">Edwards OneWorld です。</span><span class="sxs-lookup"><span data-stu-id="cc59d-106">Edwards OneWorld.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc59d-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="cc59d-107">In This Section</span></span>  
  
-   [<span data-ttu-id="cc59d-108">手順 1: スキーマ DLL を参照します。</span><span class="sxs-lookup"><span data-stu-id="cc59d-108">Step 1: Reference the Schema DLL</span></span>](../core/step-1-reference-the-schema-dll2.md)  
  
-   [<span data-ttu-id="cc59d-109">手順 2: オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="cc59d-109">Step 2: Create the Orchestration</span></span>](../core/step-2-create-the-orchestration1.md)  
  
-   [<span data-ttu-id="cc59d-110">手順 3: が完了し、プロジェクトを実行</span><span class="sxs-lookup"><span data-stu-id="cc59d-110">Step 3: Complete and Run the Project</span></span>](../core/step-3-complete-and-run-the-project2.md)  
  
-   [<span data-ttu-id="cc59d-111">手順 4: サンプル XML BeginDoc を作成します。</span><span class="sxs-lookup"><span data-stu-id="cc59d-111">Step 4: Create a Sample XML BeginDoc</span></span>](../core/step-4-create-a-sample-xml-begindoc1.md)