---
title: オーケストレーションでの永続化 |Microsoft Docs
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
ms.openlocfilehash: 184b4a7dde452902f404a5d6ed5dca5ee611e1e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008915"
---
# <a name="persistence-in-orchestrations"></a><span data-ttu-id="f03b0-102">オーケストレーションでの永続化</span><span class="sxs-lookup"><span data-stu-id="f03b0-102">Persistence in Orchestrations</span></span>
<span data-ttu-id="f03b0-103">オーケストレーション エンジンは、さまざまな永続化ポイントでのオーケストレーション インスタンスの全体の状態を保存して、オーケストレーション インスタンスを復元できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f03b0-103">The orchestration engine saves the entire state of an orchestration instance at various persistence points to allow rehydration of the orchestration instance.</span></span> <span data-ttu-id="f03b0-104">この状態には、メッセージや変数だけでなく、オーケストレーションで使用できるすべての .NET ベースのコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f03b0-104">The state includes any .NET-based components that may be used in the orchestration, in addition to messages and variables.</span></span> <span data-ttu-id="f03b0-105">エンジンは、次の永続化ポイントでの状態を保存します。</span><span class="sxs-lookup"><span data-stu-id="f03b0-105">The engine stores state at the following persistence points:</span></span>  
  
- <span data-ttu-id="f03b0-106">トランザクション スコープの最後 (アトミックまたは長時間トランザクション)</span><span class="sxs-lookup"><span data-stu-id="f03b0-106">End of a transactional scope (atomic or long running)</span></span>  
  
- <span data-ttu-id="f03b0-107">デバッグのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="f03b0-107">At debugging breakpoints</span></span>  
  
- <span data-ttu-id="f03b0-108">オーケストレーションの開始図形を使用した他のオーケストレーションの実行時</span><span class="sxs-lookup"><span data-stu-id="f03b0-108">At the execution of other orchestrations through the Start Orchestration shape</span></span>  
  
- <span data-ttu-id="f03b0-109">送信図形 (アトミック トランザクションの場合を除く)</span><span class="sxs-lookup"><span data-stu-id="f03b0-109">At the Send shape (except in an atomic transaction)</span></span>  
  
- <span data-ttu-id="f03b0-110">オーケストレーション インスタンスが中断された場合</span><span class="sxs-lookup"><span data-stu-id="f03b0-110">When an Orchestration Instance is suspended</span></span>  
  
- <span data-ttu-id="f03b0-111">システムが適切な方法でシャットダウンした場合</span><span class="sxs-lookup"><span data-stu-id="f03b0-111">When the system shutdowns in a controlled manner</span></span>  
  
- <span data-ttu-id="f03b0-112">退避が必要であるとエンジンが判断した場合</span><span class="sxs-lookup"><span data-stu-id="f03b0-112">When the engine determines it wants to dehydrate</span></span>  
  
