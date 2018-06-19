---
title: オーケストレーションに関する |Microsoft ドキュメント
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
ms.openlocfilehash: 0bd3c1abeeb2c42c399a54aea4ba0128cc19bcd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225138"
---
# <a name="about-orchestrations"></a><span data-ttu-id="24747-102">オーケストレーションについて</span><span class="sxs-lookup"><span data-stu-id="24747-102">About Orchestrations</span></span>
<span data-ttu-id="24747-103">オーケストレーションは、XLANG/s 言語に基づいて実行可能なビジネス プロセスを示すための、柔軟で強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="24747-103">An orchestration is a flexible, powerful tool for representing an executable business process based on XLANG/s language.</span></span> <span data-ttu-id="24747-104">XLANG/s は、C# の表現機能を備えたメッセージング言語と見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="24747-104">XLANG/s can be viewed as a messaging language with some of the expression capabilities of C#.</span></span> <span data-ttu-id="24747-105">フローの設計、データの解釈および生成、カスタム コードの呼び出しが可能であり、直感的に見てわかる図で、プロセス全体を編成できます。また実行時には、BizTalk オーケストレーション エンジンが、BizTalk オーケストレーション デザイナーで生成された実行可能なビジネス プロセスである XLANG/s ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="24747-105">You can design flow, interpret and generate data, call custom code, and organize the entire process in an intuitive visual drawing, and at run time, the BizTalk Orchestration Engine executes XLANG/s files which are the executable business processes that are produced by BizTalk Orchestration Designer.</span></span>  
  
 <span data-ttu-id="24747-106">オーケストレーションで送受信されるメッセージと、送受信されるメッセージが通過するポートは、オーケストレーションの基本的な要素です。</span><span class="sxs-lookup"><span data-stu-id="24747-106">Messages, the send and receive actions that operate on them, and the ports through which they are transported are all fundamental elements of an orchestration.</span></span> <span data-ttu-id="24747-107">メッセージは、オーケストレーションが外部と通信するための手段です。このメッセージに基づいて、e ビジネスが実施されます。</span><span class="sxs-lookup"><span data-stu-id="24747-107">The message is the medium by which orchestrations communicate with the outside world and by which e-business is conducted.</span></span>  
  
 <span data-ttu-id="24747-108">**受信**と**送信**図形をオーケストレーションにメッセージを受信し、そこからメッセージを送信する必要がある機能をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="24747-108">**Receive** and **Send** shapes encapsulate the functionality you need to receive messages into your orchestration and send messages from it.</span></span> <span data-ttu-id="24747-109">オーケストレーションの論理的なフローを作成するためには、オーケストレーション デザイナーに用意されているさまざまな図形について理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24747-109">You should become familiar with the various shapes that Orchestration Designer provides to represent the logical flow of your orchestration.</span></span>  
  
 <span data-ttu-id="24747-110">Web サービス、関連付け、長時間実行されるトランザクションなど、オーケストレーションの高度な概念を理解してください。</span><span class="sxs-lookup"><span data-stu-id="24747-110">You should understand advanced orchestration concepts such as Web services, correlation, and long-running transactions.</span></span> <span data-ttu-id="24747-111">これらの機能をすべて使用する必要はありませんが、どのような機能を持つか理解しておくと便利です。</span><span class="sxs-lookup"><span data-stu-id="24747-111">You might not need to use all of these facilities, but it is helpful to know what they can do for you.</span></span>  
  
 <span data-ttu-id="24747-112">Web サービスは、WSDL (Web Services Description Language) に規定されている標準準拠のインターフェイスを備えたプログラムです。</span><span class="sxs-lookup"><span data-stu-id="24747-112">Web services are programs with interfaces that adhere to the standards set forth in the Web Services Description Language (WSDL).</span></span> <span data-ttu-id="24747-113">メッセージの種類、ポート、ポートの種類、および標準的な操作方法を定義することで、異種システムの相互通信を効率的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="24747-113">By defining message types, ports, port types, and operations in a standard way, disparate systems can communicate effectively with each other.</span></span>  
  
 <span data-ttu-id="24747-114">関連付けは、実行中のオーケストレーションの特定インスタンスに、メッセージを関連付けるためのメカニズムです。関連付けを使用すると、多くのインスタンスが実行され多くのメッセージが送受信されている場合に、ビジネス プロセスで適切な情報を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="24747-114">Correlation is the mechanism by which messages are associated with particular running instances of an orchestration, so that your business process gets the appropriate information when many instances are running and many messages are being sent back and forth.</span></span>  
  
 <span data-ttu-id="24747-115">トランザクションを使用すると、予期しない問題が発生した場合にも、オーケストレーションの状態を適切に維持することができます。</span><span class="sxs-lookup"><span data-stu-id="24747-115">Transactions enable you to maintain the state of an orchestration appropriately if any unexpected issues arise.</span></span> <span data-ttu-id="24747-116">オーケストレーション デザイナーでは、さまざまな例外処理機能を利用できます。これにより、適切に設定された、わかりやすい方法でエラーを処理できます。</span><span class="sxs-lookup"><span data-stu-id="24747-116">Orchestration Designer provides various ways to handle exceptions, which enable you to deal with errors in a controlled and predictable manner.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="24747-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="24747-117">In This Section</span></span>  
  
-   [<span data-ttu-id="24747-118">オーケストレーション デザイン画面</span><span class="sxs-lookup"><span data-stu-id="24747-118">The Orchestration Design Surface</span></span>](../core/the-orchestration-design-surface.md)  
  
-   [<span data-ttu-id="24747-119">BizTalk オーケストレーション タブ、ツールボックス</span><span class="sxs-lookup"><span data-stu-id="24747-119">BizTalk Orchestrations Tab, Toolbox</span></span>](../core/biztalk-orchestrations-tab-toolbox.md)  
  
-   [<span data-ttu-id="24747-120">オーケストレーションの開発手順</span><span class="sxs-lookup"><span data-stu-id="24747-120">Steps in Orchestration Development</span></span>](../core/steps-in-orchestration-development.md)  
  
-   [<span data-ttu-id="24747-121">オーケストレーションを開発するためのセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="24747-121">Security Considerations for Developing Orchestrations</span></span>](../core/security-considerations-for-developing-orchestrations.md)  
  
-   [<span data-ttu-id="24747-122">XLANG の言語</span><span class="sxs-lookup"><span data-stu-id="24747-122">XLANG-s Language</span></span>](../core/xlang-s-language.md)  
  
-   [<span data-ttu-id="24747-123">BizTalk オーケストレーション エンジンについて</span><span class="sxs-lookup"><span data-stu-id="24747-123">About the BizTalk Orchestration Engine</span></span>](../core/about-the-biztalk-orchestration-engine.md)