---
title: "マップの警告とエラーを解決する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8a3e7f3-c96c-4d3d-9f7c-d2bfd9ace4fd
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a2983a53bb47aa66d1564772d0f8e033132e5a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-resolve-map-warnings-and-errors"></a><span data-ttu-id="0b717-102">マップ作成時の警告およびエラーの解決方法</span><span class="sxs-lookup"><span data-stu-id="0b717-102">How to Resolve Map Warnings and Errors</span></span>
<span data-ttu-id="0b717-103">マップをコンパイルすると、コンパイル処理で警告やエラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0b717-103">When you compile a map, you may find that warnings and errors result from the compilation process.</span></span>  
  
## <a name="resolve-warnings-and-errors-when-building-a-map"></a><span data-ttu-id="0b717-104">マップを構築するときに、警告およびエラーを解決します。</span><span class="sxs-lookup"><span data-stu-id="0b717-104">Resolve warnings and errors when building a map</span></span>  
  
1.  <span data-ttu-id="0b717-105">リンクおよび functoid エラーの場合に、**エラー一覧**ウィンドウで、任意の説明をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b717-105">For link and functoid errors, in the **Error List** window, double-click any description.</span></span>  
  
     <span data-ttu-id="0b717-106">エラーに関連するリンク、Functoid、またはスキーマ ノードが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b717-106">The link, functoid, or the schema node associated with the error is highlighted.</span></span> <span data-ttu-id="0b717-107">問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="0b717-107">Resolve the issue.</span></span>  
  
2.  <span data-ttu-id="0b717-108">確認、**説明**内の領域、**エラー一覧**ウィンドウをその他のエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b717-108">Review the **Description** area in the **Error List** window to determine additional errors.</span></span>  
  
3.  <span data-ttu-id="0b717-109">クリックして、**出力**ウィンドウ タブには警告とエラー メッセージの追加情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="0b717-109">Click the **Output** window tab to view additional warning and error message information.</span></span>  
  
4.  <span data-ttu-id="0b717-110">ソリューション エクスプ ローラーで、マップ ファイル名を右クリックしをクリックし、すべての問題を解決したら**マップのテスト**または**ソリューションのビルド**、としてすることができます。</span><span class="sxs-lookup"><span data-stu-id="0b717-110">After you have resolved all issues, right-click the map file name in Solution Explorer, and then click **Test Map** or **Build Solution**, as the case may be.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0b717-111">警告が表示される場合、複数のグリッド ページに問題が存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0b717-111">If a warning appears, the problem might exist over several grid pages.</span></span> <span data-ttu-id="0b717-112">たとえば、グリッド ページ 1 で、レコードがある (という**項目**) 送信元スキーマ ツリー内のレコードにリンク (という名前**数**) 送信先スキーマ ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="0b717-112">For example, you have grid page 1 with a record (named **Item**) in the source schema tree linked to a record (named **Number**) in the destination schema tree.</span></span> <span data-ttu-id="0b717-113">2 のグリッド ページのレコードが存在する (名前付き**製品**) 送信元スキーマ ツリーで、同じにリンクして**数**送信先スキーマ ツリーでレコード。</span><span class="sxs-lookup"><span data-stu-id="0b717-113">On grid page 2 you have a record (named **Product**) in the source schema tree linked to the same **Number** record in the destination schema tree.</span></span> <span data-ttu-id="0b717-114">このシナリオでは、複数の入力が同じレコードがあることを示す警告メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="0b717-114">In this scenario, a warning message is generated stating that you have multiple inputs to the same record.</span></span> <span data-ttu-id="0b717-115">ただし 1 のグリッド ページを表示する場合に、1 つのみの入力を表示、**数**レコード。</span><span class="sxs-lookup"><span data-stu-id="0b717-115">However if you view grid page 1, you see only one input into the **Number** record.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0b717-116">参照</span><span class="sxs-lookup"><span data-stu-id="0b717-116">See Also</span></span>  
 <span data-ttu-id="0b717-117">[コンパイルして、マップのテスト](../core/compiling-and-testing-maps.md) </span><span class="sxs-lookup"><span data-stu-id="0b717-117">[Compiling and Testing Maps](../core/compiling-and-testing-maps.md) </span></span>  
 <span data-ttu-id="0b717-118">[BizTalk マッパーのエラー](../core/biztalk-mapper-errors.md) </span><span class="sxs-lookup"><span data-stu-id="0b717-118">[BizTalk Mapper Errors](../core/biztalk-mapper-errors.md) </span></span>  
 [<span data-ttu-id="0b717-119">マップのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0b717-119">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)