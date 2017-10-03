---
title: "インスタンス メッセージの生成および検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a306846-3942-4ba1-a74e-6ead8deb0322
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 964f9bd2ee2b8bb20872bc593723cea778b5ed81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="instance-message-generation-and-validation"></a><span data-ttu-id="d0d71-102">インスタンス メッセージの生成および検証</span><span class="sxs-lookup"><span data-stu-id="d0d71-102">Instance Message Generation and Validation</span></span>
<span data-ttu-id="d0d71-103">スキーマを検証した後、そのスキーマを使用して、サンプルのインスタンス メッセージを生成できます。</span><span class="sxs-lookup"><span data-stu-id="d0d71-103">After you have validated a schema, you can use it to generate a sample instance message.</span></span> <span data-ttu-id="d0d71-104">生成されるサンプルのインスタンス メッセージは、スキーマによって指定される要素と属性の構造を含んでいます。また、必要に応じて、仮のデータを生成します。</span><span class="sxs-lookup"><span data-stu-id="d0d71-104">The sample instance message that is generated contains the element and attribute structure specified by the schema, and generate fake data where required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0d71-105">インスタンス メッセージを生成する際に使用されるデータ生成メカニズムには、複数のプロパティで指定される値に応じてデータを生成するなどの高度な機能はありません。</span><span class="sxs-lookup"><span data-stu-id="d0d71-105">The data-generation mechanism used when generating instance messages is not sufficiently sophisticated to generate data according to values specified for several properties.</span></span> <span data-ttu-id="d0d71-106">たとえば、スキーマには、任意の値が含まれている場合、**パターン**で使用可能なプロパティ、**制限**のカテゴリ**フィールド要素**ノードと**フィールド属性**ノードとその**Derived By**プロパティに設定されている**制限**、への入力としては、生成されたインスタンスメッセージを使用できません**インスタンスの検証**操作します。</span><span class="sxs-lookup"><span data-stu-id="d0d71-106">For example, if the schema contains any values for the **Pattern** property, which is available in the **Restrictions** category for **Field Element** nodes and **Field Attribute** nodes when their **Derived By** property is set to **Restriction**, the generated instance message cannot be used as is, as input to the **Validate Instance** operation.</span></span>  
  
 <span data-ttu-id="d0d71-107">スキーマからサンプル インスタンス メッセージを生成するには、使用、**インスタンスの生成**ソリューション エクスプ ローラーでスキーマに関連付けられているショートカット メニューのコマンド。</span><span class="sxs-lookup"><span data-stu-id="d0d71-107">To generate a sample instance message from a schema, use the **Generate Instance** command on the shortcut menu associated with the schema in Solution Explorer.</span></span> <span data-ttu-id="d0d71-108">インスタンス メッセージの生成操作の結果は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の出力ウィンドウに出力されます。</span><span class="sxs-lookup"><span data-stu-id="d0d71-108">The results of the instance message generation operation are reported in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Output window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0d71-109">**インスタンスの生成**操作が含まれる、**スキーマの検証**操作します。</span><span class="sxs-lookup"><span data-stu-id="d0d71-109">The **Generate Instance** operation includes the **Validate Schema** operation.</span></span> <span data-ttu-id="d0d71-110">検証が失敗すると、サンプルのインスタンス メッセージは生成されません。</span><span class="sxs-lookup"><span data-stu-id="d0d71-110">If validation fails, no sample instance message will be generated.</span></span>  
  
 <span data-ttu-id="d0d71-111">生成されたインスタンス メッセージを格納する出力ファイルを構成する方法をなど、スキーマからインスタンス メッセージを生成する方法に関する詳細な手順を参照してください[インスタンス メッセージの生成](../core/how-to-generate-instance-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="d0d71-111">For detailed step-by-step instructions regarding how to generate an instance message from a schema, including how to configure an output file to contain the generated instance message, see [Generating Instance Messages](../core/how-to-generate-instance-messages.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0d71-112">値を指定しない場合、**ルート参照**のプロパティ、**スキーマ**ノード、BizTalk エディターは、スキーマの最初のルート ノードのインスタンス メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="d0d71-112">If you do not specify a value for the **Root Reference** property of the **Schema** node, BizTalk Editor generates an instance message for the first root node in the schema.</span></span> <span data-ttu-id="d0d71-113">値を指定する場合、**ルート参照**プロパティ、BizTalk エディターで、指定されたルートのインスタンス メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d0d71-113">If you specify a value for the **Root Reference** property, BizTalk Editor generates an instance message for the specified root.</span></span>  
  
 <span data-ttu-id="d0d71-114">スキーマを検証した後、BizTalk エディターを使用して、インスタンス メッセージがスキーマに準拠しているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d0d71-114">If you have validated your schema, you can use BizTalk Editor to determine whether an instance message conforms to that schema.</span></span>  
  
 <span data-ttu-id="d0d71-115">スキーマに対してインスタンス メッセージを確認する、**インスタンスの検証**ソリューション エクスプ ローラーでスキーマに関連付けられているショートカット メニューのコマンド。</span><span class="sxs-lookup"><span data-stu-id="d0d71-115">To validate an instance message against a schema, use the **Validate Instance** command on the shortcut menu associated with the schema in Solution Explorer.</span></span> <span data-ttu-id="d0d71-116">検証結果は [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の出力ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0d71-116">The results of the validation are reported in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Output window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0d71-117">生成されたインスタンス メッセージを生成元のスキーマを基に検証したときに、検証が合格しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0d71-117">There are cases in which a generated instance message will not pass validation against the same schema from which it was generated.</span></span> <span data-ttu-id="d0d71-118">たとえばを使用して生成されたインスタンス メッセージを検証しようとする場合、**インスタンスの生成**BizTalk エディター、および関連するスキーマ内のコマンドが含まれる**フィールド要素**ノードまたは**フィールド属性**を持つノードの**Derived By**プロパティに設定**制限**を使用して、**パターン**プロパティを指定する、対応するデータが準拠するパターンでは、検証は失敗します。</span><span class="sxs-lookup"><span data-stu-id="d0d71-118">For example, if you attempt to validate an instance message that was generated by using the **Generate Instance** command in BizTalk Editor, and the relevant schema includes any **Field Element** nodes or **Field Attribute** nodes that have their **Derived By** property set to **Restriction** and which use the **Pattern** property to specify a pattern to which the corresponding data must conform, the validation will fail.</span></span> <span data-ttu-id="d0d71-119">これは、インスタンス メッセージを生成するときに使用されるデータ生成メカニズムが指定された値に従ってデータを生成する十分な高度なではないため、**パターン**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="d0d71-119">This is because the data-generation mechanism used when generating instance messages is not sufficiently sophisticated to generate data according to values specified for the **Pattern** property.</span></span> <span data-ttu-id="d0d71-120">この他にも、検証が失敗する状況がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="d0d71-120">Other cases also exist.</span></span>  
  
 <span data-ttu-id="d0d71-121">検証するインスタンス メッセージを指定する方法など、インスタンス メッセージを検証する方法に関する詳細な手順を参照してください[スキーマの検証](../core/how-to-validate-schemas-in-visual-studio.md)です。</span><span class="sxs-lookup"><span data-stu-id="d0d71-121">For detailed step-by-step instructions regarding how to validate an instance message, including how to specify the instance message to be validated, see [Validating Schemas](../core/how-to-validate-schemas-in-visual-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0d71-122">参照</span><span class="sxs-lookup"><span data-stu-id="d0d71-122">See Also</span></span>  
 <span data-ttu-id="d0d71-123">[スキーマについて](../core/about-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="d0d71-123">[About Schemas](../core/about-schemas.md) </span></span>  
 [<span data-ttu-id="d0d71-124">スキーマのテスト</span><span class="sxs-lookup"><span data-stu-id="d0d71-124">Testing Schemas</span></span>](../core/testing-schemas.md)