---
title: オーケストレーションについて |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations
- Orchestration Designer
- orchestrations, about orchestrations
- Orchestration Designer, about Orchestration Designer
ms.assetid: c0d9a3fb-da87-42cc-9e9e-e2c37232e606
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8517433777e57b9811ec16ce08bb12ada139ee4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362321"
---
# <a name="about-orchestrations"></a><span data-ttu-id="a6d4f-102">オーケストレーションについて</span><span class="sxs-lookup"><span data-stu-id="a6d4f-102">About Orchestrations</span></span>
<span data-ttu-id="a6d4f-103">オーケストレーションは、xlang/s 言語に基づいて、実行可能なビジネス プロセスを表す、柔軟で強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="a6d4f-103">An orchestration is a flexible, powerful tool for representing an executable business process based on XLANG/s language.</span></span> <span data-ttu-id="a6d4f-104">一部の式の機能を備えたメッセージング言語として XLANG/秒を表示できますC#します。</span><span class="sxs-lookup"><span data-stu-id="a6d4f-104">XLANG/s can be viewed as a messaging language with some of the expression capabilities of C#.</span></span> <span data-ttu-id="a6d4f-105">フローの設計、解釈し、データを生成、カスタム コードの呼び出しの直感的なビジュアルの描画では、プロセス全体を整理したりできます、実行時に、BizTalk オーケストレーション エンジンはいる実行可能なビジネス プロセスである xlang/s ファイルを実行しますBizTalk オーケストレーション デザイナーによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="a6d4f-105">You can design flow, interpret and generate data, call custom code, and organize the entire process in an intuitive visual drawing, and at run time, the BizTalk Orchestration Engine executes XLANG/s files which are the executable business processes that are produced by BizTalk Orchestration Designer.</span></span>  
  
 <span data-ttu-id="a6d4f-106">メッセージ、送信と、それを操作するアクションを受け取るし、転送されるポートはオーケストレーションのすべての基本的な要素です。</span><span class="sxs-lookup"><span data-stu-id="a6d4f-106">Messages, the send and receive actions that operate on them, and the ports through which they are transported are all fundamental elements of an orchestration.</span></span> <span data-ttu-id="a6d4f-107">メッセージは、外部および e ビジネスが実施して、オーケストレーションが通信中です。</span><span class="sxs-lookup"><span data-stu-id="a6d4f-107">The message is the medium by which orchestrations communicate with the outside world and by which e-business is conducted.</span></span>  
  
 <span data-ttu-id="a6d4f-108">**受信**と**送信**図形をオーケストレーションにメッセージを受信し、そこからメッセージを送信する必要がある機能をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="a6d4f-108">**Receive** and **Send** shapes encapsulate the functionality you need to receive messages into your orchestration and send messages from it.</span></span> <span data-ttu-id="a6d4f-109">オーケストレーションの論理フローを表すオーケストレーション デザイナーを提供するさまざまな図形を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6d4f-109">You should become familiar with the various shapes that Orchestration Designer provides to represent the logical flow of your orchestration.</span></span>  
  
 <span data-ttu-id="a6d4f-110">Web サービス、相関、および実行時間の長いトランザクションなどの高度なオーケストレーションの概念を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6d4f-110">You should understand advanced orchestration concepts such as Web services, correlation, and long-running transactions.</span></span> <span data-ttu-id="a6d4f-111">すべてのこれらの機能を使用する必要はありませんを実行できるかを把握することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a6d4f-111">You might not need to use all of these facilities, but it is helpful to know what they can do for you.</span></span>  
  
 <span data-ttu-id="a6d4f-112">Web サービスは、Web サービス記述言語 (WSDL) で規定されている標準に準拠しているインターフェイスを持つプログラムです。</span><span class="sxs-lookup"><span data-stu-id="a6d4f-112">Web services are programs with interfaces that adhere to the standards set forth in the Web Services Description Language (WSDL).</span></span> <span data-ttu-id="a6d4f-113">標準的な方法でメッセージの種類、ポート、ポートの種類、および操作を定義すると、異種システムと通信できる効果的に相互します。</span><span class="sxs-lookup"><span data-stu-id="a6d4f-113">By defining message types, ports, port types, and operations in a standard way, disparate systems can communicate effectively with each other.</span></span>  
  
 <span data-ttu-id="a6d4f-114">相関関係は、多くのインスタンスが実行され、多くのメッセージが前後へ送信されるときに、ビジネス プロセスが適切な情報を取得できるようにするメッセージが、オーケストレーションの実行中の特定のインスタンスに関連付けられたメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="a6d4f-114">Correlation is the mechanism by which messages are associated with particular running instances of an orchestration, so that your business process gets the appropriate information when many instances are running and many messages are being sent back and forth.</span></span>  
  
 <span data-ttu-id="a6d4f-115">トランザクションでは、予期しない問題が発生した場合、オーケストレーションの状態を適切に維持することができます。</span><span class="sxs-lookup"><span data-stu-id="a6d4f-115">Transactions enable you to maintain the state of an orchestration appropriately if any unexpected issues arise.</span></span> <span data-ttu-id="a6d4f-116">オーケストレーション デザイナーには、制御され、予測可能な方法でエラーを処理するための例外を処理するさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a6d4f-116">Orchestration Designer provides various ways to handle exceptions, which enable you to deal with errors in a controlled and predictable manner.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a6d4f-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a6d4f-117">In This Section</span></span>  
  
-   [<span data-ttu-id="a6d4f-118">オーケストレーション デザイン サーフェイス</span><span class="sxs-lookup"><span data-stu-id="a6d4f-118">The Orchestration Design Surface</span></span>](../core/the-orchestration-design-surface.md)  
  
-   <span data-ttu-id="a6d4f-119">[[BizTalk オーケストレーション] タブ (ツールボックス)](../core/biztalk-orchestrations-tab-toolbox.md)</span><span class="sxs-lookup"><span data-stu-id="a6d4f-119">[BizTalk Orchestrations Tab, Toolbox](../core/biztalk-orchestrations-tab-toolbox.md)</span></span>  
  
-   [<span data-ttu-id="a6d4f-120">オーケストレーションの開発手順</span><span class="sxs-lookup"><span data-stu-id="a6d4f-120">Steps in Orchestration Development</span></span>](../core/steps-in-orchestration-development.md)  
  
-   [<span data-ttu-id="a6d4f-121">オーケストレーションを開発する際のセキュリティ上の注意</span><span class="sxs-lookup"><span data-stu-id="a6d4f-121">Security Considerations for Developing Orchestrations</span></span>](../core/security-considerations-for-developing-orchestrations.md)  
  
-   [<span data-ttu-id="a6d4f-122">XLANG-s 言語</span><span class="sxs-lookup"><span data-stu-id="a6d4f-122">XLANG-s Language</span></span>](../core/xlang-s-language.md)  
  
-   [<span data-ttu-id="a6d4f-123">BizTalk オーケストレーション エンジンについて</span><span class="sxs-lookup"><span data-stu-id="a6d4f-123">About the BizTalk Orchestration Engine</span></span>](../core/about-the-biztalk-orchestration-engine.md)