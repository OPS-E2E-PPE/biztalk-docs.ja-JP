---
title: "Orchestrations3 を実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, running
- Receive shape [Orchestration Designer], starting orchestrations
- Start Orchestration shape [Orchestration Designer], starting orchestrations
- Call Orchestration shape [Orchestration Designer], starting orchestrations
- Receive shape [Orchestration Designer], activating orchestrations
ms.assetid: 5bfe61c9-80e0-4a0a-b6b1-ab48037e665e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 550fc1e03f3583215a817028917000c9a9c3074a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-orchestrations"></a><span data-ttu-id="b57fd-102">オーケストレーションの実行</span><span class="sxs-lookup"><span data-stu-id="b57fd-102">Running Orchestrations</span></span>
<span data-ttu-id="b57fd-103">オーケストレーション インスタンスに構成されていますか別のオーケストレーションからの明示的な呼び出しによってトリガーされる: を使用して、**オーケストレーションの呼び出し**図形または**オーケストレーションの開始**図形 — の受信時、アクティブ化メッセージ。</span><span class="sxs-lookup"><span data-stu-id="b57fd-103">Orchestration instances are designed to be triggered either by an explicit call from another orchestration—using a **Call Orchestration** shape or **Start Orchestration** shape—or by receipt of an activation message.</span></span> <span data-ttu-id="b57fd-104">アクティベーション メッセージ スキーマが指定された、**メッセージ**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="b57fd-104">The activation message schema is specified in the **Message** property.</span></span> <span data-ttu-id="b57fd-105">同様に、オーケストレーションをデザインする必要があり、設定するか、 **Activate**プロパティを**受信**true、または呼び出し元のオーケストレーションが存在しを実行する正しく構成されているかどうかを確認する図形、新しいオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="b57fd-105">You should design your orchestration accordingly, and either set the **Activate** property on a **Receive** shape to true, or make sure that a calling orchestration exists and is configured properly to run the new orchestration.</span></span>  
  
 <span data-ttu-id="b57fd-106">インスタンスを実行するためには、まず BizTalk アセンブリをバインドおよび展開し、オーケストレーション エンジンを参加および開始させて処理を開始しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="b57fd-106">Before any instances can run, you must first bind and deploy the BizTalk assembly, and then enlist and start the orchestration engine to begin processing.</span></span> <span data-ttu-id="b57fd-107">詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)と[を管理する BizTalk アプリケーションの展開と](../core/deploying-and-managing-biztalk-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="b57fd-107">For more information, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md) and [Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md).</span></span> <span data-ttu-id="b57fd-108">オーケストレーションが他のオーケストレーションから呼び出されたとき、または、アクティベーション受信の条件と一致するメッセージがエンジンに送信されると、エンジンによって新しいオーケストレーション インスタンスが作成され、実行されます。</span><span class="sxs-lookup"><span data-stu-id="b57fd-108">When an orchestration is invoked from another orchestration, or a message is presented to the engine that matches the criteria in an activation receive, the engine creates a new instance of the orchestration and runs that instance.</span></span> <span data-ttu-id="b57fd-109">エンジンは、複数の異なるインスタンスを同時に実行することができます。</span><span class="sxs-lookup"><span data-stu-id="b57fd-109">It can run many different instances concurrently.</span></span>  
  
## <a name="calling-and-starting-orchestrations"></a><span data-ttu-id="b57fd-110">オーケストレーションの呼び出しと開始</span><span class="sxs-lookup"><span data-stu-id="b57fd-110">Calling and starting orchestrations</span></span>  
 <span data-ttu-id="b57fd-111">**オーケストレーションの呼び出し**図形と**オーケストレーションの開始**図形は、別のオーケストレーションをアクティブ化を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b57fd-111">The **Call Orchestration** shape and **Start Orchestration** shape can be used to activate another orchestration.</span></span> <span data-ttu-id="b57fd-112">いずれの場合も、呼び出し元は、パラメーターを渡すことによって他のオーケストレーションと情報を交換できます。</span><span class="sxs-lookup"><span data-stu-id="b57fd-112">In both cases, the caller can pass in parameters to exchange information with the other orchestration.</span></span> <span data-ttu-id="b57fd-113">詳細については、次を参照してください。[オーケストレーションにパラメーターを追加する方法](../core/how-to-add-parameters-to-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="b57fd-113">For more information, see [How to Add Parameters to Orchestrations](../core/how-to-add-parameters-to-orchestrations.md).</span></span>  
  
## <a name="using-activation-receives-with-filter-expression"></a><span data-ttu-id="b57fd-114">フィルター式を指定したアクティベーション受信の使用</span><span class="sxs-lookup"><span data-stu-id="b57fd-114">Using activation receives with filter expression</span></span>  
 <span data-ttu-id="b57fd-115">**受信**図形は、ライセンス認証のための条件を要求するフィルター式を使用も可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b57fd-115">The **Receive** shape might also use a filter expression to require further criteria for activation.</span></span> <span data-ttu-id="b57fd-116">適切な型のメッセージがあり、一部のプロパティまたはメッセージのプロパティのすべてのフィルター式で条件を満たす場合、**受信**図形がメッセージを受け入れるし、オーケストレーションがアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="b57fd-116">If the message is of the correct type and some property or properties of the message meet all of the criteria in the filter expression, the **Receive** shape accepts the message and the orchestration is activated.</span></span> <span data-ttu-id="b57fd-117">このような受信図形と呼びます、*アクティベーション受信*です。</span><span class="sxs-lookup"><span data-stu-id="b57fd-117">Such a Receive shape is referred to as an *activation receive*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b57fd-118">参照</span><span class="sxs-lookup"><span data-stu-id="b57fd-118">See Also</span></span>  
 <span data-ttu-id="b57fd-119">[オーケストレーションの呼び出し図形を構成する方法](../core/how-to-configure-the-call-orchestration-shape.md) </span><span class="sxs-lookup"><span data-stu-id="b57fd-119">[How to Configure the Call Orchestration Shape](../core/how-to-configure-the-call-orchestration-shape.md) </span></span>  
 <span data-ttu-id="b57fd-120">[オーケストレーションの開始図形を構成する方法](../core/how-to-configure-the-start-orchestration-shape.md) </span><span class="sxs-lookup"><span data-stu-id="b57fd-120">[How to Configure the Start Orchestration Shape](../core/how-to-configure-the-start-orchestration-shape.md) </span></span>  
 <span data-ttu-id="b57fd-121">[受信図形を構成する方法](../core/how-to-configure-the-receive-shape.md) </span><span class="sxs-lookup"><span data-stu-id="b57fd-121">[How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md) </span></span>  
 [<span data-ttu-id="b57fd-122">ビルドとオーケストレーションの実行</span><span class="sxs-lookup"><span data-stu-id="b57fd-122">Building and Running Orchestrations</span></span>](../core/building-and-running-orchestrations.md)