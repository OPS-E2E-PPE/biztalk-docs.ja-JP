---
title: チュートリアル:BizTalk Adapter for JD Edwards EnterpriseOne の使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cafbe72-2b90-4d8e-9a1d-5735cefeb3d4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d34080e00ef05113a7d67787bcde2896b6b6e2aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393854"
---
# <a name="tutorial-using-the-biztalk-adapter-for-jd-edwards-enterpriseone"></a><span data-ttu-id="436c9-102">チュートリアル:BizTalk Adapter for JD Edwards EnterpriseOne の使用</span><span class="sxs-lookup"><span data-stu-id="436c9-102">Tutorial: Using the BizTalk Adapter for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="436c9-103">BizTalk コンテキスト プロパティを使用して、j. d. の制御を次に示します</span><span class="sxs-lookup"><span data-stu-id="436c9-103">The following demonstrates using BizTalk Context Properties to control the J.D.</span></span>  <span data-ttu-id="436c9-104">オーケストレーションで Edwards OneWorld セッションです。</span><span class="sxs-lookup"><span data-stu-id="436c9-104">Edwards OneWorld session in your orchestration.</span></span> <span data-ttu-id="436c9-105">このチュートリアルでは、j. d. for Microsoft BizTalk アダプターにバインドされた送信ポートに BeginDoc、EditLine、および EndDoc 呼び出しを送信するオーケストレーションがある前提としています</span><span class="sxs-lookup"><span data-stu-id="436c9-105">The tutorial assumes you have an orchestration that sends BeginDoc, EditLine and EndDoc calls to a send port bound to the Microsoft BizTalk Adapter for J.D.</span></span> <span data-ttu-id="436c9-106">Edwards OneWorld します。</span><span class="sxs-lookup"><span data-stu-id="436c9-106">Edwards OneWorld.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="436c9-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="436c9-107">In This Section</span></span>  
  
-   [<span data-ttu-id="436c9-108">ステップ 1: スキーマ DLL を参照します。</span><span class="sxs-lookup"><span data-stu-id="436c9-108">Step 1: Reference the Schema DLL</span></span>](../core/step-1-reference-the-schema-dll1.md)  
  
-   [<span data-ttu-id="436c9-109">手順 2:オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="436c9-109">Step 2: Create the Orchestration</span></span>](../core/step-2-create-the-orchestration2.md)  
  
-   [<span data-ttu-id="436c9-110">ステップ 3:完了して、プロジェクトを実行</span><span class="sxs-lookup"><span data-stu-id="436c9-110">Step 3: Complete and Run the Project</span></span>](../core/step-3-complete-and-run-the-project1.md)  
  
-   [<span data-ttu-id="436c9-111">手順 4:サンプル XML BeginDoc を作成します。</span><span class="sxs-lookup"><span data-stu-id="436c9-111">Step 4: Create a Sample XML BeginDoc</span></span>](../core/step-4-create-a-sample-xml-begindoc2.md)