---
title: "定数値を追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f46bf66e-caf2-4352-930f-c3c43a5717c3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 398e2f4d176fdfab866cc8c87ce19aaf523a1b03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-constant-values"></a><span data-ttu-id="052df-102">定数値を追加する方法</span><span class="sxs-lookup"><span data-stu-id="052df-102">How to Add Constant Values</span></span>
<span data-ttu-id="052df-103">マップをテストする際、テスト中に使用する定数値を設定する場合があります。</span><span class="sxs-lookup"><span data-stu-id="052df-103">When testing maps, you will sometimes want to set constant values for use during the test.</span></span>  
  
## <a name="set-constant-values-for-nodes-in-the-source-or-destination-schema-trees"></a><span data-ttu-id="052df-104">ソースまたは変換先のスキーマ ツリー ノードの定数値を設定します。</span><span class="sxs-lookup"><span data-stu-id="052df-104">Set constant values for nodes in the source or destination schema trees</span></span>  
  
1.  <span data-ttu-id="052df-105">送信元スキーマ ツリーまたは送信先スキーマ ツリーのレコードまたはフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="052df-105">Select a record or field in the source or destination schema trees.</span></span>  
  
2.  <span data-ttu-id="052df-106">[プロパティ] ウィンドウで、**全般**カテゴリを使用して、**値**プロパティを選択しているレコードまたはフィールドの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="052df-106">In the Properties window, in the **General** category, use the **Value** property to enter a value for the selected record or field.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="052df-107">関連付けることができますのみ値を持つレコード、**コンテンツ**プロパティに設定**テキストのみ**または**Mixed**です。</span><span class="sxs-lookup"><span data-stu-id="052df-107">You can only associate a value with a record with its **Content** property set to **Text Only** or **Mixed**.</span></span>  
  
 <span data-ttu-id="052df-108">設定した場合、送信元スキーマ内のノードに対して、**値**プロパティを**\<空 >**、送信元スキーマの生成されたインスタンス メッセージには、それぞれのノードに空の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="052df-108">For a node in source schema, if you set the **Value** property to **\<empty>**, the generated instance message for the source schema contains an empty value for the respective node.</span></span>  
  
 <span data-ttu-id="052df-109">送信先スキーマのフィールドをすべては使用しないことがあります。つまり、送信先スキーマのフィールドには、受信リンクが指定されないものもあります。</span><span class="sxs-lookup"><span data-stu-id="052df-109">Sometimes, you do not use all the fields in the target schema, i.e. some of the fields in the target schema do not have any incoming links.</span></span> <span data-ttu-id="052df-110">このような場合、マップのテスト操作によってスローされるエラーを提供する、 **TestMap 入力の検証**または**TestMap 出力の検証**プロパティに設定されます**True**です。</span><span class="sxs-lookup"><span data-stu-id="052df-110">In such cases, the Test Map operation throws error, provided that the **Validate TestMap Input** or **Validate TestMap Output** properties are set to **True**.</span></span> <span data-ttu-id="052df-111">このような場合はマップのテスト エラーを避けるためには、次のように設定します。、**値**いずれかの定数値にノードのプロパティまたは**\<空 >**です。</span><span class="sxs-lookup"><span data-stu-id="052df-111">To avoid Test Map errors in such cases, set the **Value** property of the node to either a constant value or **\<empty>**.</span></span> <span data-ttu-id="052df-112">使用して**\<空 >**未使用の送信先スキーマのフィールドの任意のデータを設定したくない場合。</span><span class="sxs-lookup"><span data-stu-id="052df-112">Use **\<empty>** if you do not want to set arbitrary data for unused target schema fields.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="052df-113">参照</span><span class="sxs-lookup"><span data-stu-id="052df-113">See Also</span></span>  
[<span data-ttu-id="052df-114">検証し、マップのテスト</span><span class="sxs-lookup"><span data-stu-id="052df-114">Validate and test your maps</span></span>](../core/how-to-configure-map-validation-and-test-parameters.md)