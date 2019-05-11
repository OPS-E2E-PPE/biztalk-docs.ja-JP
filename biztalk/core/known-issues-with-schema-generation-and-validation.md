---
title: スキーマの生成と検証に関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df1eaa6c-0d3e-4aec-9de0-8b9817b7bb97
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f76e8043519672e5fe5b39bc9ce75b71dc0e95d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380717"
---
# <a name="known-issues-with-schema-generation-and-validation"></a><span data-ttu-id="56bb8-102">スキーマの生成と検証に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="56bb8-102">Known Issues with Schema Generation and Validation</span></span>
<span data-ttu-id="56bb8-103">このトピックでは、スキーマの生成と検証に関する既知の問題に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="56bb8-103">This topic provides information about known issues with schema generation and validation.</span></span>  
  
## <a name="an-instance-message-generated-for-a-positional-record-with-tags-could-be-incorrect"></a><span data-ttu-id="56bb8-104">タグを持つ位置指定レコードの生成されたインスタンス メッセージが正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="56bb8-104">An instance message generated for a positional record with tags could be incorrect</span></span>  
 <span data-ttu-id="56bb8-105">位置指定レコードのタグはフィールド内であることができますか、フィールドの間にまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="56bb8-105">For positional records, the tag can be within a field or can span between fields.</span></span> <span data-ttu-id="56bb8-106">いずれの場合も、生成されたインスタンスは無効になります、、解析エンジンで、解析ステージ中にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="56bb8-106">In either case, the instance generated will not be valid and will cause a failure in the Parsing Engine during the parsing stage.</span></span>  
  
 <span data-ttu-id="56bb8-107">タグ (子レコードまたはフィールドの子) 子の一部でない場合、この問題は発生しません。</span><span class="sxs-lookup"><span data-stu-id="56bb8-107">If the tag is not part of any children (child records or child fields), this problem will not occur.</span></span>  
  
 <span data-ttu-id="56bb8-108">この問題を回避するには、スキーマの既定値として、タグの実際の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="56bb8-108">To work around this issue, include the actual value of the tag as the default in the schema.</span></span> <span data-ttu-id="56bb8-109">フラット ファイル拡張機能の BizTalk エディターで設定できます、**固定値**または**既定値**タグの値を持つ適切な位置指定フィールドのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="56bb8-109">In the flat file extension of the BizTalk Editor, you can set the **Fixed Value** or **Default Value** property of the appropriate positional field with the value of the tag.</span></span>  
  
## <a name="an-instance-message-generated-for-a-field-with-some-restrictions-may-not-pass-validation"></a><span data-ttu-id="56bb8-110">いくつかの制限を持つフィールドに対して生成されたインスタンス メッセージでは、検証を渡すことができません。</span><span class="sxs-lookup"><span data-stu-id="56bb8-110">An instance message generated for a field with some restrictions may not pass validation</span></span>  
 <span data-ttu-id="56bb8-111">1 つまたは複数を含むスキーマからインスタンス メッセージを生成すると**フィールド要素**と**フィールド属性**など、制限メカニズムを使用して派生されているデータ型を持つノードときに、**パターン**プロパティを使用すると、このようなフィールドに対して生成されたサンプル データは可能性があります、同じスキーマを使用してそのインスタンス メッセージの検証に成功したことを制限の要件に準拠していませんどの it が生成されました。</span><span class="sxs-lookup"><span data-stu-id="56bb8-111">When you generate an instance message from a schema that contains one or more **Field Element** and **Field Attribute** nodes that have data types that have been derived using the restriction mechanism, such as when the **Pattern** property is used, the sample data generated for such fields may not conform to the requirements of the restriction, thereby preventing successful validation of that instance message using the same schema from which it was generated.</span></span>  
  
## <a name="an-instance-message-generated-for-a-schema-that-contains-an-infinite-loop-may-not-be-valid"></a><span data-ttu-id="56bb8-112">無限ループを含むスキーマに対して生成されたインスタンス メッセージは、有効でない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="56bb8-112">An instance message generated for a schema that contains an infinite loop may not be valid.</span></span>  
 <span data-ttu-id="56bb8-113">持つノードに循環参照が含まれている場合、スキーマが無限ループを含めることができます、 **Min Occurs**本質的には、終了条件を防止、1 つ以上のプロパティの値。</span><span class="sxs-lookup"><span data-stu-id="56bb8-113">Your schema can contain an infinite loop when it contains a circular reference to a node with a **Min Occurs** property value greater than or equal to one, essentially preventing a termination condition.</span></span> <span data-ttu-id="56bb8-114">インスタンス メッセージの生成は、生成操作は完了できますが、生成されたインスタンス メッセージが生成されたスキーマに準拠しませんように意図的に終了します。</span><span class="sxs-lookup"><span data-stu-id="56bb8-114">Instance message generation will artificially terminate so that the generation operation can complete, but the produced instance message will thereby not conform to the schema from which it was generated.</span></span> <span data-ttu-id="56bb8-115">このようなスキーマは、通常は疑いがあります。</span><span class="sxs-lookup"><span data-stu-id="56bb8-115">Such schemas are usually suspect.</span></span>  
  
## <a name="validation-of-xml-instance-fails-for-document-schema-which-has-the-target-namespacehttpwwww3orgxml1998namespace"></a><span data-ttu-id="56bb8-116">ターゲットの名前空間を持つドキュメント スキーマに対して XML インスタンスの検証に失敗した ="<http://www.w3.org/XML/1998/namespace>"</span><span class="sxs-lookup"><span data-stu-id="56bb8-116">Validation of XML instance fails for document schema which has the target namespace="<http://www.w3.org/XML/1998/namespace>"</span></span>  
 <span data-ttu-id="56bb8-117">ハイパーリンク"<http://www.w3.org/XML/1998/namespace>"は予約された名前空間のプレフィックスが"XML"にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="56bb8-117">The HYPERLINK "<http://www.w3.org/XML/1998/namespace>" is a reserved namespace whose prefix should be “XML”.</span></span> <span data-ttu-id="56bb8-118">"XML"プレフィックスを手動で編集することができます。</span><span class="sxs-lookup"><span data-stu-id="56bb8-118">You can manually edit the prefix to “XML”.</span></span>

## <a name="see-also"></a><span data-ttu-id="56bb8-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="56bb8-119">See also</span></span>
<span data-ttu-id="56bb8-120">これらのプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="56bb8-120">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
