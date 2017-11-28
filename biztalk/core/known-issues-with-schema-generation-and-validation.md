---
title: "スキーマの生成と検証に関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df1eaa6c-0d3e-4aec-9de0-8b9817b7bb97
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b830e955b54ae8e3ba7fc05f21f22acd97f290a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-schema-generation-and-validation"></a><span data-ttu-id="984a8-102">スキーマの生成と検証に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="984a8-102">Known Issues with Schema Generation and Validation</span></span>
<span data-ttu-id="984a8-103">このトピックでは、スキーマの生成と検証に関する既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="984a8-103">This topic provides information about known issues with schema generation and validation.</span></span>  
  
## <a name="an-instance-message-generated-for-a-positional-record-with-tags-could-be-incorrect"></a><span data-ttu-id="984a8-104">タグが位置指定レコードの生成されたインスタンス メッセージが正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="984a8-104">An instance message generated for a positional record with tags could be incorrect</span></span>  
 <span data-ttu-id="984a8-105">位置指定レコードのタグが、フィールド内に配置されている可能性があります。または、フィールドをまたいでいる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="984a8-105">For positional records, the tag can be within a field or can span between fields.</span></span> <span data-ttu-id="984a8-106">どちらの場合も、生成されたインスタンスは無効で、解析ステージ中に解析エンジンでエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="984a8-106">In either case, the instance generated will not be valid and will cause a failure in the Parsing Engine during the parsing stage.</span></span>  
  
 <span data-ttu-id="984a8-107">タグが子 (子レコードまたは子フィールド) の一部ではない場合、この問題は発生しません。</span><span class="sxs-lookup"><span data-stu-id="984a8-107">If the tag is not part of any children (child records or child fields), this problem will not occur.</span></span>  
  
 <span data-ttu-id="984a8-108">この問題を回避するには、タグの実際の値をスキーマの既定値として格納してください。</span><span class="sxs-lookup"><span data-stu-id="984a8-108">To work around this issue, include the actual value of the tag as the default in the schema.</span></span> <span data-ttu-id="984a8-109">BizTalk エディターのフラット ファイル拡張子で設定できます、**固定値**または**既定値**タグの値は、適切な位置指定フィールドのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="984a8-109">In the flat file extension of the BizTalk Editor, you can set the **Fixed Value** or **Default Value** property of the appropriate positional field with the value of the tag.</span></span>  
  
## <a name="an-instance-message-generated-for-a-field-with-some-restrictions-may-not-pass-validation"></a><span data-ttu-id="984a8-110">フィールドに対して制限付きで生成されたインスタンス メッセージが検証に合格しない</span><span class="sxs-lookup"><span data-stu-id="984a8-110">An instance message generated for a field with some restrictions may not pass validation</span></span>  
 <span data-ttu-id="984a8-111">1 つまたは複数を含むスキーマからインスタンス メッセージを生成すると**フィールド要素**と**フィールド属性**などの制約メカニズムを使用して作成されたデータ型を持つノードときに、**パターン**プロパティを使用して、このようなフィールドに対して生成されたサンプル データが同じスキーマを使用してインスタンス メッセージの検証が成功したように、制限の要件に準拠していませんそこが生成されました。</span><span class="sxs-lookup"><span data-stu-id="984a8-111">When you generate an instance message from a schema that contains one or more **Field Element** and **Field Attribute** nodes that have data types that have been derived using the restriction mechanism, such as when the **Pattern** property is used, the sample data generated for such fields may not conform to the requirements of the restriction, thereby preventing successful validation of that instance message using the same schema from which it was generated.</span></span>  
  
## <a name="an-instance-message-generated-for-a-schema-that-contains-an-infinite-loop-may-not-be-valid"></a><span data-ttu-id="984a8-112">無限ループを含むスキーマに対して生成されたインスタンス メッセージが無効になる</span><span class="sxs-lookup"><span data-stu-id="984a8-112">An instance message generated for a schema that contains an infinite loop may not be valid.</span></span>  
 <span data-ttu-id="984a8-113">持つノードに循環参照が含まれている場合に、スキーマが、無限ループを含めることができます、 **Min Occurs**本質的には、終了条件を防止、1 つ以上のプロパティの値。</span><span class="sxs-lookup"><span data-stu-id="984a8-113">Your schema can contain an infinite loop when it contains a circular reference to a node with a **Min Occurs** property value greater than or equal to one, essentially preventing a termination condition.</span></span> <span data-ttu-id="984a8-114">生成操作を終了するには、インスタンス メッセージの生成を強制終了させます。このため、生成されたインスタンス メッセージは、生成元のスキーマに準拠しません。</span><span class="sxs-lookup"><span data-stu-id="984a8-114">Instance message generation will artificially terminate so that the generation operation can complete, but the produced instance message will thereby not conform to the schema from which it was generated.</span></span> <span data-ttu-id="984a8-115">通常、このようなスキーマが問題となります。</span><span class="sxs-lookup"><span data-stu-id="984a8-115">Such schemas are usually suspect.</span></span>  
  
## <a name="validation-of-xml-instance-fails-for-document-schema-which-has-the-target-namespacehttpwwww3orgxml1998namespace"></a><span data-ttu-id="984a8-116">ドキュメント スキーマのターゲットの名前空間が "http://www.w3.org/XML/1998/namespace" である場合、XML インスタンスの検証が失敗する</span><span class="sxs-lookup"><span data-stu-id="984a8-116">Validation of XML instance fails for document schema which has the target namespace="http://www.w3.org/XML/1998/namespace"</span></span>  
 <span data-ttu-id="984a8-117">"ハイパーリンク "http://www.w3.org/XML/1998/namespace" http://www.w3.org/XML/1998/namespace" は、予約された名前空間のプレフィックスを持つが"XML"にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="984a8-117">The “ HYPERLINK "http://www.w3.org/XML/1998/namespace" http://www.w3.org/XML/1998/namespace” is a reserved namespace whose prefix should be “XML”.</span></span> <span data-ttu-id="984a8-118">このプレフィックスを手動で "XML" に変更できます。</span><span class="sxs-lookup"><span data-stu-id="984a8-118">You can manually edit the prefix to “XML”.</span></span>

## <a name="see-also"></a><span data-ttu-id="984a8-119">参照</span><span class="sxs-lookup"><span data-stu-id="984a8-119">See also</span></span>
<span data-ttu-id="984a8-120">これらのプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="984a8-120">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>