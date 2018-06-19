---
title: BizTalk FileAct アダプター エンド ツー エンドのチュートリアルの対話と |Microsoft ドキュメント
ms.custom: ''
ms.date: 2015-12-10
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73fbfb10-73e8-4365-a943-bcb9055f4f74
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15f2908abdb039d531fc0829efa7e019a6d0ca03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222962"
---
# <a name="biztalk-fileact-and-interact-adapters-end-to-end-tutorial"></a><span data-ttu-id="820b1-102">BizTalk FileAct と対話するアダプターのエンド ツー エンドのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="820b1-102">BizTalk FileAct and InterAct Adapters End-to-End Tutorial</span></span>
<span data-ttu-id="820b1-103">The Microsoft®[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]エンド ツー エンドのチュートリアルを使用する方法に関する情報を提供する[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]をリアルタイムに設定し、格納、およびメッセージ交換のシナリオを転送します。</span><span class="sxs-lookup"><span data-stu-id="820b1-103">The Microsoft® [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] End-to-End Tutorial provides specific information about how you can use [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] and [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to set up real-time and store and forward message exchange scenarios.</span></span>  
  
 <span data-ttu-id="820b1-104">[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]エンド ツー エンドのチュートリアルは、ソリューションの種類ごとにチュートリアルの形式で詳細な手順を含む 4 つの独立したシナリオを提供します。</span><span class="sxs-lookup"><span data-stu-id="820b1-104">The [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] End-To-End Tutorial provides four separate scenarios that include detailed steps in the form of tutorials for each type of solution.</span></span> <span data-ttu-id="820b1-105">これらのチュートリアルを開始する前に、BizTalk Server の基本概念を理解して SWIFT Alliance ゲートウェイ (SAG) ドキュメントに理解してください。</span><span class="sxs-lookup"><span data-stu-id="820b1-105">Before you begin these tutorials, you should understand the fundamental concepts surrounding BizTalk Server, and be familiar with the SWIFT Alliance Gateway (SAG) documentation.</span></span>  
  
 <span data-ttu-id="820b1-106">A4SWIFT のエンド ツー エンド チュートリアルを使うと A4Swift のリアルタイムを構成する詳細な手順と、FileAct と InterAct アダプターを使用するストア アンド フォワード シナリオを使用できます。</span><span class="sxs-lookup"><span data-stu-id="820b1-106">The A4SWIFT end-to-end tutorial provides you with detailed steps to configure real-time and store-and-forward scenarios with both the FileAct and InterAct adapters for A4Swift.</span></span> <span data-ttu-id="820b1-107">シナリオごとに、次を行います。</span><span class="sxs-lookup"><span data-stu-id="820b1-107">For each of the scenarios, you will do the following:</span></span>  
  
-   <span data-ttu-id="820b1-108">SWIFT のアダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="820b1-108">Configure the SWIFT adapter</span></span>  
  
-   <span data-ttu-id="820b1-109">SWIFTNet paramfile を構成します。</span><span class="sxs-lookup"><span data-stu-id="820b1-109">Configure the SWIFTNet paramfile</span></span>  
  
-   <span data-ttu-id="820b1-110">送信ポートを作成し、受信ポート</span><span class="sxs-lookup"><span data-stu-id="820b1-110">Create send ports and receive ports</span></span>  
  
-   <span data-ttu-id="820b1-111">シナリオをテストします。</span><span class="sxs-lookup"><span data-stu-id="820b1-111">Test the scenario</span></span>  
  
 <span data-ttu-id="820b1-112">このチュートリアルでは、2 つのロールを再生する: 送信者と受信者です。</span><span class="sxs-lookup"><span data-stu-id="820b1-112">In this tutorial, you will play two roles: Sender and Receiver.</span></span> <span data-ttu-id="820b1-113">メッセージの送信し、受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="820b1-113">You will create ports that send messages and receive them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="820b1-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="820b1-114">In This Section</span></span>  
  
-   [<span data-ttu-id="820b1-115">このチュートリアルを使用する準備をしています</span><span class="sxs-lookup"><span data-stu-id="820b1-115">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)  
  
-   [<span data-ttu-id="820b1-116">リアルタイムのシナリオを対話します。</span><span class="sxs-lookup"><span data-stu-id="820b1-116">InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md)  
  
-   [<span data-ttu-id="820b1-117">ストアと順方向 (プッシュ) シナリオを対話します。</span><span class="sxs-lookup"><span data-stu-id="820b1-117">InterAct Store and Forward (Push) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md)  
  
-   [<span data-ttu-id="820b1-118">FileAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="820b1-118">FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="820b1-119">FileAct ストア アンド フォワードのシナリオ</span><span class="sxs-lookup"><span data-stu-id="820b1-119">FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)