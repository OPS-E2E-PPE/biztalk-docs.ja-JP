---
title: ループ パスが |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Looping functoids, paths
- maps, conditional looping
ms.assetid: 4612dc2d-2c39-427d-88ac-65f9e85873c7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37cc3178228c1d80cfd9ffb8a27d974610ea0c2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330202"
---
# <a name="loop-paths"></a><span data-ttu-id="77915-102">ループ パス</span><span class="sxs-lookup"><span data-stu-id="77915-102">Loop Paths</span></span>
<span data-ttu-id="77915-103">その Max Occurs プロパティが 1 より大きい場合は、スキーマ内の要素がループです。</span><span class="sxs-lookup"><span data-stu-id="77915-103">An element in a schema is looping if its Max Occurs property is greater than 1.</span></span> <span data-ttu-id="77915-104">ループ パスは、送信元スキーマのループ要素と送信先スキーマのループ要素間のリンクを描画するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="77915-104">A loop path occurs when you draw a link between a looping element in the source schema and a looping element in the destination schema.</span></span>  
  
## <a name="configuring-a-loop-path"></a><span data-ttu-id="77915-105">ループ パスの構成</span><span class="sxs-lookup"><span data-stu-id="77915-105">Configuring a Loop Path</span></span>  
 <span data-ttu-id="77915-106">ループ パスを作成するときに、BizTalk マッパーは、ループ レコードを自動的に処理します。</span><span class="sxs-lookup"><span data-stu-id="77915-106">BizTalk Mapper automatically handles the looping records when you create a loop path.</span></span>  
  
 <span data-ttu-id="77915-107">ループ パスは、送信元スキーマのループ レコードのフィールドを、送信先スキーマのループ レコードのフィールドにリンクさせることによって構成できます。</span><span class="sxs-lookup"><span data-stu-id="77915-107">You can configure a loop path in a map by linking a field in a looping record in the source schema to a field that is in a looping record in the destination schema.</span></span> <span data-ttu-id="77915-108">次の図に、食品調査レコードのみをマスター住所リストにコピーするマップを示します。</span><span class="sxs-lookup"><span data-stu-id="77915-108">The figure below shows a map that copies only food survey records into a master address list.</span></span>  
  
 <span data-ttu-id="77915-109">![ループ パスの使用方法を示すマップです。](../core/media/correct-loop-path-map.gif "correct_loop_path_map")</span><span class="sxs-lookup"><span data-stu-id="77915-109">![Map illustrating the use of a loop path.](../core/media/correct-loop-path-map.gif "correct_loop_path_map")</span></span>  
<span data-ttu-id="77915-110">ループ パス マップ</span><span class="sxs-lookup"><span data-stu-id="77915-110">Loop Path Map</span></span>  
  
## <a name="multiple-loop-paths"></a><span data-ttu-id="77915-111">ループ パスが複数あります</span><span class="sxs-lookup"><span data-stu-id="77915-111">Multiple Loop Paths</span></span>  
 <span data-ttu-id="77915-112">複数のループ レコードに含まれるフィールドと、単一のループ レコードに含まれるフィールドとをリンクさせた場合、マップ内に複数のループ パスが形成されます。</span><span class="sxs-lookup"><span data-stu-id="77915-112">A multiple loop path occurs in a map when you link fields contained by two or more looping records to fields contained in a single looping record.</span></span> <span data-ttu-id="77915-113">次の図は、単一のマスター住所リストに 2 つの異なるアンケートから収集されたアドレスを組み合わせようとしたを示します。</span><span class="sxs-lookup"><span data-stu-id="77915-113">The following figure shows an attempt to combine addresses collected from two different surveys into a single master address list.</span></span>  
  
 <span data-ttu-id="77915-114">![複数のループ パスを使用したマップ](../core/media/multiple-loop-path-map.gif "multiple_loop_path_map")</span><span class="sxs-lookup"><span data-stu-id="77915-114">![Map with multiple loop paths](../core/media/multiple-loop-path-map.gif "multiple_loop_path_map")</span></span>  
<span data-ttu-id="77915-115">複数のループ パスが含まれたマップ (正しくない)</span><span class="sxs-lookup"><span data-stu-id="77915-115">Map With Multiple Loop Paths (Incorrect)</span></span>  
  
 <span data-ttu-id="77915-116">このマップでは、予想どおりの結果にはなりません。</span><span class="sxs-lookup"><span data-stu-id="77915-116">This map will not produce the expected results.</span></span> <span data-ttu-id="77915-117">コンパイル時にマッパーにより複数のループ パスが検出されると、警告が生成され、既定では最初のループ パスが選択されます。</span><span class="sxs-lookup"><span data-stu-id="77915-117">When the Mapper encounters multiple loop paths during compilation, it produces a warning and selects the first loop path by default.</span></span> <span data-ttu-id="77915-118">単一のマスター住所リストに 2 つの異なるアドレスを結合するために使用して、**ループ**functoid マップの下に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="77915-118">In order to combine the two different addresses into a single master address list, use a **Looping** functoid as shown in the map below.</span></span>  
  
 <span data-ttu-id="77915-119">![ループ functoid の使用方法を示すマップです。](../core/media/loopingfunctoid.gif "loopingfunctoid")</span><span class="sxs-lookup"><span data-stu-id="77915-119">![Map illustrating the use of the looping functoid.](../core/media/loopingfunctoid.gif "loopingfunctoid")</span></span>  
<span data-ttu-id="77915-120">ループ Functoid マップ (正しい)</span><span class="sxs-lookup"><span data-stu-id="77915-120">Looping Functoid Map (Correct)</span></span>  
  
 <span data-ttu-id="77915-121">**ループ**functoid は、次のシナリオで複数のループ パスの代わりに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77915-121">The **Looping** functoid should be used instead of multiple loop paths in the following scenarios:</span></span>  
  
1.  <span data-ttu-id="77915-122">複数のループ パス シナリオで、マッパーによって必要な出力が生成されない場合。</span><span class="sxs-lookup"><span data-stu-id="77915-122">When the Mapper does not produce the desired output in a multiple loop paths scenario.</span></span>  
  
2.  <span data-ttu-id="77915-123">入力インスタンス メッセージ内の複数の繰り返し構造を、出力インスタンス メッセージ内の単一の繰り返し構造に結合する場合。</span><span class="sxs-lookup"><span data-stu-id="77915-123">To combine multiple repeating structures in an input instance message into a single repeating structure in the output instance message.</span></span>  
  
3.  <span data-ttu-id="77915-124">単一のレコードを複数のレコードにマッピングすることにより、フラット スキーマを階層構造のスキーマに変換する場合。</span><span class="sxs-lookup"><span data-stu-id="77915-124">To convert a flat schema to a hierarchical schema by mapping a single record to multiple records.</span></span> <span data-ttu-id="77915-125">これは、フラット スキーマを Microsoft Commerce Server カタログに変換する場合の一般的な操作です。</span><span class="sxs-lookup"><span data-stu-id="77915-125">This is a common operation in converting flat schemas to Microsoft Commerce Server catalogs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77915-126">参照</span><span class="sxs-lookup"><span data-stu-id="77915-126">See Also</span></span>  
 <span data-ttu-id="77915-127">[マップにループ Functoid を追加する方法](../core/how-to-add-looping-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="77915-127">[How to Add Looping Functoids to a Map](../core/how-to-add-looping-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="77915-128">ループ Functoid</span><span class="sxs-lookup"><span data-stu-id="77915-128">Looping Functoid</span></span>](../core/looping-functoid.md)