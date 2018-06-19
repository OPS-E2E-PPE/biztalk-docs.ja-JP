---
title: 'レッスン 3: ソリューションの配置 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enterprise application integration tutorial, deploying solutions
ms.assetid: b2f50fe7-7636-45bf-a09b-776065dd8a33
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1f8c565a55bf59c49ccda9f1c521ebadc60aac5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261914"
---
# <a name="lesson-3-deploy-the-solution"></a><span data-ttu-id="b629e-102">レッスン 3: ソリューションの展開</span><span class="sxs-lookup"><span data-stu-id="b629e-102">Lesson 3: Deploy the Solution</span></span>
<span data-ttu-id="b629e-103">EAISolution を展開するには、まず BizTalk 管理データベースおよびグローバル アセンブリ キャッシュにアセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="b629e-103">The first step in deploying EAISolution is to add assemblies to the BizTalk Management database and the global assembly cache.</span></span>  
  
 <span data-ttu-id="b629e-104">次に、アプリケーションを構成して開始します。</span><span class="sxs-lookup"><span data-stu-id="b629e-104">The second step is to configure and start the application.</span></span>  
  
 <span data-ttu-id="b629e-105">[レッスン 2: ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)、EAIProcess オーケストレーションに論理ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="b629e-105">In [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md), you added logical ports to the EAIProcess orchestration.</span></span> <span data-ttu-id="b629e-106">このレッスンでは、物理ポートを定義し、論理ポートにバインドします。</span><span class="sxs-lookup"><span data-stu-id="b629e-106">In this lesson, you define the physical ports, and bind the physical ports to the logical ports.</span></span> <span data-ttu-id="b629e-107">また、オーケストレーション、受信ポート、および送信ポートをホストに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b629e-107">You must also assign orchestration, receive port and send ports to hosts.</span></span>  <span data-ttu-id="b629e-108">ホストは、BizTalk アイテムの仮想コンテナーです。</span><span class="sxs-lookup"><span data-stu-id="b629e-108">A host is a virtual container for BizTalk artifacts.</span></span>  <span data-ttu-id="b629e-109">各ホストには、アイテムを処理するための指定されたホスト インスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="b629e-109">Each host has designated host instances to process the artifacts.</span></span>  
  
 <span data-ttu-id="b629e-110">このレッスンでは、BizTalk Server 管理コンソールを使用して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のアイテムを管理する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="b629e-110">In this lesson, you learn about administering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] artifacts by using the BizTalk Server Administration Console.</span></span> <span data-ttu-id="b629e-111">BizTalk Server 管理コンソールの使用については、次を参照してください。 [、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="b629e-111">For information about using the BizTalk Server Administration Console, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b629e-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b629e-112">In This Section</span></span>  
  
-   [<span data-ttu-id="b629e-113">手順 1: 配置プロジェクト</span><span class="sxs-lookup"><span data-stu-id="b629e-113">Step 1: Deploy the Projects</span></span>](../core/step-1-deploy-the-projects.md)  
  
-   [<span data-ttu-id="b629e-114">手順 2: を構成し、アプリケーションを起動</span><span class="sxs-lookup"><span data-stu-id="b629e-114">Step 2: Configure and Start the Application</span></span>](../core/step-2-configure-and-start-the-application1.md)  
  
-   [<span data-ttu-id="b629e-115">手順 3: ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="b629e-115">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)  
  
## <a name="see-also"></a><span data-ttu-id="b629e-116">参照</span><span class="sxs-lookup"><span data-stu-id="b629e-116">See Also</span></span>  
 <span data-ttu-id="b629e-117">[このチュートリアルを開始する前に](../core/before-you-begin-the-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="b629e-117">[Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md) </span></span>  
 <span data-ttu-id="b629e-118">[レッスン 1: 定義のスキーマとマップ](../core/lesson-1-define-schemas-and-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="b629e-118">[Lesson 1: Define Schemas and a Map](../core/lesson-1-define-schemas-and-a-map.md) </span></span>  
 [<span data-ttu-id="b629e-119">レッスン 2: ビジネス プロセスを定義します。</span><span class="sxs-lookup"><span data-stu-id="b629e-119">Lesson 2: Define the Business Process</span></span>](../core/lesson-2-define-the-business-process.md)