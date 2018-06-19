---
title: オーケストレーションで永続化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, persistence
- persistence
- BizTalk Server Orchestration Engine
ms.assetid: 2f79d294-f7df-4d84-ba76-50618506b6c6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af73db551ced1206ac316f0ba15b8c90a7d5053f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264594"
---
# <a name="persistence-in-orchestrations"></a><span data-ttu-id="fe129-102">オーケストレーションの永続性</span><span class="sxs-lookup"><span data-stu-id="fe129-102">Persistence in Orchestrations</span></span>
<span data-ttu-id="fe129-103">オーケストレーション エンジンは、さまざまな永続化ポイントでのオーケストレーション インスタンスの全体の状態を保存して、オーケストレーション インスタンスを復元できるようにします。</span><span class="sxs-lookup"><span data-stu-id="fe129-103">The orchestration engine saves the entire state of an orchestration instance at various persistence points to allow rehydration of the orchestration instance.</span></span> <span data-ttu-id="fe129-104">この状態には、メッセージや変数だけでなく、オーケストレーションで使用できるすべての .NET ベースのコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe129-104">The state includes any .NET-based components that may be used in the orchestration, in addition to messages and variables.</span></span> <span data-ttu-id="fe129-105">エンジンは、次の永続化ポイントでの状態を保存します。</span><span class="sxs-lookup"><span data-stu-id="fe129-105">The engine stores state at the following persistence points:</span></span>  
  
-   <span data-ttu-id="fe129-106">トランザクション スコープの最後 (アトミックまたは長時間トランザクション)</span><span class="sxs-lookup"><span data-stu-id="fe129-106">End of a transactional scope (atomic or long running)</span></span>  
  
-   <span data-ttu-id="fe129-107">デバッグのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="fe129-107">At debugging breakpoints</span></span>  
  
-   <span data-ttu-id="fe129-108">オーケストレーションの開始図形を使用した他のオーケストレーションの実行時</span><span class="sxs-lookup"><span data-stu-id="fe129-108">At the execution of other orchestrations through the Start Orchestration shape</span></span>  
  
-   <span data-ttu-id="fe129-109">送信図形 (アトミック トランザクションの場合を除く)</span><span class="sxs-lookup"><span data-stu-id="fe129-109">At the Send shape (except in an atomic transaction)</span></span>  
  
-   <span data-ttu-id="fe129-110">オーケストレーション インスタンスが中断された場合</span><span class="sxs-lookup"><span data-stu-id="fe129-110">When an Orchestration Instance is suspended</span></span>  
  
-   <span data-ttu-id="fe129-111">システムが適切な方法でシャットダウンした場合</span><span class="sxs-lookup"><span data-stu-id="fe129-111">When the system shutdowns in a controlled manner</span></span>  
  
-   <span data-ttu-id="fe129-112">退避が必要であるとエンジンが判断した場合</span><span class="sxs-lookup"><span data-stu-id="fe129-112">When the engine determines it wants to dehydrate</span></span>  
  
