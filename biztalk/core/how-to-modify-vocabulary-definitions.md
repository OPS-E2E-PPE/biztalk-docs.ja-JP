---
title: ボキャブラリの定義を変更する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- vocabularies, facts
- modifying, vocabularies
- vocabularies, definitions
- vocabularies, modifying
ms.assetid: 866bb9b9-34e1-4a05-a84e-540c7f7fae3b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6aa62ebf0adda5798824003fa25cf1ed07b62932
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254170"
---
# <a name="how-to-modify-vocabulary-definitions"></a><span data-ttu-id="62460-102">ボキャブラリの定義を変更する方法</span><span class="sxs-lookup"><span data-stu-id="62460-102">How to Modify Vocabulary Definitions</span></span>
<span data-ttu-id="62460-103">ボキャブラリの定義ウィザードを使用して、未公開バージョンのボキャブラリに関する、ボキャブラリの定義を変更できます。ボキャブラリの定義ウィザードで、表示名または表示名に関連するバインドを変更します。</span><span class="sxs-lookup"><span data-stu-id="62460-103">You can modify a vocabulary definition in an unpublished version of a vocabulary by using the Vocabulary Definition Wizard to change the display name or to change the binding associated with the display name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62460-104">すべての要素を変更できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="62460-104">Not all elements can be modified.</span></span>  
  
 <span data-ttu-id="62460-105">このトピックでは、次の操作の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="62460-105">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="62460-106">ボキャブラリの定義を変更するには</span><span class="sxs-lookup"><span data-stu-id="62460-106">To modify a vocabulary definition</span></span>  
  
-   <span data-ttu-id="62460-107">ボキャブラリまたはボキャブラリの定義へファクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="62460-107">To add a fact to a vocabulary or vocabulary definition</span></span>  
  
### <a name="to-modify-a-vocabulary-definition"></a><span data-ttu-id="62460-108">ボキャブラリの定義を変更するには</span><span class="sxs-lookup"><span data-stu-id="62460-108">To modify a vocabulary definition</span></span>  
  
1.  <span data-ttu-id="62460-109">ボキャブラリの定義を右クリックし、をクリックして**変更**です。</span><span class="sxs-lookup"><span data-stu-id="62460-109">Right-click the vocabulary definition, and then click **Modify**.</span></span>  
  
2.  <span data-ttu-id="62460-110">新しいボキャブラリの定義を作成する場合は、ボキャブラリの定義ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="62460-110">Use the Vocabulary Definition Wizard as you would to create a new vocabulary definition.</span></span>  
  
### <a name="to-add-a-fact-to-a-vocabulary-or-vocabulary-definition"></a><span data-ttu-id="62460-111">ボキャブラリまたはボキャブラリの定義へファクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="62460-111">To add a fact to a vocabulary or vocabulary definition</span></span>  
  
1.  <span data-ttu-id="62460-112">[ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブをクリックし、更新する未公開のボキャブラリのバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="62460-112">In the Facts Explorer window, click the **Vocabularies** tab, and select the unpublished vocabulary version that you want to update.</span></span>  
  
2.  <span data-ttu-id="62460-113">をクリックして**データベース**、 **XML スキーマ**、または **.NET クラス**です。</span><span class="sxs-lookup"><span data-stu-id="62460-113">Click **Databases**, **XML Schemas**, or **.NET Classes**.</span></span>  
  
3.  <span data-ttu-id="62460-114">データ ソース階層を移動して、該当するファクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="62460-114">Navigate through the data source hierarchy to the fact you want.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="62460-115">ファクトは、データベース テーブルまたはデータベース テーブルの列、ドキュメントの要素または属性、あるいは .NET クラスまたはクラス メンバーになります。</span><span class="sxs-lookup"><span data-stu-id="62460-115">The fact can be a database table or database table column, an XML document element or attribute, or a .NET class or class member.</span></span>  
  
4.  <span data-ttu-id="62460-116">ファクトをクリックし、マウスのボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="62460-116">Click the fact and hold down the mouse button.</span></span>  
  
5.  <span data-ttu-id="62460-117">経由で、ファクトをドラッグして、**ボキャブラリ**タブです。</span><span class="sxs-lookup"><span data-stu-id="62460-117">Drag the fact over the **Vocabularies** tab.</span></span>  
  
     <span data-ttu-id="62460-118">**ボキャブラリ**タブが開きます。</span><span class="sxs-lookup"><span data-stu-id="62460-118">The **Vocabularies** tab opens.</span></span>  
  
6.  <span data-ttu-id="62460-119">変更するボキャブラリのバージョンにファクトをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="62460-119">Drag the fact to the vocabulary version you want to modify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62460-120">参照</span><span class="sxs-lookup"><span data-stu-id="62460-120">See Also</span></span>  
 [<span data-ttu-id="62460-121">ボキャブラリの定義を作成する方法</span><span class="sxs-lookup"><span data-stu-id="62460-121">How to Create Vocabulary Definitions</span></span>](../core/how-to-create-vocabulary-definitions.md)