---
title: Loopback チュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- loopbacks, tutorial
- loopback tutorial, about the loopback tutorial
- loopback tutorial
- tutorials, loopback tutorial
ms.assetid: 0f69c1f1-4039-4949-8eed-127ceabbc3cc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f96d81e59686759300e996e2f257da5afbc91ed0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283286"
---
# <a name="loopback-tutorial"></a><span data-ttu-id="01a57-102">Loopback チュートリアル</span><span class="sxs-lookup"><span data-stu-id="01a57-102">Loopback Tutorial</span></span>
<span data-ttu-id="01a57-103">このチュートリアルには、Microsoft® を使用する方法を説明する詳細な手順が含まれています。[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]を 1 台のコンピューターをホームとパートナーの組織間のプロセスの実装をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="01a57-103">This tutorial contains detailed steps that describe how you can use Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] to simulate a process implementation between the home and partner organization on a single computer.</span></span>  
  
 <span data-ttu-id="01a57-104">実際の運用環境で、パートナー組織の実装は、リモート コンピューターに存在します。</span><span class="sxs-lookup"><span data-stu-id="01a57-104">In a real production environment, your partner organization implementation resides on a remote computer.</span></span> <span data-ttu-id="01a57-105">このチュートリアルでは、同じコンピューター上で取引をシミュレートするためのアグリーメントを取引先ミラーを作成するのに、Loopback ユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="01a57-105">This tutorial uses the Loopback utility to create a mirror trading agreement to simulate the trading partner on the same computer.</span></span> <span data-ttu-id="01a57-106">1 台のコンピューターのループバック シナリオを使用して開発およびテスト目的に適しています。</span><span class="sxs-lookup"><span data-stu-id="01a57-106">Using a single computer loop-back scenario works for development and test purposes.</span></span> <span data-ttu-id="01a57-107">運用環境で、Loopback ユーティリティを使用しないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="01a57-107">It is recommended that you do not to use the Loopback utility in a production environment.</span></span>  
  
 <span data-ttu-id="01a57-108">このループバック シナリオは、メッセージの署名をサポートしていませんし、ため、否認不可はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="01a57-108">This loopback scenario does not support signing messages, and thus does not support non-repudiation.</span></span>  
  
 <span data-ttu-id="01a57-109">このシナリオは、テスト目的で使用できる暗号化用の秘密キーを使用して、構成されている証明機関がある場合、メッセージの暗号化をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="01a57-109">This scenario supports encryption of messages if you have a certification authority configured, and you have a private key for encryption available for test purposes.</span></span>  
  
 <span data-ttu-id="01a57-110">このチュートリアルでは、Loopback ユーティリティを使用してミラー アグリーメントを作成するや、ループバック シナリオを確認するサンプル プロセスを実行し、ホーム組織、取引先組織、取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="01a57-110">In this tutorial, you create a home organization, a partner organization, a trade agreement, use the Loopback utility to create a mirror agreement, and then run a sample process to verify the loop-back scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01a57-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="01a57-111">In This Section</span></span>  
  
-   [<span data-ttu-id="01a57-112">チュートリアルの準備</span><span class="sxs-lookup"><span data-stu-id="01a57-112">Preparing for the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-tutorial.md)  
  
-   [<span data-ttu-id="01a57-113">ステップ 1: ホーム組織の作成</span><span class="sxs-lookup"><span data-stu-id="01a57-113">Step 1: Create the Home Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-the-home-organization.md)  
  
-   [<span data-ttu-id="01a57-114">手順 2:取引先組織の作成</span><span class="sxs-lookup"><span data-stu-id="01a57-114">Step 2: Create the Partner Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-the-partner-organization.md)  
  
-   [<span data-ttu-id="01a57-115">ステップ 3:PIP (Partner Interface Process) の編集</span><span class="sxs-lookup"><span data-stu-id="01a57-115">Step 3: Edit the Partner Interface Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-edit-the-partner-interface-process.md)  
  
-   [<span data-ttu-id="01a57-116">手順 4:取引契約の作成</span><span class="sxs-lookup"><span data-stu-id="01a57-116">Step 4: Create a Trade Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)  
  
-   [<span data-ttu-id="01a57-117">手順 5:ミラー アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="01a57-117">Step 5: Create a Mirror Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)  
  
-   [<span data-ttu-id="01a57-118">手順 6:オーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="01a57-118">Step 6: Start Orchestrations</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)  
  
-   [<span data-ttu-id="01a57-119">手順 7:サンプル LOB メッセージの作成</span><span class="sxs-lookup"><span data-stu-id="01a57-119">Step 7: Create a Sample LOB Message</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)  
  
-   [<span data-ttu-id="01a57-120">手順 8:BTARN データベース内のメッセージの表示</span><span class="sxs-lookup"><span data-stu-id="01a57-120">Step 8: View Messages in the BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)