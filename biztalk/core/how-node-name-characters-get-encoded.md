---
title: "ノード名における文字エン コードのどの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6462856b-7a52-40c9-9aff-c0579130eec9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d2c9410e56b2b50a32ec73ce5f49ae59909f59a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-node-name-characters-get-encoded"></a><span data-ttu-id="726c3-102">ノード名の文字エンコードの方法</span><span class="sxs-lookup"><span data-stu-id="726c3-102">How Node Name Characters Get Encoded</span></span>
<span data-ttu-id="726c3-103">ノード名で許可されていない文字を使用する場合は、BizTalk エディターが表示されたら、使用できない文字またはエンコード文字を続行するかどうかたずねる (**OK**または**キャンセル**)。</span><span class="sxs-lookup"><span data-stu-id="726c3-103">If you use a character that is not allowed in a node name, BizTalk Editor prompts you, asking if you want to proceed with the disallowed character or characters encoded (**OK** or **Cancel**).</span></span> <span data-ttu-id="726c3-104">続行した場合 ([OK] をクリック)、禁止文字がそれぞれ次のようにエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="726c3-104">If you proceed, each disallowed character is encoded as follows:</span></span>  
  
-   <span data-ttu-id="726c3-105">として使用できない文字がエンコードされます"_xDDDD\_"、"DDDD"は、文字の 4 桁の 16 進 Unicode 表現します。</span><span class="sxs-lookup"><span data-stu-id="726c3-105">Disallowed characters are encoded as "_xDDDD\_" where "DDDD" is the 4-digit hexadecimal Unicode representation of the character.</span></span> <span data-ttu-id="726c3-106">たとえば、スペース (0x0020) としてエンコード"_x0020\_"です。</span><span class="sxs-lookup"><span data-stu-id="726c3-106">For example, the space character (0x0020) is encoded as "_x0020\_".</span></span>  
  
-   <span data-ttu-id="726c3-107">複数の隣接する禁止文字がエンコードされる場合、文字間にアンダースコア文字が 1 つ挿入されます。</span><span class="sxs-lookup"><span data-stu-id="726c3-107">If two or more adjacent disallowed characters are encoded, only a single underscore character is used between them.</span></span> <span data-ttu-id="726c3-108">たとえば、3 つのスペースとしてエンコード"_x0020_x0020_x0020\_"ではなく"_x0020\__x0020\__x0020\_"です。</span><span class="sxs-lookup"><span data-stu-id="726c3-108">For example, three spaces are encoded as "_x0020_x0020_x0020\_" rather than "_x0020\__x0020\__x0020\_".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="726c3-109">ノード名のエンコードを設定して要求するプロンプトを無効にする、**エンコード警告ダイアログの表示**プロパティを**False**の BizTalk エディター フォルダーで、**オプション** ダイアログ ボックス使用できる、**ツール** メニューの または を選択して、**今後このダイアログ ボックスを表示しない**ノード名のエンコード ダイアログ ボックスのチェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="726c3-109">You can disable prompting for node name encoding by setting the **Show Encode Warning Dialog** property to **False** in the BizTalk Editor folder of the **Options** dialog box, available on the **Tools** menu, or by selecting the **Do not show this dialog in the future** check box in the node name encoding dialog box.</span></span> <span data-ttu-id="726c3-110">このダイアログ ボックスでオプションの詳細については、次を参照してください。[スキーマ ツリー ビューの管理](../core/how-to-manage-the-schema-tree-view.md)です。</span><span class="sxs-lookup"><span data-stu-id="726c3-110">For more information about the options in this dialog box, see [Managing the Schema Tree View](../core/how-to-manage-the-schema-tree-view.md).</span></span>  
  
 <span data-ttu-id="726c3-111">BizTalk エディターのスキーマ ツリー ビューには、入力された文字を使ってノード名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="726c3-111">The schema tree view in BizTalk Editor displays node names by using the characters you type.</span></span> <span data-ttu-id="726c3-112">また、BizTalk マッパーでも、エンコード後の文字ではなく、入力された文字がそのまま表示されます。</span><span class="sxs-lookup"><span data-stu-id="726c3-112">BizTalk Mapper also displays the characters you have typed rather than the encoded version.</span></span> <span data-ttu-id="726c3-113">BizTalk エディターの XSD ビュー、および XSD ファイル自体には、エンコードされたノード名が使用されます。</span><span class="sxs-lookup"><span data-stu-id="726c3-113">In the XSD view of BizTalk Editor, and in the XSD file itself, the encoded node name is used.</span></span> <span data-ttu-id="726c3-114">たとえば、ノード名として「Purchase Order」を入力した場合、BizTalk エディターおよび BizTalk マッパーのスキーマ ツリーには "Purchase Order" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="726c3-114">For example, if you name a node Purchase Order, it will be displayed as Purchase Order in the schema trees in both BizTalk Editor and BizTalk Mapper.</span></span> <span data-ttu-id="726c3-115">BizTalk エディターの XSD ビューでは、対応する要素ノードが (最初に挿入されたときに) 次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="726c3-115">In the XSD view of BizTalk Editor, the corresponding element node, when first inserted, will be as follows.</span></span>  
  
```  
<element name="Purchase_x0020_Order" type="xs:string />  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="726c3-116">参照</span><span class="sxs-lookup"><span data-stu-id="726c3-116">See Also</span></span>  
 <span data-ttu-id="726c3-117">[ノード名プロパティ](../core/node-name-property.md) </span><span class="sxs-lookup"><span data-stu-id="726c3-117">[Node Name Property](../core/node-name-property.md) </span></span>  
 [<span data-ttu-id="726c3-118">ノード名における文字エン コードします。</span><span class="sxs-lookup"><span data-stu-id="726c3-118">Which Node Name Characters Get Encoded</span></span>](../core/which-node-name-characters-get-encoded.md)