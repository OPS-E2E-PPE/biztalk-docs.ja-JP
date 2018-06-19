---
title: メッセージを動的に変換する式を使用する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48387d97-9312-4df5-b614-727ea9035bf8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b9d16c38fefb4e2732bd05f7c3489acaa8ca645
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256938"
---
# <a name="how-to-use-expressions-to-dynamic-transform-messages"></a><span data-ttu-id="d476e-102">メッセージを動的に変換する式の使用方法</span><span class="sxs-lookup"><span data-stu-id="d476e-102">How to Use Expressions to Dynamic Transform Messages</span></span>
<span data-ttu-id="d476e-103">式を使用して、オーケストレーション内のメッセージを動的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="d476e-103">You can use expressions to dynamic transform messages in your orchestration.</span></span> <span data-ttu-id="d476e-104">XLANG 内から呼び出すことができる変換メソッドを公開する、**メッセージの割り当て**図形の内側、**メッセージの構築**図形です。</span><span class="sxs-lookup"><span data-stu-id="d476e-104">XLANG exposes a transform method that can be called from within a **Message Assignment** shape inside of a **Construct Message** shape.</span></span> <span data-ttu-id="d476e-105">これは、同じときに呼び出される、**変換**図形は使用しますが、プログラムによって、オーケストレーション内で指定したマップを使用してメッセージを変換することができます。</span><span class="sxs-lookup"><span data-stu-id="d476e-105">This is the same method that is called when a **Transform** shape is used, but allows you to programmatically transform the messages using the map you designated within the orchestration.</span></span> <span data-ttu-id="d476e-106">これは、種類に関係なくメッセージ処理を行う場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="d476e-106">This is useful when you are doing type-agnostic message processing.</span></span> <span data-ttu-id="d476e-107">たとえば、あるビジネス プロセスで、受け取った受信メッセージで指定されているパラメーターに基づいて一連のマップの中から受信メッセージの変換用のマップを選択する必要がある場合、式図形内で変換メソッドを使用すると、ビジネス プロセス全体を維持したままこれを実現することができます。</span><span class="sxs-lookup"><span data-stu-id="d476e-107">For example, if you have a business process that needs to choose from a series of maps to transform inbound messages based on the parameters provided by the received inbound messages, you can achieve this by using the transform method in the Expression shape while maintaining your overall business process intact.</span></span>  
  
## <a name="transforming-messages"></a><span data-ttu-id="d476e-108">メッセージの変換</span><span class="sxs-lookup"><span data-stu-id="d476e-108">Transforming messages</span></span>  
 <span data-ttu-id="d476e-109">次のサンプル コードを使用してプログラムからのメッセージを変換することができます、**メッセージの割り当て**図形。</span><span class="sxs-lookup"><span data-stu-id="d476e-109">You can use the following sample code to programmatically transform the messages in the **Message Assignment** shape:</span></span>  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg);  
```  
  
 <span data-ttu-id="d476e-110">この例では、MyMapType は型の変数として宣言されて**System.Type**オーケストレーションでします。</span><span class="sxs-lookup"><span data-stu-id="d476e-110">In this example, MyMapType is declared as a variable of type **System.Type** in the orchestration.</span></span> <span data-ttu-id="d476e-111">MyMapName は、BizTalk プロジェクトで作成済みのマップの名前です。</span><span class="sxs-lookup"><span data-stu-id="d476e-111">MyMapName is the name of a map that was already created in your BizTalk project.</span></span> <span data-ttu-id="d476e-112">別の BizTalk アセンブリにあるマップを参照する場合は、そのアセンブリを BizTalk プロジェクト内で参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d476e-112">If you would like to reference a map that is in a separate BizTalk assembly, you will need to reference that assembly in your BizTalk project.</span></span> <span data-ttu-id="d476e-113">MyInputMsg は変換元のメッセージ、MyOutputMsg は変換先のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="d476e-113">MyInputMsg is the source message and MyOutputMsg is the destination message.</span></span> <span data-ttu-id="d476e-114">変換元メッセージの複数指定が可能なマップの場合は、次のサンプル コードを使用してメッセージを変換できます。</span><span class="sxs-lookup"><span data-stu-id="d476e-114">If your map takes multiple source messages, then you can use the following sample code to transform the messages:</span></span>  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg1, MyInputMsg2);  
```  
  
> [!NOTE]
>  <span data-ttu-id="d476e-115">変換元メッセージが複数ある場合、それらのメッセージは、マップで指定されている入力メッセージ部分の番号の順に式に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d476e-115">If you have multiple source messages, they must be placed in order in the expression with respect to the input message part number indicated in the map.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d476e-116">式図形内のメッセージを動的に変換する場合は、コンパイル済みのマップをキャッシュするためのキャッシュをユーザー コード内に記述し、そのキャッシュを式図形で使用してメッセージ変換の実行前にマップを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d476e-116">When dynamic transforming messages in the Expression shape, we recommend that you write a cache in user code for caching the compiled maps, and then use the cache in the Expression shape to retrieve the maps before performing the message transformation.</span></span> <span data-ttu-id="d476e-117">マップをキャッシュしないと、共通言語ランタイム (CLR) のメモリ使用量が大幅に増加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d476e-117">If you are not caching the maps, it is possible to see Common Language Runtime (CLR) memory grow significantly.</span></span> <span data-ttu-id="d476e-118">動的マッピングを行うには .NET ランタイムでコード アクセス チェックを実行する必要があるため、変換ごとに .NET Evidence objec (.NET の Evidence オブジェクト) が Large Object Heap (ラージ オブジェクト ヒープ) に配置されることになり、オーケストレーションが完了するまで破棄されません。</span><span class="sxs-lookup"><span data-stu-id="d476e-118">Dynamic mapping requires that the .NET Runtime perform code access check which results in a .NET Evidence object being placed in the Large Object Heap for each transformation and this object is not disposed of until the orchestration completes.</span></span> <span data-ttu-id="d476e-119">したがって、このような種類の変換が同時に多数発生すると、メモリ使用量が大幅に増加する可能性があり、ひいてはメモリ不足の例外が発生する可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="d476e-119">Therefore, when there are a lot of these types of transforms occurring simultaneously, you may see the memory usage increase substantially which can also lead to the out of memory exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d476e-120">参照</span><span class="sxs-lookup"><span data-stu-id="d476e-120">See Also</span></span>  
 <span data-ttu-id="d476e-121">[オーケストレーション図形](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="d476e-121">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 [<span data-ttu-id="d476e-122">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="d476e-122">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)