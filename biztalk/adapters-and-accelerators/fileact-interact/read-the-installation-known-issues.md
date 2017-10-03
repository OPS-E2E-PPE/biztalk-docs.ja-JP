---
title: "インストールの既知の問題を読み取る |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 245379f2-4048-4803-83ea-38dc23eb1a81
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f11e713d09ca8babcf7622710fd63bde9980373
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="read-the-installation-known-issues"></a><span data-ttu-id="92da3-102">既知の問題のインストールします。</span><span class="sxs-lookup"><span data-stu-id="92da3-102">Read the installation known issues</span></span>
[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]<span data-ttu-id="92da3-103">既知の問題は、次のセクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="92da3-103"> have known issues listed in the following sections.</span></span>  
  
## <a name="swift-does-not-support-stress-testing-on-integration-test-bed-itb-and-swiftnet-stub-environment"></a><span data-ttu-id="92da3-104">SWIFT は統合テスト ベッド (ITB) および SWIFTNet スタブ環境でのテストのストレスをサポートしていません</span><span class="sxs-lookup"><span data-stu-id="92da3-104">SWIFT Does Not Support Stress Testing on Integration Test Bed (ITB) and SWIFTNet Stub Environment</span></span>  
 <span data-ttu-id="92da3-105">ITB は、スループットの観点からサービス レベル アグリーメント (SLA) を提供せず、データが完全に転送されるか、一貫性のあることを保証できません。</span><span class="sxs-lookup"><span data-stu-id="92da3-105">The ITB does not provide Service Level Agreement (SLA) in terms of throughput, and cannot guarantee that data is completely transmitted or consistent.</span></span> <span data-ttu-id="92da3-106">ストレス テスト、パイロット運用環境でネットワークの運用環境に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92da3-106">You should stress test your implementation on the production network in the Pilot environment.</span></span>  
  
 <span data-ttu-id="92da3-107">さらに、すべてのノード (サーバー、線、および帯域幅) は、データの損失を避けるために正しく構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92da3-107">Additionally, you must ensure that all of the nodes (server, lines, and bandwidth) are properly configured to avoid any data loss.</span></span> <span data-ttu-id="92da3-108">スループットの典型的な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="92da3-108">Following are typical sample throughputs:</span></span>  
  
-   <span data-ttu-id="92da3-109">操作/Fileact のストレスがコンピューターに属する送信: 20 メッセージ/分</span><span class="sxs-lookup"><span data-stu-id="92da3-109">Interact/Fileact Send under stressed computer: 20 messages/minute</span></span>  
  
-   <span data-ttu-id="92da3-110">操作/Fileact が高負荷のコンピューターに属する受信: 300 ~ 400 メッセージ/分</span><span class="sxs-lookup"><span data-stu-id="92da3-110">Interact/Fileact Receive under stressed computer: 300-400 messages/minute</span></span>  
  
 <span data-ttu-id="92da3-111">詳細については、迅速な対応は、マニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="92da3-111">For more information, see your SWIFT documentation.</span></span>  
  
## <a name="messages-not-pushed-when-queue-is-open"></a><span data-ttu-id="92da3-112">メッセージ キューを開いている場合にプッシュされません。</span><span class="sxs-lookup"><span data-stu-id="92da3-112">Messages Not Pushed When Queue Is Open</span></span>  
 <span data-ttu-id="92da3-113">キューとのセッションが開いていて、メッセージがプッシュされるされなかった場合は、対話または FileAct ストア アンド フォワード (SnF) モードを使用している、SNLreceiver.exe を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92da3-113">When you are using InterAct or FileAct Store and Forward (SnF) mode, if the session with the queue is open and messages are not being pushed, then you must restart SNLreceiver.exe.</span></span> <span data-ttu-id="92da3-114">これは、ときどき発生する可能性が SWIFT の問題を回避できます。</span><span class="sxs-lookup"><span data-stu-id="92da3-114">This avoids an issue with SWIFT that can occur occasionally.</span></span>  
  
## <a name="you-must-use-cdata-when-passing-characters-like--and--in-message"></a><span data-ttu-id="92da3-115">などの文字を渡すときに使用する CDATA 必要があります"<"と"&"は、メッセージに</span><span class="sxs-lookup"><span data-stu-id="92da3-115">You Must Use CDATA when Passing Characters like "<" and "&" in message</span></span>  
 <span data-ttu-id="92da3-116">という用語は、CDATA、XML パーサーで解析してはなりませんテキスト データに関するします。</span><span class="sxs-lookup"><span data-stu-id="92da3-116">The term CDATA is used about text data that should not be parsed by the XML parser.</span></span>  <span data-ttu-id="92da3-117">などの文字"<"と"&"の XML 要素では無効です。</span><span class="sxs-lookup"><span data-stu-id="92da3-117">Characters like "<" and "&" are illegal in XML elements.</span></span> <span data-ttu-id="92da3-118">"<"、パーサーは、新しい要素の開始として解釈するために、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="92da3-118">"<" will generate an error because the parser interprets it as the start of a new element.</span></span> <span data-ttu-id="92da3-119">"&"、パーサーは文字エンティティの開始として解釈するために、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="92da3-119">"&" will generate an error because the parser interprets it as the start of a character entity.</span></span> <span data-ttu-id="92da3-120">CDATA セクション内のすべてのものは、パーサーによって無視されます。</span><span class="sxs-lookup"><span data-stu-id="92da3-120">Everything inside a CDATA section is ignored by the parser.</span></span> <span data-ttu-id="92da3-121">CDATA セクションの開始"\<! [CDATA ["で終わると"] >"</span><span class="sxs-lookup"><span data-stu-id="92da3-121">A CDATA section starts with "\<![CDATA[" and ends with "]]>"</span></span>  
  
## <a name="you-must-use-passthrough-pipelines-with-payload-only-mode"></a><span data-ttu-id="92da3-122">ペイロードのみのモードでパススルー パイプラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92da3-122">You Must Use Passthrough Pipelines with Payload-Only Mode</span></span>  
 <span data-ttu-id="92da3-123">InterAct アダプターのペイロードのみのモードを使用している場合、両方の送信パススルー パイプラインを使用して、カスタム パイプラインを使用していない場合、受信ポートください。</span><span class="sxs-lookup"><span data-stu-id="92da3-123">If you are using payload-only mode for the InterAct adapter, you must use pass-through pipelines on both the send and receive ports if you are not using custom pipelines.</span></span>  
  
## <a name="multiple-security-contexts-not-created-swiftnet-stub-computer"></a><span data-ttu-id="92da3-124">複数のセキュリティ コンテキスト (SWIFTNet スタブ コンピューター) は作成されません。</span><span class="sxs-lookup"><span data-stu-id="92da3-124">Multiple Security Contexts Not Created (SWIFTNet Stub Computer)</span></span>  
 <span data-ttu-id="92da3-125">SWIFTNet スタブ コンピューター上の異なる送信ポートの複数のセキュリティ コンテキストは作成されません。</span><span class="sxs-lookup"><span data-stu-id="92da3-125">On a SWIFTNet stub computer, multiple security contexts are not created for different send ports.</span></span> <span data-ttu-id="92da3-126">複数のセキュリティ コンテキストは、ITB に作成されます。</span><span class="sxs-lookup"><span data-stu-id="92da3-126">Multiple security contexts are created on ITB.</span></span>