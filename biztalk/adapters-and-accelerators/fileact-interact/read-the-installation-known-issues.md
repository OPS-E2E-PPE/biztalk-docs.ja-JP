---
title: インストールに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 245379f2-4048-4803-83ea-38dc23eb1a81
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26aaca5ce206e8ef320b61959f04f5e0fd5657a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366530"
---
# <a name="read-the-installation-known-issues"></a><span data-ttu-id="b4a53-102">インストールをに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="b4a53-102">Read the installation known issues</span></span>
[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] <span data-ttu-id="b4a53-103">既知の問題は、次のセクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4a53-103">have known issues listed in the following sections.</span></span>  
  
## <a name="swift-does-not-support-stress-testing-on-integration-test-bed-itb-and-swiftnet-stub-environment"></a><span data-ttu-id="b4a53-104">SWIFT はストレス テスト ベッドの統合 (ITB) と SWIFTNet スタブ環境でテストをサポートしていません</span><span class="sxs-lookup"><span data-stu-id="b4a53-104">SWIFT Does Not Support Stress Testing on Integration Test Bed (ITB) and SWIFTNet Stub Environment</span></span>  
 <span data-ttu-id="b4a53-105">ITB は、スループットの観点からサービス レベル アグリーメント (SLA) を指定しないと、データが完全に転送されるか、一貫性のあるであることを保証できません。</span><span class="sxs-lookup"><span data-stu-id="b4a53-105">The ITB does not provide Service Level Agreement (SLA) in terms of throughput, and cannot guarantee that data is completely transmitted or consistent.</span></span> <span data-ttu-id="b4a53-106">ストレスのテスト、パイロット環境でネットワークの運用環境に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4a53-106">You should stress test your implementation on the production network in the Pilot environment.</span></span>  
  
 <span data-ttu-id="b4a53-107">さらに、すべてのノード (サーバー、線、および帯域幅) が、データの損失を回避するために正しく構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4a53-107">Additionally, you must ensure that all of the nodes (server, lines, and bandwidth) are properly configured to avoid any data loss.</span></span> <span data-ttu-id="b4a53-108">スループットの一般的なサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b4a53-108">Following are typical sample throughputs:</span></span>  
  
- <span data-ttu-id="b4a53-109">操作/Fileact のストレスがコンピューターに属する送信:20 メッセージ/分</span><span class="sxs-lookup"><span data-stu-id="b4a53-109">Interact/Fileact Send under stressed computer: 20 messages/minute</span></span>  
  
- <span data-ttu-id="b4a53-110">操作/Fileact のストレスがコンピューターに属する受信:300 ~ 400 メッセージ/分</span><span class="sxs-lookup"><span data-stu-id="b4a53-110">Interact/Fileact Receive under stressed computer: 300-400 messages/minute</span></span>  
  
  <span data-ttu-id="b4a53-111">詳細については、SWIFT、マニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4a53-111">For more information, see your SWIFT documentation.</span></span>  
  
## <a name="messages-not-pushed-when-queue-is-open"></a><span data-ttu-id="b4a53-112">メッセージ キューが開いているときにプッシュされません。</span><span class="sxs-lookup"><span data-stu-id="b4a53-112">Messages Not Pushed When Queue Is Open</span></span>  
 <span data-ttu-id="b4a53-113">キューとのセッションが開いており、メッセージがプッシュされていない場合は、対話または FileAct ストア アンド フォワード (SnF) モードを使用している、SNLreceiver.exe を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4a53-113">When you are using InterAct or FileAct Store and Forward (SnF) mode, if the session with the queue is open and messages are not being pushed, then you must restart SNLreceiver.exe.</span></span> <span data-ttu-id="b4a53-114">SWIFT ときどき発生する問題を回避できます。</span><span class="sxs-lookup"><span data-stu-id="b4a53-114">This avoids an issue with SWIFT that can occur occasionally.</span></span>  
  
## <a name="you-must-use-cdata-when-passing-characters-like--and--in-message"></a><span data-ttu-id="b4a53-115">などの文字を渡すときに使用して CDATA する必要があります"<"と"&"は、メッセージ</span><span class="sxs-lookup"><span data-stu-id="b4a53-115">You Must Use CDATA when Passing Characters like "<" and "&" in message</span></span>  
 <span data-ttu-id="b4a53-116">という用語は、CDATA のテキスト データ、XML パーサーで解析する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4a53-116">The term CDATA is used about text data that should not be parsed by the XML parser.</span></span>  <span data-ttu-id="b4a53-117">文字"<"と"&"は XML 要素で無効です。</span><span class="sxs-lookup"><span data-stu-id="b4a53-117">Characters like "<" and "&" are illegal in XML elements.</span></span> <span data-ttu-id="b4a53-118">"<"、パーサーは、新しい要素の先頭として解釈されるので、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b4a53-118">"<" will generate an error because the parser interprets it as the start of a new element.</span></span> <span data-ttu-id="b4a53-119">"&"、パーサーは文字のエンティティの先頭として解釈されるので、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b4a53-119">"&" will generate an error because the parser interprets it as the start of a character entity.</span></span> <span data-ttu-id="b4a53-120">CDATA セクション内のすべてのものは、パーサーによって無視されます。</span><span class="sxs-lookup"><span data-stu-id="b4a53-120">Everything inside a CDATA section is ignored by the parser.</span></span> <span data-ttu-id="b4a53-121">CDATA セクションの開始"\<! [CDATA ["で終わる"]\>"</span><span class="sxs-lookup"><span data-stu-id="b4a53-121">A CDATA section starts with "\<![CDATA[" and ends with "]]\>"</span></span>  
  
## <a name="you-must-use-passthrough-pipelines-with-payload-only-mode"></a><span data-ttu-id="b4a53-122">ペイロードのみのモードでパススルー パイプラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4a53-122">You Must Use Passthrough Pipelines with Payload-Only Mode</span></span>  
 <span data-ttu-id="b4a53-123">InterAct アダプターのペイロードのみのモードを使用する場合は、パススルー パイプラインを使用して、両方の送信と受信ポートのカスタム パイプラインを使用していない場合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4a53-123">If you are using payload-only mode for the InterAct adapter, you must use pass-through pipelines on both the send and receive ports if you are not using custom pipelines.</span></span>  
  
## <a name="multiple-security-contexts-not-created-swiftnet-stub-computer"></a><span data-ttu-id="b4a53-124">複数のセキュリティ コンテキストを作成していない (SWIFTNet スタブ コンピューター)</span><span class="sxs-lookup"><span data-stu-id="b4a53-124">Multiple Security Contexts Not Created (SWIFTNet Stub Computer)</span></span>  
 <span data-ttu-id="b4a53-125">SWIFTNet スタブ コンピューターで、複数のセキュリティ コンテキストは、別の送信ポートは作成されません。</span><span class="sxs-lookup"><span data-stu-id="b4a53-125">On a SWIFTNet stub computer, multiple security contexts are not created for different send ports.</span></span> <span data-ttu-id="b4a53-126">ITB で複数のセキュリティ コンテキストが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b4a53-126">Multiple security contexts are created on ITB.</span></span>