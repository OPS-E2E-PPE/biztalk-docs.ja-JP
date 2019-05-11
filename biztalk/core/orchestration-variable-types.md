---
title: オーケストレーション変数の型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: 34990be2-35b6-40ec-b107-42a1c7b45aca
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ff157896d15b99685379bef16c0b3fc87e2e76e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322502"
---
# <a name="orchestration-variable-types"></a><span data-ttu-id="59354-102">オーケストレーション変数の型</span><span class="sxs-lookup"><span data-stu-id="59354-102">Orchestration Variable Types</span></span>
<span data-ttu-id="59354-103">次の定義済みの型の変数を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="59354-103">You can declare variables of the following predefined types:</span></span>  

|||||  
|-|-|-|-|  
|<span data-ttu-id="59354-104">boolean</span><span class="sxs-lookup"><span data-stu-id="59354-104">boolean</span></span>|<span data-ttu-id="59354-105">byte</span><span class="sxs-lookup"><span data-stu-id="59354-105">byte</span></span>|<span data-ttu-id="59354-106">char</span><span class="sxs-lookup"><span data-stu-id="59354-106">char</span></span>|<span data-ttu-id="59354-107">DATETIME</span><span class="sxs-lookup"><span data-stu-id="59354-107">datetime</span></span>|  
|<span data-ttu-id="59354-108">Decimal</span><span class="sxs-lookup"><span data-stu-id="59354-108">decimal</span></span>|<span data-ttu-id="59354-109">double</span><span class="sxs-lookup"><span data-stu-id="59354-109">double</span></span>|<span data-ttu-id="59354-110">int16</span><span class="sxs-lookup"><span data-stu-id="59354-110">int16</span></span>|<span data-ttu-id="59354-111">Int32</span><span class="sxs-lookup"><span data-stu-id="59354-111">int32</span></span>|  
|<span data-ttu-id="59354-112">int64</span><span class="sxs-lookup"><span data-stu-id="59354-112">int64</span></span>|<span data-ttu-id="59354-113">long</span><span class="sxs-lookup"><span data-stu-id="59354-113">long</span></span>|<span data-ttu-id="59354-114">sbyte</span><span class="sxs-lookup"><span data-stu-id="59354-114">sbyte</span></span>|<span data-ttu-id="59354-115">1 つ</span><span class="sxs-lookup"><span data-stu-id="59354-115">single</span></span>|  
|<span data-ttu-id="59354-116">string</span><span class="sxs-lookup"><span data-stu-id="59354-116">string</span></span>|<span data-ttu-id="59354-117">timespan</span><span class="sxs-lookup"><span data-stu-id="59354-117">timespan</span></span>|<span data-ttu-id="59354-118">uint16</span><span class="sxs-lookup"><span data-stu-id="59354-118">uint16</span></span>|<span data-ttu-id="59354-119">uint32</span><span class="sxs-lookup"><span data-stu-id="59354-119">uint32</span></span>|  
|<span data-ttu-id="59354-120">uint64</span><span class="sxs-lookup"><span data-stu-id="59354-120">uint64</span></span>||||  

 <span data-ttu-id="59354-121">いずれかの変数を宣言することもできます。プロジェクトで参照されている NET ベースの型。</span><span class="sxs-lookup"><span data-stu-id="59354-121">You can also declare variables of any .NET-based types that are referenced in your project.</span></span>  

## <a name="considerations-for-declare-orchestration-variables"></a><span data-ttu-id="59354-122">オーケストレーション変数を宣言に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="59354-122">Considerations for Declare Orchestration Variables</span></span>  
 <span data-ttu-id="59354-123">オーケストレーションを宣言する場合、変数は、次を検討してください。</span><span class="sxs-lookup"><span data-stu-id="59354-123">When declare orchestration variables, consider the following:</span></span>  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="59354-124">特定のコンテンツ ベースのルーティングのシナリオがサポートする複数値のコンテキスト プロパティは、オーケストレーションでこのようなプロパティを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="59354-124">supports multivalued context properties for certain content-based routing scenarios, but you cannot use such properties in orchestrations.</span></span>  

- <span data-ttu-id="59354-125">中断とオーケストレーションの変数である必要がありますすべてのオーケストレーションの退避をサポートするために持つことができる状態の永続化されます。</span><span class="sxs-lookup"><span data-stu-id="59354-125">In order to support suspension and re-hydration of orchestrations, all orchestration variables must be capable of having their state persisted.</span></span>  <span data-ttu-id="59354-126">通常、これは、変数の型またはクラスがシリアル化またはストリーミングによって実現されます。</span><span class="sxs-lookup"><span data-stu-id="59354-126">Typically, this is accomplished by the variable's type or class being serializable or streamable.</span></span>  

- <span data-ttu-id="59354-127">これらは。NET ベースの型 (クラス) は、シリアル化可能なクラスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="59354-127">These .NET-based types (classes) must be serializable classes.</span></span>  <span data-ttu-id="59354-128">"[Serializable]"属性で宣言されているか、ISerializable .NET インターフェイス (System.Runtime.Serialization 名前空間の) 内に明示的に実装しているか、実装できます。</span><span class="sxs-lookup"><span data-stu-id="59354-128">They may either implement this by being declared with the "[Serializable]” attribute or by explicitly implementing the ISerializable .NET interface (in the System.Runtime.Serialization namespace).</span></span>  

- <span data-ttu-id="59354-129">場合、します。NET ベースの型は、基になる COM コンポーネントの実際には、ランタイム呼び出し可能ラッパー (RCW)、その COM コンポーネントでは RCW がシリアル化可能な .NET クラス (IPersistStream、ipersiststreaminit など) に必要なインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59354-129">If the .NET-based type is actually a runtime callable wrapper (RCW) of an underlying COM component, then that COM component must implement the interface(s) required for the RCW to be a serializable .NET class (e.g. IPersistStream, IPersistStreamInit).</span></span>  

- <span data-ttu-id="59354-130">任意です。NET ベース (または、基になる COM) 型は、オーケストレーションのフローで実行して、これらの型のメソッドは、(競合リソースなど) を使用するなどのオーケストレーションの実行を遅延しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="59354-130">Because any .NET-based (or underlying COM) types are executing within the flow of an orchestration, methods in these types must not delay execution of the orchestration (e.g. through contention for resources, etc.).</span></span>  <span data-ttu-id="59354-131">これらの型の実装によってリソースの競合が呼び出し元のオーケストレーションを実行するホスト インスタンスに反映されます。</span><span class="sxs-lookup"><span data-stu-id="59354-131">And any consumption of resources by these type implementations will affect the host instance in which the calling orchestration runs.</span></span>
