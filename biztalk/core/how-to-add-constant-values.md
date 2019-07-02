---
title: 定数値を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f46bf66e-caf2-4352-930f-c3c43a5717c3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6510c278be4f64814dd690d275e42c6739587e4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387236"
---
# <a name="how-to-add-constant-values"></a><span data-ttu-id="32405-102">定数値を追加する方法</span><span class="sxs-lookup"><span data-stu-id="32405-102">How to Add Constant Values</span></span>
<span data-ttu-id="32405-103">マップをテストするときに、テスト中に使用する定数値を設定するが場合があります。</span><span class="sxs-lookup"><span data-stu-id="32405-103">When testing maps, you will sometimes want to set constant values for use during the test.</span></span>  
  
## <a name="set-constant-values-for-nodes-in-the-source-or-destination-schema-trees"></a><span data-ttu-id="32405-104">送信元または送信先のスキーマ ツリー ノードの定数値を設定します。</span><span class="sxs-lookup"><span data-stu-id="32405-104">Set constant values for nodes in the source or destination schema trees</span></span>  
  
1. <span data-ttu-id="32405-105">送信元または送信先スキーマ ツリーで、レコードまたはフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="32405-105">Select a record or field in the source or destination schema trees.</span></span>  
  
2. <span data-ttu-id="32405-106">[プロパティ] ウィンドウで、 **全般**カテゴリを使用して、 **値**プロパティを選択したレコードまたはフィールドの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="32405-106">In the Properties window, in the **General** category, use the **Value** property to enter a value for the selected record or field.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="32405-107">レコードを含む値を関連付けることができますのみその**コンテンツ**プロパティに設定**テキストのみ**または**Mixed**します。</span><span class="sxs-lookup"><span data-stu-id="32405-107">You can only associate a value with a record with its **Content** property set to **Text Only** or **Mixed**.</span></span>  
  
   <span data-ttu-id="32405-108">設定した場合、送信元スキーマ内のノードの **値**プロパティを **\<空\>** 、送信元スキーマの生成されたインスタンス メッセージには、それぞれに空の値が含まれています。ノードです。</span><span class="sxs-lookup"><span data-stu-id="32405-108">For a node in source schema, if you set the **Value** property to **\<empty\>**, the generated instance message for the source schema contains an empty value for the respective node.</span></span>  
  
   <span data-ttu-id="32405-109">場合によっては、ターゲット スキーマのすべてのフィールドを使用しない、つまり、ターゲット スキーマのフィールドのいくつか必要はありません受信リンク。</span><span class="sxs-lookup"><span data-stu-id="32405-109">Sometimes, you do not use all the fields in the target schema, i.e. some of the fields in the target schema do not have any incoming links.</span></span> <span data-ttu-id="32405-110">マップのテスト操作をこのような場合に、提供する、エラーをスローします、 **TestMap 入力の検証**または**TestMap 出力の検証**プロパティに設定されます**True**します。</span><span class="sxs-lookup"><span data-stu-id="32405-110">In such cases, the Test Map operation throws error, provided that the **Validate TestMap Input** or **Validate TestMap Output** properties are set to **True**.</span></span> <span data-ttu-id="32405-111">このような場合、マップのテスト エラーを回避するには、設定、 **値**定数の値にノードのプロパティまたは **\<空\>** 。</span><span class="sxs-lookup"><span data-stu-id="32405-111">To avoid Test Map errors in such cases, set the **Value** property of the node to either a constant value or **\<empty\>**.</span></span> <span data-ttu-id="32405-112">使用 **\<空\>** 未使用の送信先スキーマのフィールドの任意のデータを設定したくない場合。</span><span class="sxs-lookup"><span data-stu-id="32405-112">Use **\<empty\>** if you do not want to set arbitrary data for unused target schema fields.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32405-113">参照</span><span class="sxs-lookup"><span data-stu-id="32405-113">See Also</span></span>  
[<span data-ttu-id="32405-114">マップの検証とテスト</span><span class="sxs-lookup"><span data-stu-id="32405-114">Validate and test your maps</span></span>](../core/how-to-configure-map-validation-and-test-parameters.md)