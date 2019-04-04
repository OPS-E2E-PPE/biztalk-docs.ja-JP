---
title: 既存のリンクを管理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0db213b9-df84-4ebd-a59f-7691774d5031
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cacb316d9783692dd55cbdbbbda92b6f55d98a3a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982891"
---
# <a name="how-to-manage-existing-links"></a><span data-ttu-id="5993d-102">既存のリンクを管理する方法</span><span class="sxs-lookup"><span data-stu-id="5993d-102">How to Manage Existing Links</span></span>
<span data-ttu-id="5993d-103">リンクの送信元や送信先の変更、リンクの名前付けや名前の変更、およびリンクの削除などが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5993d-103">Sometimes you may need to change the source or destination of a link, name or rename a link, or delete a link.</span></span> <span data-ttu-id="5993d-104">このトピックでは、このようなリンクに関する操作を実行する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="5993d-104">This topic provides step-by-step instructions for performing these types of link operations.</span></span>  
  
### <a name="to-change-the-source-or-destination-of-a-link"></a><span data-ttu-id="5993d-105">リンクの送信元または送信先を変更するには</span><span class="sxs-lookup"><span data-stu-id="5993d-105">To change the source or destination of a link</span></span>  
  
1.  <span data-ttu-id="5993d-106">BizTalk マッパーのグリッド ページで、リンクをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="5993d-106">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
     <span data-ttu-id="5993d-107">グリッド ページ内の選択したリンクのエンドポイントが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="5993d-107">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2.  <span data-ttu-id="5993d-108">リンクのいずれかのエンドポイントを、新たに接続するスキーマ ノードまたは Functoid にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="5993d-108">Drag either endpoint of the link to the new schema node or functoid to which you want it to connect it.</span></span>  
  
     <span data-ttu-id="5993d-109">エンドポイントをドラッグしている間は、カーソルが十字型になります。</span><span class="sxs-lookup"><span data-stu-id="5993d-109">As you drag an endpoint, the cursor becomes a crosshair.</span></span> <span data-ttu-id="5993d-110">リンクを受け付けることができないスキーマ ノードや Functoid (またはその他のオブジェクト) にドラッグすると、円の中に 1 本の線が描かれた形にカーソルが変化します。</span><span class="sxs-lookup"><span data-stu-id="5993d-110">If you point to a schema node or functoid (or other object) which cannot accept the link, the cursor becomes a circle with a line through it.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="5993d-111">2 つ以上の入力リンクを 1 つの Functoid に接続して、これらの入力リンクのいずれかを送信元スキーマの他のノードまたは他の Functoid にリダイレクトする場合、元の Functoid に対する入力パラメーターの順序は維持されません。</span><span class="sxs-lookup"><span data-stu-id="5993d-111">If you have two or more input links connected to a functoid and you redirect one or more of those input links to other nodes in the source schema or to other functoids, the order of the input parameters to the original functoid may not be preserved.</span></span> <span data-ttu-id="5993d-112">使用して、**構成\<Functoid\> Functoid**  ダイアログ ボックスおよびを並べ替えるには必要に応じて、入力パラメーターの結果として得られる順序を確認します。</span><span class="sxs-lookup"><span data-stu-id="5993d-112">Use the **Configure \<Functoid\> Functoid** dialog box to review the resulting order of the input parameters and to reorder them if necessary.</span></span> <span data-ttu-id="5993d-113">Functoid の入力パラメーターの順序変更の詳細については、[Functoid プロパティの編集および入力パラメーター](../core/editing-functoid-properties-and-input-parameters.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5993d-113">For more information about reordering the input parameters of a functoid, see [Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md).</span></span>  
  
### <a name="to-setedit-the-label-of-a-link"></a><span data-ttu-id="5993d-114">リンクのラベルを設定/編集するには</span><span class="sxs-lookup"><span data-stu-id="5993d-114">To set/edit the label of a link</span></span>  
  
1. <span data-ttu-id="5993d-115">BizTalk マッパーのグリッド ページで、リンクをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="5993d-115">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
    <span data-ttu-id="5993d-116">グリッド ページ内の選択したリンクのエンドポイントが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="5993d-116">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2. <span data-ttu-id="5993d-117">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、リンクを使用して、名前を付けます (新規)、**ラベル**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="5993d-117">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, provide a (new) name for the link using the **Label** property.</span></span>  
  
### <a name="to-delete-a-link"></a><span data-ttu-id="5993d-118">リンクを削除するには</span><span class="sxs-lookup"><span data-stu-id="5993d-118">To delete a link</span></span>  
  
1.  <span data-ttu-id="5993d-119">BizTalk マッパーのグリッド ページで、リンクをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="5993d-119">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
     <span data-ttu-id="5993d-120">グリッド ページ内の選択したリンクのエンドポイントが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="5993d-120">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2.  <span data-ttu-id="5993d-121">**編集** メニューのをクリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="5993d-121">On the **Edit** menu, click **Delete**.</span></span>  
  
     <span data-ttu-id="5993d-122">また DEL キーを押しますまたはリンクを右クリックしてをクリックして**削除**ショートカット メニューの します。</span><span class="sxs-lookup"><span data-stu-id="5993d-122">You can also press the DELETE key or right-click the link and click **Delete** on the shortcut menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5993d-123">複数のリンクおよび Functoid を一括で選択し、1 つの操作でそれらを削除できます。</span><span class="sxs-lookup"><span data-stu-id="5993d-123">You can bulk-select multiple link(s) and/or functoid(s) and then delete them in one operation.</span></span> <span data-ttu-id="5993d-124">リンクや Functoid の一括削除を取り消したり、やり直したりできます。</span><span class="sxs-lookup"><span data-stu-id="5993d-124">You can undo or redo the bulk deletion of link(s) and/or functoid(s).</span></span> <span data-ttu-id="5993d-125">詳細については、元に戻すおよびやり直し操作を参照してください。[を元に戻すまたはユーザーの操作をやり直す方法](../core/how-to-undo-or-redo-user-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="5993d-125">For more information about undo and redo operations, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5993d-126">参照</span><span class="sxs-lookup"><span data-stu-id="5993d-126">See Also</span></span>  
 [<span data-ttu-id="5993d-127">リンクを使用してレコードとフィールド マッピングを指定する</span><span class="sxs-lookup"><span data-stu-id="5993d-127">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)