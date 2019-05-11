---
title: ボキャブラリの定義を変更する方法 |Microsoft Docs
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
ms.openlocfilehash: dcbe156f026d45badc13f88f0caf79bb347889db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336004"
---
# <a name="how-to-modify-vocabulary-definitions"></a><span data-ttu-id="43fac-102">ボキャブラリの定義を変更する方法</span><span class="sxs-lookup"><span data-stu-id="43fac-102">How to Modify Vocabulary Definitions</span></span>
<span data-ttu-id="43fac-103">表示名を変更したり、表示名に関連付けられているバインドを変更するのには、ボキャブラリの定義ウィザードを使用して、ボキャブラリの未公開バージョンのボキャブラリの定義を変更できます。</span><span class="sxs-lookup"><span data-stu-id="43fac-103">You can modify a vocabulary definition in an unpublished version of a vocabulary by using the Vocabulary Definition Wizard to change the display name or to change the binding associated with the display name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43fac-104">すべての要素を変更できます。</span><span class="sxs-lookup"><span data-stu-id="43fac-104">Not all elements can be modified.</span></span>  
  
 <span data-ttu-id="43fac-105">このトピックには、次のタスクの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="43fac-105">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="43fac-106">ボキャブラリの定義を変更するには</span><span class="sxs-lookup"><span data-stu-id="43fac-106">To modify a vocabulary definition</span></span>  
  
-   <span data-ttu-id="43fac-107">ボキャブラリまたはボキャブラリの定義に、ファクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="43fac-107">To add a fact to a vocabulary or vocabulary definition</span></span>  
  
### <a name="to-modify-a-vocabulary-definition"></a><span data-ttu-id="43fac-108">ボキャブラリの定義を変更するには</span><span class="sxs-lookup"><span data-stu-id="43fac-108">To modify a vocabulary definition</span></span>  
  
1.  <span data-ttu-id="43fac-109">ボキャブラリの定義を右クリックし、をクリックし、**変更**します。</span><span class="sxs-lookup"><span data-stu-id="43fac-109">Right-click the vocabulary definition, and then click **Modify**.</span></span>  
  
2.  <span data-ttu-id="43fac-110">新しいボキャブラリの定義を作成すると、ボキャブラリの定義ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="43fac-110">Use the Vocabulary Definition Wizard as you would to create a new vocabulary definition.</span></span>  
  
### <a name="to-add-a-fact-to-a-vocabulary-or-vocabulary-definition"></a><span data-ttu-id="43fac-111">ボキャブラリまたはボキャブラリの定義に、ファクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="43fac-111">To add a fact to a vocabulary or vocabulary definition</span></span>  
  
1.  <span data-ttu-id="43fac-112">[ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブをクリックし、更新する未公開のボキャブラリのバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="43fac-112">In the Facts Explorer window, click the **Vocabularies** tab, and select the unpublished vocabulary version that you want to update.</span></span>  
  
2.  <span data-ttu-id="43fac-113">クリックして**データベース**、 **XML スキーマ**、または **.NET クラス**します。</span><span class="sxs-lookup"><span data-stu-id="43fac-113">Click **Databases**, **XML Schemas**, or **.NET Classes**.</span></span>  
  
3.  <span data-ttu-id="43fac-114">必要なファクトにデータのソース階層内を移動します。</span><span class="sxs-lookup"><span data-stu-id="43fac-114">Navigate through the data source hierarchy to the fact you want.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="43fac-115">実際には、データベース テーブルまたはデータベース テーブルの列、XML ドキュメントの要素または属性、または、.NET クラスまたはクラス メンバーができます。</span><span class="sxs-lookup"><span data-stu-id="43fac-115">The fact can be a database table or database table column, an XML document element or attribute, or a .NET class or class member.</span></span>  
  
4.  <span data-ttu-id="43fac-116">ファクトをクリックし、マウス ボタンを押したままです。</span><span class="sxs-lookup"><span data-stu-id="43fac-116">Click the fact and hold down the mouse button.</span></span>  
  
5.  <span data-ttu-id="43fac-117">経由で、ファクトをドラッグして、**ボキャブラリ**タブ。</span><span class="sxs-lookup"><span data-stu-id="43fac-117">Drag the fact over the **Vocabularies** tab.</span></span>  
  
     <span data-ttu-id="43fac-118">**ボキャブラリ**タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="43fac-118">The **Vocabularies** tab opens.</span></span>  
  
6.  <span data-ttu-id="43fac-119">ボキャブラリのバージョンを変更するのには、という事実をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="43fac-119">Drag the fact to the vocabulary version you want to modify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43fac-120">参照</span><span class="sxs-lookup"><span data-stu-id="43fac-120">See Also</span></span>  
 [<span data-ttu-id="43fac-121">ボキャブラリの定義を作成する方法</span><span class="sxs-lookup"><span data-stu-id="43fac-121">How to Create Vocabulary Definitions</span></span>](../core/how-to-create-vocabulary-definitions.md)