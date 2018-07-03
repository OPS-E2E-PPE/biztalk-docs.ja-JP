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
ms.openlocfilehash: 23d3128d8cb3298dbab7e2394d55f6c2d6ff6ac3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971739"
---
# <a name="orchestration-variable-types"></a><span data-ttu-id="60ffc-102">オーケストレーション変数の型</span><span class="sxs-lookup"><span data-stu-id="60ffc-102">Orchestration Variable Types</span></span>
<span data-ttu-id="60ffc-103">次の定義済み型の変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="60ffc-103">You can declare variables of the following predefined types:</span></span>  

|||||  
|-|-|-|-|  
|<span data-ttu-id="60ffc-104">boolean</span><span class="sxs-lookup"><span data-stu-id="60ffc-104">boolean</span></span>|<span data-ttu-id="60ffc-105">byte</span><span class="sxs-lookup"><span data-stu-id="60ffc-105">byte</span></span>|<span data-ttu-id="60ffc-106">char</span><span class="sxs-lookup"><span data-stu-id="60ffc-106">char</span></span>|<span data-ttu-id="60ffc-107">DATETIME</span><span class="sxs-lookup"><span data-stu-id="60ffc-107">datetime</span></span>|  
|<span data-ttu-id="60ffc-108">Decimal</span><span class="sxs-lookup"><span data-stu-id="60ffc-108">decimal</span></span>|<span data-ttu-id="60ffc-109">double</span><span class="sxs-lookup"><span data-stu-id="60ffc-109">double</span></span>|<span data-ttu-id="60ffc-110">int16</span><span class="sxs-lookup"><span data-stu-id="60ffc-110">int16</span></span>|<span data-ttu-id="60ffc-111">int32</span><span class="sxs-lookup"><span data-stu-id="60ffc-111">int32</span></span>|  
|<span data-ttu-id="60ffc-112">int64</span><span class="sxs-lookup"><span data-stu-id="60ffc-112">int64</span></span>|<span data-ttu-id="60ffc-113">long</span><span class="sxs-lookup"><span data-stu-id="60ffc-113">long</span></span>|<span data-ttu-id="60ffc-114">sbyte</span><span class="sxs-lookup"><span data-stu-id="60ffc-114">sbyte</span></span>|<span data-ttu-id="60ffc-115">single</span><span class="sxs-lookup"><span data-stu-id="60ffc-115">single</span></span>|  
|<span data-ttu-id="60ffc-116">string</span><span class="sxs-lookup"><span data-stu-id="60ffc-116">string</span></span>|<span data-ttu-id="60ffc-117">timespan</span><span class="sxs-lookup"><span data-stu-id="60ffc-117">timespan</span></span>|<span data-ttu-id="60ffc-118">uint16</span><span class="sxs-lookup"><span data-stu-id="60ffc-118">uint16</span></span>|<span data-ttu-id="60ffc-119">uint32</span><span class="sxs-lookup"><span data-stu-id="60ffc-119">uint32</span></span>|  
|<span data-ttu-id="60ffc-120">uint64</span><span class="sxs-lookup"><span data-stu-id="60ffc-120">uint64</span></span>||||  

 <span data-ttu-id="60ffc-121">プロジェクト内で参照されている任意の .NET ベースの型の変数を宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="60ffc-121">You can also declare variables of any .NET-based types that are referenced in your project.</span></span>  

## <a name="considerations-for-declare-orchestration-variables"></a><span data-ttu-id="60ffc-122">オーケストレーション変数を宣言する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="60ffc-122">Considerations for Declare Orchestration Variables</span></span>  
 <span data-ttu-id="60ffc-123">オーケストレーション変数を宣言するときは、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="60ffc-123">When declare orchestration variables, consider the following:</span></span>  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="60ffc-124"> は、特定のコンテキストベースのルーティング シナリオに対して複数値のコンテキスト プロパティをサポートしていますが、このようなプロパティをオーケストレーションで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="60ffc-124"> supports multivalued context properties for certain content-based routing scenarios, but you cannot use such properties in orchestrations.</span></span>  

- <span data-ttu-id="60ffc-125">オーケストレーションの中断と退避をサポートするには、すべてのオーケストレーション変数がその状態を永続化できるようになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="60ffc-125">In order to support suspension and re-hydration of orchestrations, all orchestration variables must be capable of having their state persisted.</span></span>  <span data-ttu-id="60ffc-126">通常、これは変数の型またはクラスをシリアル化またはストリーミング化可能にすることで実現します。</span><span class="sxs-lookup"><span data-stu-id="60ffc-126">Typically, this is accomplished by the variable's type or class being serializable or streamable.</span></span>  

- <span data-ttu-id="60ffc-127">これらの .NET ベースの型 (クラス) はシリアル化可能なクラスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="60ffc-127">These .NET-based types (classes) must be serializable classes.</span></span>  <span data-ttu-id="60ffc-128">これは、"[Serializable]" 属性を使用して宣言するか、ISerializable .NET インターフェイス (System.Runtime.Serialization 名前空間内) を明示的に実装することによって実装できます。</span><span class="sxs-lookup"><span data-stu-id="60ffc-128">They may either implement this by being declared with the "[Serializable]” attribute or by explicitly implementing the ISerializable .NET interface (in the System.Runtime.Serialization namespace).</span></span>  

- <span data-ttu-id="60ffc-129">.NET ベースの型が、実際には基になる COM コンポーネントのランタイム呼び出し可能ラッパー (RCW) である場合、その COM コンポーネントでは RCW がシリアル化可能な .NET クラス (IPersistStream、IPersistStreamInit など) となるために必要なインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60ffc-129">If the .NET-based type is actually a runtime callable wrapper (RCW) of an underlying COM component, then that COM component must implement the interface(s) required for the RCW to be a serializable .NET class (e.g. IPersistStream, IPersistStreamInit).</span></span>  

- <span data-ttu-id="60ffc-130">.NET ベース (または基になる COM) の型はオーケストレーションのフロー内で実行されるので、これらの型のメソッドはオーケストレーションの実行を (リソースの競合などにより) 遅延しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="60ffc-130">Because any .NET-based (or underlying COM) types are executing within the flow of an orchestration, methods in these types must not delay execution of the orchestration (e.g. through contention for resources, etc.).</span></span>  <span data-ttu-id="60ffc-131">また、これらの型の実装によるリソースの競合は、呼び出し元のオーケストレーションを実行するホスト インスタンスに影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="60ffc-131">And any consumption of resources by these type implementations will affect the host instance in which the calling orchestration runs.</span></span>