-   <span data-ttu-id="fe129-113">オーケストレーション インスタンスが完了した場合</span><span class="sxs-lookup"><span data-stu-id="fe129-113">When an orchestration instance is finished</span></span>  
  
 <span data-ttu-id="fe129-114">エンジンは、特にサイズの大きいメッセージを処理するときなど、負荷がかかる場合に永続化ポイントの数を最適化します。</span><span class="sxs-lookup"><span data-stu-id="fe129-114">The engine optimizes the number of persistence points as they are expensive, especially when dealing with large message sizes.</span></span> <span data-ttu-id="fe129-115">以下に 2 つのオーケストレーション インスタンスを示します。アトミックのスコープ内に送信図形のあるオーケストレーションでは、エンジンは、トランザクション スコープの最後とオーケストレーションの最後の間で 1 つの永続化ポイントを決定します。</span><span class="sxs-lookup"><span data-stu-id="fe129-115">As shown in the two orchestration instances below, in the orchestration with the Send Shapes in an atomic scope, the engine determines a single persistence point between the end of the transaction scope and the end of the orchestration.</span></span> <span data-ttu-id="fe129-116">別のオーケストレーションでは、2 つの永続化ポイントがあります。1 つは最初の送信図形のためのもので、もう 1 つはオーケストレーションの最後がある送信図形のためのものです。</span><span class="sxs-lookup"><span data-stu-id="fe129-116">In the other orchestration, there will be two persistence points, one for the first Send shape and the second for the Send shape plus end of the orchestration.</span></span>  
  
 <span data-ttu-id="fe129-117">**オーケストレーションの永続化**</span><span class="sxs-lookup"><span data-stu-id="fe129-117">**Orchestration persistence**</span></span>  
  
 <span data-ttu-id="fe129-118">![オーケストレーションの永続化](../core/media/bts-trans-orch-fig2.gif "BTS_Trans_Orch_Fig2")</span><span class="sxs-lookup"><span data-stu-id="fe129-118">![Orchestration persistence](../core/media/bts-trans-orch-fig2.gif "BTS_Trans_Orch_Fig2")</span></span>  
  
 <span data-ttu-id="fe129-119">オーケストレーションで直接的または間接的に使用するすべての .NET ベースのオブジェクトは、アトミックのスコープで呼び出されない場合に、あるいはオブジェクトがステートレスであり、静的メソッドによってのみ呼び出される場合に、シリアル化可能としてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe129-119">Any .NET-based objects you use in orchestrations, either directly or indirectly, must be marked as serializable unless they are invoked in atomic scopes, or if the objects are stateless and are invoked only through static methods.</span></span> <span data-ttu-id="fe129-120">**System.Xml.XmlDocument**特殊なケースは、スコープのトランザクション プロパティに関係なくシリアル化可能としてマークする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fe129-120">**System.Xml.XmlDocument** is a special case and does not need to be marked as serializable regardless of the transaction property for a scope.</span></span>  
  
 <span data-ttu-id="fe129-121">特別な処理をどのように**System.Xml.XmlDocument**動作します。</span><span class="sxs-lookup"><span data-stu-id="fe129-121">How does the special handling for **System.Xml.XmlDocument** work:</span></span>  
  
 <span data-ttu-id="fe129-122">ユーザーが変数を定義するときに**X**型の**T**ここで、 **T**は**System.Xml.XmlDocument**から派生したクラスまたは**System.Xml.XmlDocument**はコンパイラに処理し、 **X**としてシリアル化可能なオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="fe129-122">When the user defines a variable **X** of type **T**, where **T** is **System.Xml.XmlDocument** or a class derived from **System.Xml.XmlDocument** then the compiler will treat **X** as a serializable object.</span></span>  
  
 <span data-ttu-id="fe129-123">シリアル化中に**X**、ランタイムは次の種類の情報を保持: (a)、実際の型**Tr**オブジェクトの**X**を参照しています (b) **OuterXml**ドキュメントの文字列。</span><span class="sxs-lookup"><span data-stu-id="fe129-123">When serializing **X**, the runtime will keep the following pieces of information: (a) the actual type **Tr** of the object **X** is referring to (b) the **OuterXml** string of the document.</span></span>  
  
 <span data-ttu-id="fe129-124">逆シリアル化中に**X**、ランタイムのインスタンスが作成されます**Tr** (を任意のパラメーターを受け取らないコンス トラクターを想定しています) と呼び出されます**LoadXml**を提供する、保存されているインスタンス**OuterXml です。X**の新しく作成されたインスタンスを指すように設定されます、 **Tr**です。</span><span class="sxs-lookup"><span data-stu-id="fe129-124">When de-serializing **X**, the runtime will create an instance of **Tr** (this assumes a constructor that does not take any parameters) and will call **LoadXml** providing the instance with the saved **OuterXml.  X** will then be set to point to the newly created instance of **Tr**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe129-125">参照</span><span class="sxs-lookup"><span data-stu-id="fe129-125">See Also</span></span>  
 [<span data-ttu-id="fe129-126">トランザクション</span><span class="sxs-lookup"><span data-stu-id="fe129-126">Transactions</span></span>](../core/transactions.md)