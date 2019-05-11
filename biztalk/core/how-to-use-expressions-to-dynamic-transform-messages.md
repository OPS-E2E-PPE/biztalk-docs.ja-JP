---
title: メッセージに動的に変換する式を使用する方法 |Microsoft Docs
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
ms.openlocfilehash: 084d8144aae37f3036d17f574a7fb663755e0b26
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333464"
---
# <a name="how-to-use-expressions-to-dynamic-transform-messages"></a><span data-ttu-id="09ddb-102">メッセージに動的に変換する式を使用する方法</span><span class="sxs-lookup"><span data-stu-id="09ddb-102">How to Use Expressions to Dynamic Transform Messages</span></span>
<span data-ttu-id="09ddb-103">オーケストレーションでメッセージを動的に変換する式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="09ddb-103">You can use expressions to dynamic transform messages in your orchestration.</span></span> <span data-ttu-id="09ddb-104">XLANG 内から呼び出せる変換メソッドを公開する、**メッセージの割り当て**図形の内部を**メッセージの構築**図形。</span><span class="sxs-lookup"><span data-stu-id="09ddb-104">XLANG exposes a transform method that can be called from within a **Message Assignment** shape inside of a **Construct Message** shape.</span></span> <span data-ttu-id="09ddb-105">これは、同じメソッド時に呼び出される、**変換**図形が使用されますが、プログラムによって、オーケストレーション内で指定したマップを使用してメッセージを変換することができます。</span><span class="sxs-lookup"><span data-stu-id="09ddb-105">This is the same method that is called when a **Transform** shape is used, but allows you to programmatically transform the messages using the map you designated within the orchestration.</span></span> <span data-ttu-id="09ddb-106">これは、機能は、型に依存しないメッセージの処理を実行すると便利です。</span><span class="sxs-lookup"><span data-stu-id="09ddb-106">This is useful when you are doing type-agnostic message processing.</span></span> <span data-ttu-id="09ddb-107">たとえば、受信した受信メッセージによって提供されるパラメーターに基づく受信メッセージを変換する一連のマップから選択する必要があるビジネス プロセスがあれば、これを行う中に、式図形で変換メソッドを使用して、ビジネス プロセス全体をそのまま維持します。</span><span class="sxs-lookup"><span data-stu-id="09ddb-107">For example, if you have a business process that needs to choose from a series of maps to transform inbound messages based on the parameters provided by the received inbound messages, you can achieve this by using the transform method in the Expression shape while maintaining your overall business process intact.</span></span>  
  
## <a name="transforming-messages"></a><span data-ttu-id="09ddb-108">メッセージの変換</span><span class="sxs-lookup"><span data-stu-id="09ddb-108">Transforming messages</span></span>  
 <span data-ttu-id="09ddb-109">次のサンプル コードを使用してプログラムでメッセージを変換することができます、**メッセージの割り当て**図形。</span><span class="sxs-lookup"><span data-stu-id="09ddb-109">You can use the following sample code to programmatically transform the messages in the **Message Assignment** shape:</span></span>  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg);  
```  
  
 <span data-ttu-id="09ddb-110">この例では、MyMapType は型の変数として宣言されて**System.Type**オーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="09ddb-110">In this example, MyMapType is declared as a variable of type **System.Type** in the orchestration.</span></span> <span data-ttu-id="09ddb-111">MyMapName は、BizTalk プロジェクトで既に作成されているマップの名前です。</span><span class="sxs-lookup"><span data-stu-id="09ddb-111">MyMapName is the name of a map that was already created in your BizTalk project.</span></span> <span data-ttu-id="09ddb-112">別の BizTalk アセンブリ内にあるマップを参照する場合は、BizTalk プロジェクトでそのアセンブリを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09ddb-112">If you would like to reference a map that is in a separate BizTalk assembly, you will need to reference that assembly in your BizTalk project.</span></span> <span data-ttu-id="09ddb-113">MyInputMsg は送信元メッセージ、MyOutputMsg は変換先のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="09ddb-113">MyInputMsg is the source message and MyOutputMsg is the destination message.</span></span> <span data-ttu-id="09ddb-114">マップが複数のソースのメッセージを受け取る場合は、メッセージを変換する、次のサンプル コードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="09ddb-114">If your map takes multiple source messages, then you can use the following sample code to transform the messages:</span></span>  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg1, MyInputMsg2);  
```  
  
> [!NOTE]
>  <span data-ttu-id="09ddb-115">を複数のソースのメッセージがある場合は、マップに示されている入力メッセージ部分の番号に式の順序で配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09ddb-115">If you have multiple source messages, they must be placed in order in the expression with respect to the input message part number indicated in the map.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="09ddb-116">動的式図形内のメッセージを変換する場合は、ユーザー コードのコンパイル済みのマップをキャッシュのキャッシュを記述し、式図形内のキャッシュを使用して、メッセージの変換を実行する前に、マップを取得することを勧めします。</span><span class="sxs-lookup"><span data-stu-id="09ddb-116">When dynamic transforming messages in the Expression shape, we recommend that you write a cache in user code for caching the compiled maps, and then use the cache in the Expression shape to retrieve the maps before performing the message transformation.</span></span> <span data-ttu-id="09ddb-117">マップをキャッシュしない場合は、共通言語ランタイム (CLR) 大幅に増大するメモリを確認できます。</span><span class="sxs-lookup"><span data-stu-id="09ddb-117">If you are not caching the maps, it is possible to see Common Language Runtime (CLR) memory grow significantly.</span></span> <span data-ttu-id="09ddb-118">動的マッピングは、.NET ランタイムが、オーケストレーションが完了するまでの各変換の大きなオブジェクト ヒープに配置されている .NET の証拠オブジェクトとこのオブジェクトとその結果が破棄されませんが、コード アクセス チェックを実行することが必要です。</span><span class="sxs-lookup"><span data-stu-id="09ddb-118">Dynamic mapping requires that the .NET Runtime perform code access check which results in a .NET Evidence object being placed in the Large Object Heap for each transformation and this object is not disposed of until the orchestration completes.</span></span> <span data-ttu-id="09ddb-119">そのため、これらの種類に同時に発生する変換の多くがある場合に、メモリ使用量が大幅に上昇、メモリ不足の例外にもつながりますを参照してください可能性があります。</span><span class="sxs-lookup"><span data-stu-id="09ddb-119">Therefore, when there are a lot of these types of transforms occurring simultaneously, you may see the memory usage increase substantially which can also lead to the out of memory exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09ddb-120">参照</span><span class="sxs-lookup"><span data-stu-id="09ddb-120">See Also</span></span>  
 <span data-ttu-id="09ddb-121">[オーケストレーション図形](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="09ddb-121">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 [<span data-ttu-id="09ddb-122">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="09ddb-122">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)