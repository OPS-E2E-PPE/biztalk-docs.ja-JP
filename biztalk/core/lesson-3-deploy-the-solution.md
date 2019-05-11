---
title: 'レッスン 3: ソリューションの配置 |Microsoft Docs'
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
ms.openlocfilehash: 92fa0155ed7b95bd433c99122362de8dca3cfc79
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380643"
---
# <a name="lesson-3-deploy-the-solution"></a><span data-ttu-id="6e958-102">レッスン 3: ソリューションをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="6e958-102">Lesson 3: Deploy the Solution</span></span>
<span data-ttu-id="6e958-103">EAISolution を展開する最初の手順では、BizTalk 管理データベースおよびグローバル アセンブリ キャッシュにアセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="6e958-103">The first step in deploying EAISolution is to add assemblies to the BizTalk Management database and the global assembly cache.</span></span>  
  
 <span data-ttu-id="6e958-104">2 番目の手順を構成して、アプリケーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="6e958-104">The second step is to configure and start the application.</span></span>  
  
 <span data-ttu-id="6e958-105">「[レッスン 2: ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)、EAIProcess オーケストレーションに論理ポートを追加しました。</span><span class="sxs-lookup"><span data-stu-id="6e958-105">In [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md), you added logical ports to the EAIProcess orchestration.</span></span> <span data-ttu-id="6e958-106">このレッスンでは、物理ポートを定義し、物理ポートを論理ポートにバインドします。</span><span class="sxs-lookup"><span data-stu-id="6e958-106">In this lesson, you define the physical ports, and bind the physical ports to the logical ports.</span></span> <span data-ttu-id="6e958-107">オーケストレーションを割り当て、受信ポート、および送信ポートをホストにもする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e958-107">You must also assign orchestration, receive port and send ports to hosts.</span></span>  <span data-ttu-id="6e958-108">ホストは、BizTalk アイテムの仮想コンテナーです。</span><span class="sxs-lookup"><span data-stu-id="6e958-108">A host is a virtual container for BizTalk artifacts.</span></span>  <span data-ttu-id="6e958-109">各ホストでは、アイテムを処理するためのホスト インスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e958-109">Each host has designated host instances to process the artifacts.</span></span>  
  
 <span data-ttu-id="6e958-110">このレッスンを管理する方法について説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk Server 管理コンソールを使用して成果物。</span><span class="sxs-lookup"><span data-stu-id="6e958-110">In this lesson, you learn about administering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] artifacts by using the BizTalk Server Administration Console.</span></span> <span data-ttu-id="6e958-111">BizTalk Server 管理コンソールの使用方法の詳細については、次を参照してください。 [、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="6e958-111">For information about using the BizTalk Server Administration Console, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6e958-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6e958-112">In This Section</span></span>  
  
-   [<span data-ttu-id="6e958-113">ステップ 1: プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="6e958-113">Step 1: Deploy the Projects</span></span>](../core/step-1-deploy-the-projects.md)  
  
-   [<span data-ttu-id="6e958-114">手順 2:アプリケーションの構成と開始</span><span class="sxs-lookup"><span data-stu-id="6e958-114">Step 2: Configure and Start the Application</span></span>](../core/step-2-configure-and-start-the-application1.md)  
  
-   [<span data-ttu-id="6e958-115">ステップ 3:ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="6e958-115">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)  
  
## <a name="see-also"></a><span data-ttu-id="6e958-116">参照</span><span class="sxs-lookup"><span data-stu-id="6e958-116">See Also</span></span>  
 <span data-ttu-id="6e958-117">[このチュートリアルを開始する前に](../core/before-you-begin-the-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="6e958-117">[Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md) </span></span>  
 <span data-ttu-id="6e958-118">[レッスン 1:スキーマおよびマップを定義します。](../core/lesson-1-define-schemas-and-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="6e958-118">[Lesson 1: Define Schemas and a Map](../core/lesson-1-define-schemas-and-a-map.md) </span></span>  
 [<span data-ttu-id="6e958-119">レッスン 2:ビジネス プロセスを定義します。</span><span class="sxs-lookup"><span data-stu-id="6e958-119">Lesson 2: Define the Business Process</span></span>](../core/lesson-2-define-the-business-process.md)