---
title: マップの警告とエラーを解決する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8a3e7f3-c96c-4d3d-9f7c-d2bfd9ace4fd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68ec8b45d3e336c12d6a72f8827c536605ad7ccb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384136"
---
# <a name="how-to-resolve-map-warnings-and-errors"></a><span data-ttu-id="c6663-102">マップの警告とエラーを解決する方法</span><span class="sxs-lookup"><span data-stu-id="c6663-102">How to Resolve Map Warnings and Errors</span></span>
<span data-ttu-id="c6663-103">マップをコンパイルするときに警告やエラーが、コンパイル処理があります。</span><span class="sxs-lookup"><span data-stu-id="c6663-103">When you compile a map, you may find that warnings and errors result from the compilation process.</span></span>  
  
## <a name="resolve-warnings-and-errors-when-building-a-map"></a><span data-ttu-id="c6663-104">マップを構築するときに、警告およびエラーを解決します。</span><span class="sxs-lookup"><span data-stu-id="c6663-104">Resolve warnings and errors when building a map</span></span>  
  
1.  <span data-ttu-id="c6663-105">リンクおよび functoid エラーの場合で、**エラー一覧**ウィンドウで、任意の説明をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6663-105">For link and functoid errors, in the **Error List** window, double-click any description.</span></span>  
  
     <span data-ttu-id="c6663-106">リンク、functoid、またはエラーに関連付けられているスキーマのノードが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6663-106">The link, functoid, or the schema node associated with the error is highlighted.</span></span> <span data-ttu-id="c6663-107">問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="c6663-107">Resolve the issue.</span></span>  
  
2.  <span data-ttu-id="c6663-108">レビュー、**説明**領域で、**エラー一覧**ウィンドウをその他のエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="c6663-108">Review the **Description** area in the **Error List** window to determine additional errors.</span></span>  
  
3.  <span data-ttu-id="c6663-109">をクリックして、**出力**警告およびエラー メッセージの追加情報を表示するのには、[ウィンドウ] タブ。</span><span class="sxs-lookup"><span data-stu-id="c6663-109">Click the **Output** window tab to view additional warning and error message information.</span></span>  
  
4.  <span data-ttu-id="c6663-110">ソリューション エクスプ ローラーでマップ ファイル名を右クリックし をクリックし、すべての問題を解決したら**マップのテスト**または**ソリューションのビルド**にします。</span><span class="sxs-lookup"><span data-stu-id="c6663-110">After you have resolved all issues, right-click the map file name in Solution Explorer, and then click **Test Map** or **Build Solution**, as the case may be.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6663-111">警告が表示されたらの場合は、問題がいくつかのグリッド ページにわたって存在可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c6663-111">If a warning appears, the problem might exist over several grid pages.</span></span> <span data-ttu-id="c6663-112">たとえば、グリッド ページ 1 のレコードを含むがある (という名前**項目**)、送信元スキーマ ツリーでは、レコードにリンク (という名前**数**) 送信先スキーマ ツリーで。</span><span class="sxs-lookup"><span data-stu-id="c6663-112">For example, you have grid page 1 with a record (named **Item**) in the source schema tree linked to a record (named **Number**) in the destination schema tree.</span></span> <span data-ttu-id="c6663-113">レコードが存在するグリッド ページ 2 (という名前の**製品**)、送信元スキーマ ツリーでは、同じリンク**数**送信先スキーマ ツリー内のレコード。</span><span class="sxs-lookup"><span data-stu-id="c6663-113">On grid page 2 you have a record (named **Product**) in the source schema tree linked to the same **Number** record in the destination schema tree.</span></span> <span data-ttu-id="c6663-114">このシナリオで、同じレコードを複数の入力があることを示す警告メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c6663-114">In this scenario, a warning message is generated stating that you have multiple inputs to the same record.</span></span> <span data-ttu-id="c6663-115">ただし 1 のグリッド ページを表示する場合への入力を 1 つだけを表示、**数**レコード。</span><span class="sxs-lookup"><span data-stu-id="c6663-115">However if you view grid page 1, you see only one input into the **Number** record.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c6663-116">参照</span><span class="sxs-lookup"><span data-stu-id="c6663-116">See Also</span></span>  
 <span data-ttu-id="c6663-117">[コンパイルして、マップのテスト](../core/compiling-and-testing-maps.md) </span><span class="sxs-lookup"><span data-stu-id="c6663-117">[Compiling and Testing Maps](../core/compiling-and-testing-maps.md) </span></span>  
 <span data-ttu-id="c6663-118">[BizTalk マッパー エラー](../core/biztalk-mapper-errors.md) </span><span class="sxs-lookup"><span data-stu-id="c6663-118">[BizTalk Mapper Errors](../core/biztalk-mapper-errors.md) </span></span>  
 [<span data-ttu-id="c6663-119">マップのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c6663-119">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)