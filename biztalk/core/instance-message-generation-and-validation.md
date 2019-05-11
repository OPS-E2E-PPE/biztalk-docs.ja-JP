---
title: インスタンス メッセージの生成と検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a306846-3942-4ba1-a74e-6ead8deb0322
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e9a79a589dcedd9169de8d753922632cff2acb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331913"
---
# <a name="instance-message-generation-and-validation"></a><span data-ttu-id="54995-102">インスタンス メッセージの生成および検証</span><span class="sxs-lookup"><span data-stu-id="54995-102">Instance Message Generation and Validation</span></span>
<span data-ttu-id="54995-103">スキーマを検証した後は、サンプル インスタンス メッセージの生成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="54995-103">After you have validated a schema, you can use it to generate a sample instance message.</span></span> <span data-ttu-id="54995-104">サンプル インスタンス メッセージが表示される要素が含まれています、スキーマで指定された構造体の属性し、仮のデータを生成するために必要な場合。</span><span class="sxs-lookup"><span data-stu-id="54995-104">The sample instance message that is generated contains the element and attribute structure specified by the schema, and generate fake data where required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54995-105">データ生成メカニズムをいくつかのプロパティに指定された値に応じてデータの生成に十分に高度ながインスタンス メッセージを生成するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="54995-105">The data-generation mechanism used when generating instance messages is not sufficiently sophisticated to generate data according to values specified for several properties.</span></span> <span data-ttu-id="54995-106">たとえば、次のスキーマにすべての値が含まれています、**パターン**プロパティで使用可能な**制限**のカテゴリ**フィールド要素**ノードと**フィールド属性**ノードとその**Derived By**プロパティに設定されて**制限**、現状、への入力として、生成されたインスタンスメッセージを使用できません**インスタンスの検証**操作。</span><span class="sxs-lookup"><span data-stu-id="54995-106">For example, if the schema contains any values for the **Pattern** property, which is available in the **Restrictions** category for **Field Element** nodes and **Field Attribute** nodes when their **Derived By** property is set to **Restriction**, the generated instance message cannot be used as is, as input to the **Validate Instance** operation.</span></span>  
  
 <span data-ttu-id="54995-107">スキーマからサンプル インスタンス メッセージを生成するには、使用、**インスタンスの生成**ソリューション エクスプ ローラーでスキーマに関連付けられたショートカット メニューの コマンド。</span><span class="sxs-lookup"><span data-stu-id="54995-107">To generate a sample instance message from a schema, use the **Generate Instance** command on the shortcut menu associated with the schema in Solution Explorer.</span></span> <span data-ttu-id="54995-108">インスタンス メッセージの生成操作の結果が表示、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]出力ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="54995-108">The results of the instance message generation operation are reported in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Output window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54995-109">**インスタンスの生成**操作が含まれる、**スキーマの検証**操作。</span><span class="sxs-lookup"><span data-stu-id="54995-109">The **Generate Instance** operation includes the **Validate Schema** operation.</span></span> <span data-ttu-id="54995-110">検証に失敗した場合は、サンプル インスタンス メッセージは生成されません。</span><span class="sxs-lookup"><span data-stu-id="54995-110">If validation fails, no sample instance message will be generated.</span></span>  
  
 <span data-ttu-id="54995-111">生成されたインスタンス メッセージを格納する出力ファイルを構成する方法など、スキーマからインスタンス メッセージを生成する方法に関する詳細な手順についてを参照してください[インスタンス メッセージの生成](../core/how-to-generate-instance-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="54995-111">For detailed step-by-step instructions regarding how to generate an instance message from a schema, including how to configure an output file to contain the generated instance message, see [Generating Instance Messages](../core/how-to-generate-instance-messages.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54995-112">値を指定しない場合、**ルート参照**のプロパティ、**スキーマ**ノード、BizTalk エディターでは、スキーマの最初のルート ノードのインスタンス メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="54995-112">If you do not specify a value for the **Root Reference** property of the **Schema** node, BizTalk Editor generates an instance message for the first root node in the schema.</span></span> <span data-ttu-id="54995-113">値を指定する場合、**ルート参照**プロパティを BizTalk エディターには、指定したルートのインスタンス メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="54995-113">If you specify a value for the **Root Reference** property, BizTalk Editor generates an instance message for the specified root.</span></span>  
  
 <span data-ttu-id="54995-114">場合は、スキーマが検証されると、BizTalk エディターを使用して、インスタンス メッセージをそのスキーマに準拠しているかどうかを判断することができます。</span><span class="sxs-lookup"><span data-stu-id="54995-114">If you have validated your schema, you can use BizTalk Editor to determine whether an instance message conforms to that schema.</span></span>  
  
 <span data-ttu-id="54995-115">スキーマに対してインスタンス メッセージを検証するには、使用、**インスタンスの検証**ソリューション エクスプ ローラーでスキーマに関連付けられたショートカット メニューの コマンド。</span><span class="sxs-lookup"><span data-stu-id="54995-115">To validate an instance message against a schema, use the **Validate Instance** command on the shortcut menu associated with the schema in Solution Explorer.</span></span> <span data-ttu-id="54995-116">検証の結果が表示、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]出力ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="54995-116">The results of the validation are reported in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Output window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54995-117">生成された同じスキーマに対する検証が生成されたインスタンス メッセージに合格しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="54995-117">There are cases in which a generated instance message will not pass validation against the same schema from which it was generated.</span></span> <span data-ttu-id="54995-118">たとえばを使用して生成されたインスタンス メッセージを検証しようとした場合、**インスタンスの生成**BizTalk エディター、および関連するスキーマ内のコマンドが含まれる**フィールド要素**ノードまたは**フィールド属性**を持つノード、 **Derived By**プロパティに設定**制限**使用して、**パターン**プロパティを指定する、パターンは、対応するデータが準拠する、検証は失敗します。</span><span class="sxs-lookup"><span data-stu-id="54995-118">For example, if you attempt to validate an instance message that was generated by using the **Generate Instance** command in BizTalk Editor, and the relevant schema includes any **Field Element** nodes or **Field Attribute** nodes that have their **Derived By** property set to **Restriction** and which use the **Pattern** property to specify a pattern to which the corresponding data must conform, the validation will fail.</span></span> <span data-ttu-id="54995-119">これは、インスタンス メッセージを生成するときに使用されるデータ生成メカニズムが十分に指定された値に従ってデータを生成する高度なため、**パターン**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="54995-119">This is because the data-generation mechanism used when generating instance messages is not sufficiently sophisticated to generate data according to values specified for the **Pattern** property.</span></span> <span data-ttu-id="54995-120">それ以外の場合にも存在します。</span><span class="sxs-lookup"><span data-stu-id="54995-120">Other cases also exist.</span></span>  
  
 <span data-ttu-id="54995-121">検証するインスタンス メッセージを指定する方法など、インスタンス メッセージを検証する方法に関する詳細な手順についてを参照してください[スキーマの検証](../core/how-to-validate-schemas-in-visual-studio.md)です。</span><span class="sxs-lookup"><span data-stu-id="54995-121">For detailed step-by-step instructions regarding how to validate an instance message, including how to specify the instance message to be validated, see [Validating Schemas](../core/how-to-validate-schemas-in-visual-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54995-122">参照</span><span class="sxs-lookup"><span data-stu-id="54995-122">See Also</span></span>  
 <span data-ttu-id="54995-123">[スキーマについて](../core/about-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="54995-123">[About Schemas](../core/about-schemas.md) </span></span>  
 [<span data-ttu-id="54995-124">スキーマのテスト</span><span class="sxs-lookup"><span data-stu-id="54995-124">Testing Schemas</span></span>](../core/testing-schemas.md)