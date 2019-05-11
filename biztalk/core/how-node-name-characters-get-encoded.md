---
title: ノード名における文字エン コードの方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6462856b-7a52-40c9-9aff-c0579130eec9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 387f80f54952b1f2bdae877c806b0a130c5bf1b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387454"
---
# <a name="how-node-name-characters-get-encoded"></a><span data-ttu-id="cf961-102">ノード名の文字エンコードの方法</span><span class="sxs-lookup"><span data-stu-id="cf961-102">How Node Name Characters Get Encoded</span></span>
<span data-ttu-id="cf961-103">BizTalk エディターが使用できない文字またはエンコードされた文字を続行するかを確認するように求められますノード名で許可されていない文字を使用する場合 (**OK**または**キャンセル**)。</span><span class="sxs-lookup"><span data-stu-id="cf961-103">If you use a character that is not allowed in a node name, BizTalk Editor prompts you, asking if you want to proceed with the disallowed character or characters encoded (**OK** or **Cancel**).</span></span> <span data-ttu-id="cf961-104">続行した場合 ([OK] をクリック)、禁止文字がそれぞれ次のようにエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="cf961-104">If you proceed, each disallowed character is encoded as follows:</span></span>  
  
- <span data-ttu-id="cf961-105">許可されない文字としてエンコードされます"*xDDDD\\*"ここ"DDDD"には、文字の 4 桁の 16 進数 Unicode 表現。</span><span class="sxs-lookup"><span data-stu-id="cf961-105">Disallowed characters are encoded as "*xDDDD\\*" where "DDDD" is the 4-digit hexadecimal Unicode representation of the character.</span></span> <span data-ttu-id="cf961-106">たとえば、スペース (0x0020) としてエンコード"*x0020\\*"。</span><span class="sxs-lookup"><span data-stu-id="cf961-106">For example, the space character (0x0020) is encoded as "*x0020\\*".</span></span>  
  
- <span data-ttu-id="cf961-107">複数の隣接する禁止文字がエンコードされる場合、文字間にアンダースコア文字が 1 つ挿入されます。</span><span class="sxs-lookup"><span data-stu-id="cf961-107">If two or more adjacent disallowed characters are encoded, only a single underscore character is used between them.</span></span> <span data-ttu-id="cf961-108">たとえば、3 つのスペースとしてエンコード"*x0020_x0020_x0020\\*「なく」*x0020\__x0020\__x0020\\*"。</span><span class="sxs-lookup"><span data-stu-id="cf961-108">For example, three spaces are encoded as "*x0020_x0020_x0020\\*" rather than "*x0020\__x0020\__x0020\\*".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf961-109">設定してノード名のエンコードのプロンプトを無効にした、**エンコード警告ダイアログを表示する**プロパティを**False**の BizTalk エディター フォルダーで、**オプション**ダイアログ ボックスで、使用できる、**ツール**メニュー、またはを選択して、 **、今後このダイアログ ボックスを表示しない**ノード名のエンコード ダイアログ ボックスのチェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="cf961-109">You can disable prompting for node name encoding by setting the **Show Encode Warning Dialog** property to **False** in the BizTalk Editor folder of the **Options** dialog box, available on the **Tools** menu, or by selecting the **Do not show this dialog in the future** check box in the node name encoding dialog box.</span></span> <span data-ttu-id="cf961-110">このダイアログ ボックスでオプションの詳細については、次を参照してください。[スキーマ ツリー ビューの管理](../core/how-to-manage-the-schema-tree-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf961-110">For more information about the options in this dialog box, see [Managing the Schema Tree View](../core/how-to-manage-the-schema-tree-view.md).</span></span>  
  
 <span data-ttu-id="cf961-111">BizTalk エディターのスキーマ ツリー ビューには、入力された文字を使ってノード名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf961-111">The schema tree view in BizTalk Editor displays node names by using the characters you type.</span></span> <span data-ttu-id="cf961-112">また、BizTalk マッパーでも、エンコード後の文字ではなく、入力された文字がそのまま表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf961-112">BizTalk Mapper also displays the characters you have typed rather than the encoded version.</span></span> <span data-ttu-id="cf961-113">BizTalk エディターの XSD ビュー、および XSD ファイル自体には、エンコードされたノード名が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf961-113">In the XSD view of BizTalk Editor, and in the XSD file itself, the encoded node name is used.</span></span> <span data-ttu-id="cf961-114">たとえば、ノード名として「Purchase Order」を入力した場合、BizTalk エディターおよび BizTalk マッパーのスキーマ ツリーには "Purchase Order" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf961-114">For example, if you name a node Purchase Order, it will be displayed as Purchase Order in the schema trees in both BizTalk Editor and BizTalk Mapper.</span></span> <span data-ttu-id="cf961-115">BizTalk エディターの XSD ビューでは、対応する要素ノードが (最初に挿入されたときに) 次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf961-115">In the XSD view of BizTalk Editor, the corresponding element node, when first inserted, will be as follows.</span></span>  
  
```  
<element name="Purchase_x0020_Order" type="xs:string />  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf961-116">参照</span><span class="sxs-lookup"><span data-stu-id="cf961-116">See Also</span></span>  
 <span data-ttu-id="cf961-117">[ノード名プロパティ](../core/node-name-property.md) </span><span class="sxs-lookup"><span data-stu-id="cf961-117">[Node Name Property](../core/node-name-property.md) </span></span>  
 [<span data-ttu-id="cf961-118">ノード名における文字エンコード</span><span class="sxs-lookup"><span data-stu-id="cf961-118">Which Node Name Characters Get Encoded</span></span>](../core/which-node-name-characters-get-encoded.md)