- <span data-ttu-id="f03b0-113">オーケストレーション インスタンスが完了した場合</span><span class="sxs-lookup"><span data-stu-id="f03b0-113">When an orchestration instance is finished</span></span>  
  
  <span data-ttu-id="f03b0-114">エンジンは、特にサイズの大きいメッセージを処理するときなど、負荷がかかる場合に永続化ポイントの数を最適化します。</span><span class="sxs-lookup"><span data-stu-id="f03b0-114">The engine optimizes the number of persistence points as they are expensive, especially when dealing with large message sizes.</span></span> <span data-ttu-id="f03b0-115">以下に 2 つのオーケストレーション インスタンスを示します。アトミックのスコープ内に送信図形のあるオーケストレーションでは、エンジンは、トランザクション スコープの最後とオーケストレーションの最後の間で 1 つの永続化ポイントを決定します。</span><span class="sxs-lookup"><span data-stu-id="f03b0-115">As shown in the two orchestration instances below, in the orchestration with the Send Shapes in an atomic scope, the engine determines a single persistence point between the end of the transaction scope and the end of the orchestration.</span></span> <span data-ttu-id="f03b0-116">別のオーケストレーションでは、2 つの永続化ポイントがあります。1 つは最初の送信図形のためのもので、もう 1 つはオーケストレーションの最後がある送信図形のためのものです。</span><span class="sxs-lookup"><span data-stu-id="f03b0-116">In the other orchestration, there will be two persistence points, one for the first Send shape and the second for the Send shape plus end of the orchestration.</span></span>  
  
  <span data-ttu-id="f03b0-117">**オーケストレーションの永続化**</span><span class="sxs-lookup"><span data-stu-id="f03b0-117">**Orchestration persistence**</span></span>  
  
  <span data-ttu-id="f03b0-118">![オーケストレーションの永続化](../core/media/bts-trans-orch-fig2.gif "BTS_Trans_Orch_Fig2")</span><span class="sxs-lookup"><span data-stu-id="f03b0-118">![Orchestration persistence](../core/media/bts-trans-orch-fig2.gif "BTS_Trans_Orch_Fig2")</span></span>  
  
  <span data-ttu-id="f03b0-119">オーケストレーションで直接的または間接的に使用するすべての .NET ベースのオブジェクトは、アトミックのスコープで呼び出されない場合に、あるいはオブジェクトがステートレスであり、静的メソッドによってのみ呼び出される場合に、シリアル化可能としてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f03b0-119">Any .NET-based objects you use in orchestrations, either directly or indirectly, must be marked as serializable unless they are invoked in atomic scopes, or if the objects are stateless and are invoked only through static methods.</span></span> <span data-ttu-id="f03b0-120">**System.Xml.XmlDocument**特殊なケースでは、スコープのトランザクション プロパティに関係なくシリアル化可能としてマーク済みである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f03b0-120">**System.Xml.XmlDocument** is a special case and does not need to be marked as serializable regardless of the transaction property for a scope.</span></span>  
  
  <span data-ttu-id="f03b0-121">特別な処理をどのように行わ**System.Xml.XmlDocument**機能します。</span><span class="sxs-lookup"><span data-stu-id="f03b0-121">How does the special handling for **System.Xml.XmlDocument** work:</span></span>  
  
  <span data-ttu-id="f03b0-122">ユーザーが変数を定義する場合**X**型の**T**ここで、 **T**は**System.Xml.XmlDocument**から派生したクラスまたは**System.Xml.XmlDocument** 、コンパイラは処理し、 **X**としてシリアル化可能なオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f03b0-122">When the user defines a variable **X** of type **T**, where **T** is **System.Xml.XmlDocument** or a class derived from **System.Xml.XmlDocument** then the compiler will treat **X** as a serializable object.</span></span>  
  
  <span data-ttu-id="f03b0-123">シリアル化中に**X**、ランタイムは、次の情報を保持: (a)、実際の型**Tr**オブジェクトの**X**を参照している (b) **OuterXml**ドキュメントの文字列。</span><span class="sxs-lookup"><span data-stu-id="f03b0-123">When serializing **X**, the runtime will keep the following pieces of information: (a) the actual type **Tr** of the object **X** is referring to (b) the **OuterXml** string of the document.</span></span>  
  
  <span data-ttu-id="f03b0-124">逆シリアル化時に**X**、ランタイムのインスタンスが作成されます**Tr** (すべてのパラメーターを受け取らないコンストラクターを想定しています) とが呼び出されます**LoadXml**を提供する、保存されているインスタンス**OuterXml します。X**の新しく作成されたインスタンスを指すように設定し、されます**Tr**します。</span><span class="sxs-lookup"><span data-stu-id="f03b0-124">When de-serializing **X**, the runtime will create an instance of **Tr** (this assumes a constructor that does not take any parameters) and will call **LoadXml** providing the instance with the saved **OuterXml.  X** will then be set to point to the newly created instance of **Tr**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f03b0-125">参照</span><span class="sxs-lookup"><span data-stu-id="f03b0-125">See Also</span></span>  
 [<span data-ttu-id="f03b0-126">トランザクション</span><span class="sxs-lookup"><span data-stu-id="f03b0-126">Transactions</span></span>](../core/transactions.md)