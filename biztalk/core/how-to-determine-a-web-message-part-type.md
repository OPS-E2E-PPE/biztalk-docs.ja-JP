---
title: Web メッセージ部分の型を確認する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web messages, message types
- Web services, Web messages
- Web messages, parts
ms.assetid: bdd1f604-ec35-41e3-b5a8-1e0ad0193eff
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb191f72612d364d69600f0d6e22505b6196b056
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338614"
---
# <a name="how-to-determine-a-web-message-part-type"></a><span data-ttu-id="46e6b-102">Web メッセージ部分の型を確認する方法</span><span class="sxs-lookup"><span data-stu-id="46e6b-102">How to Determine a Web Message Part Type</span></span>
<span data-ttu-id="46e6b-103">Web メッセージ部分の型が指定した Web メッセージの種類のプロパティ ウィンドウを使用して、プリミティブ .NET 型またはスキーマ型がある場合を判断できます。</span><span class="sxs-lookup"><span data-stu-id="46e6b-103">You can determine if a Web message part type is a primitive .NET type or a schema type by using the Properties window for a given Web message type.</span></span>  
  
### <a name="to-determine-a-web-message-part-type"></a><span data-ttu-id="46e6b-104">Web メッセージ部分の型を決定するには</span><span class="sxs-lookup"><span data-stu-id="46e6b-104">To determine a Web message part type</span></span>  
  
1.  <span data-ttu-id="46e6b-105">オーケストレーションを開いて、**ビュー**  メニューのをクリックして**その他の Windows**、順にクリックします**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="46e6b-105">With an orchestration open, on the **View** menu, click **Other Windows**,and then click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="46e6b-106">展開、**マルチパート メッセージの種類**ノード、し、Web メッセージの種類を展開します。</span><span class="sxs-lookup"><span data-stu-id="46e6b-106">Expand the **Multi-part Message Types** node, and then expand a Web message type.</span></span>  
  
3.  <span data-ttu-id="46e6b-107">メッセージ部分を選択します。</span><span class="sxs-lookup"><span data-stu-id="46e6b-107">Select a message part.</span></span>  
  
     <span data-ttu-id="46e6b-108">形式で始まる Web メッセージ部分の署名 **\<*プロジェクトの既定の名前空間*\>.\<*Web 参照名*\>します。参照。\<*スキーマ ルート*\>** はスキーマの一種です。</span><span class="sxs-lookup"><span data-stu-id="46e6b-108">A Web message part signature that begins as **\<*project default namespace*\>.\<*Web reference name*\>.Reference.\<*schema root*\>** is a schema type.</span></span> <span data-ttu-id="46e6b-109">**\<*スキーマ ルート*\>** 型の一部は、Web メッセージ部分を構築する Web 参照スキーマのルート要素。</span><span class="sxs-lookup"><span data-stu-id="46e6b-109">The **\<*schema root*\>** part of the type is the root element of the Web reference schema that constructs the Web message part.</span></span> <span data-ttu-id="46e6b-110">それ以外の場合、プリミティブ .NET 型は、メッセージ部分の署名など**System.String**または**System.Int32**します。</span><span class="sxs-lookup"><span data-stu-id="46e6b-110">Otherwise, the message part signature is a primitive .NET type such as **System.String** or **System.Int32**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46e6b-111">参照</span><span class="sxs-lookup"><span data-stu-id="46e6b-111">See Also</span></span>  
 [<span data-ttu-id="46e6b-112">Web メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="46e6b-112">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)