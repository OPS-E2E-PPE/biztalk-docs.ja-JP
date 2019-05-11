---
title: Orchestrations3 を実行している |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, running
- Receive shape [Orchestration Designer], starting orchestrations
- Start Orchestration shape [Orchestration Designer], starting orchestrations
- Call Orchestration shape [Orchestration Designer], starting orchestrations
- Receive shape [Orchestration Designer], activating orchestrations
ms.assetid: 5bfe61c9-80e0-4a0a-b6b1-ab48037e665e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc582889d30922b4446e9a941906064a8c08c418
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254540"
---
# <a name="running-orchestrations"></a><span data-ttu-id="d557f-102">オーケストレーションの実行</span><span class="sxs-lookup"><span data-stu-id="d557f-102">Running Orchestrations</span></span>
<span data-ttu-id="d557f-103">オーケストレーション インスタンスがデザインされていますか別のオーケストレーションからの明示的な呼び出しによってトリガーされる: を使用して、**オーケストレーションの呼び出し**図形または**オーケストレーションの開始**図形などの受信時に自動的、アクティベーション メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d557f-103">Orchestration instances are designed to be triggered either by an explicit call from another orchestration—using a **Call Orchestration** shape or **Start Orchestration** shape—or by receipt of an activation message.</span></span> <span data-ttu-id="d557f-104">アクティベーション メッセージ スキーマが指定された、**メッセージ**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d557f-104">The activation message schema is specified in the **Message** property.</span></span> <span data-ttu-id="d557f-105">したがって、オーケストレーションを設計する必要があり、いずれかを設定、**アクティブ化**プロパティを**受信**図形を [true]、または呼び出し元のオーケストレーションが存在しが実行を正しく構成されているかどうかを確認します新しいオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="d557f-105">You should design your orchestration accordingly, and either set the **Activate** property on a **Receive** shape to true, or make sure that a calling orchestration exists and is configured properly to run the new orchestration.</span></span>  
  
 <span data-ttu-id="d557f-106">インスタンスを実行すると、前にまずバインドし、BizTalk アセンブリを展開しし、参加して処理を開始するオーケストレーション エンジンを起動します。</span><span class="sxs-lookup"><span data-stu-id="d557f-106">Before any instances can run, you must first bind and deploy the BizTalk assembly, and then enlist and start the orchestration engine to begin processing.</span></span> <span data-ttu-id="d557f-107">詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)と[Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="d557f-107">For more information, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md) and [Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md).</span></span> <span data-ttu-id="d557f-108">オーケストレーションが別のオーケストレーションから呼び出され、アクティブ化の条件に一致するエンジンにメッセージが表示されます、受信、エンジンがオーケストレーションの新しいインスタンスを作成し、そのインスタンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="d557f-108">When an orchestration is invoked from another orchestration, or a message is presented to the engine that matches the criteria in an activation receive, the engine creates a new instance of the orchestration and runs that instance.</span></span> <span data-ttu-id="d557f-109">多数の異なるインスタンスで同時に実行できます。</span><span class="sxs-lookup"><span data-stu-id="d557f-109">It can run many different instances concurrently.</span></span>  
  
## <a name="calling-and-starting-orchestrations"></a><span data-ttu-id="d557f-110">呼び出しとオーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="d557f-110">Calling and starting orchestrations</span></span>  
 <span data-ttu-id="d557f-111">**オーケストレーションの呼び出し**図形と**オーケストレーションの開始**を別のオーケストレーションをアクティブ化図形を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d557f-111">The **Call Orchestration** shape and **Start Orchestration** shape can be used to activate another orchestration.</span></span> <span data-ttu-id="d557f-112">どちらの場合も、呼び出し元は、他のオーケストレーションと情報を交換するパラメーターに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d557f-112">In both cases, the caller can pass in parameters to exchange information with the other orchestration.</span></span> <span data-ttu-id="d557f-113">詳細については、次を参照してください。[オーケストレーションにパラメーターを追加する方法](../core/how-to-add-parameters-to-orchestrations.md)します。</span><span class="sxs-lookup"><span data-stu-id="d557f-113">For more information, see [How to Add Parameters to Orchestrations](../core/how-to-add-parameters-to-orchestrations.md).</span></span>  
  
## <a name="using-activation-receives-with-filter-expression"></a><span data-ttu-id="d557f-114">フィルター式を持つ受信ライセンス認証の使用</span><span class="sxs-lookup"><span data-stu-id="d557f-114">Using activation receives with filter expression</span></span>  
 <span data-ttu-id="d557f-115">**受信**図形がアクティブ化の条件をフィルター式を使用も可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d557f-115">The **Receive** shape might also use a filter expression to require further criteria for activation.</span></span> <span data-ttu-id="d557f-116">適切な種類のメッセージがあり、一部のプロパティまたはメッセージのプロパティのすべてのフィルター式で条件を満たす場合、**受信**図形がメッセージを受け入れるし、オーケストレーションがアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="d557f-116">If the message is of the correct type and some property or properties of the message meet all of the criteria in the filter expression, the **Receive** shape accepts the message and the orchestration is activated.</span></span> <span data-ttu-id="d557f-117">このような受信図形と呼びます、*アクティベーション受信*します。</span><span class="sxs-lookup"><span data-stu-id="d557f-117">Such a Receive shape is referred to as an *activation receive*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d557f-118">参照</span><span class="sxs-lookup"><span data-stu-id="d557f-118">See Also</span></span>  
 <span data-ttu-id="d557f-119">[オーケストレーションの呼び出し図形を構成する方法](../core/how-to-configure-the-call-orchestration-shape.md) </span><span class="sxs-lookup"><span data-stu-id="d557f-119">[How to Configure the Call Orchestration Shape](../core/how-to-configure-the-call-orchestration-shape.md) </span></span>  
 <span data-ttu-id="d557f-120">[オーケストレーションの開始図形を構成する方法](../core/how-to-configure-the-start-orchestration-shape.md) </span><span class="sxs-lookup"><span data-stu-id="d557f-120">[How to Configure the Start Orchestration Shape](../core/how-to-configure-the-start-orchestration-shape.md) </span></span>  
 <span data-ttu-id="d557f-121">[受信図形を構成する方法](../core/how-to-configure-the-receive-shape.md) </span><span class="sxs-lookup"><span data-stu-id="d557f-121">[How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md) </span></span>  
 [<span data-ttu-id="d557f-122">オーケストレーションのビルドおよび実行</span><span class="sxs-lookup"><span data-stu-id="d557f-122">Building and Running Orchestrations</span></span>](../core/building-and-running-orchestrations.md)