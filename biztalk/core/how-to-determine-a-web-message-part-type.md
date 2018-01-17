---
title: "Web メッセージ部分の型を確認する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web messages, message types
- Web services, Web messages
- Web messages, parts
ms.assetid: bdd1f604-ec35-41e3-b5a8-1e0ad0193eff
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6102e39eb38e919c68405ae18bebde0b46c0b053
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-determine-a-web-message-part-type"></a><span data-ttu-id="2fbc1-102">Web メッセージ部分の型を判別する方法</span><span class="sxs-lookup"><span data-stu-id="2fbc1-102">How to Determine a Web Message Part Type</span></span>
<span data-ttu-id="2fbc1-103">特定の Web メッセージの種類の [プロパティ] ウィンドウを使用して、Web メッセージ部分の型がプリミティブ .NET 型かスキーマ型かを判別できます。</span><span class="sxs-lookup"><span data-stu-id="2fbc1-103">You can determine if a Web message part type is a primitive .NET type or a schema type by using the Properties window for a given Web message type.</span></span>  
  
### <a name="to-determine-a-web-message-part-type"></a><span data-ttu-id="2fbc1-104">Web メッセージ部分の型を判別するには</span><span class="sxs-lookup"><span data-stu-id="2fbc1-104">To determine a Web message part type</span></span>  
  
1.  <span data-ttu-id="2fbc1-105">オーケストレーションを開いている状態で、 **ビュー**  メニューのをクリックして **その他のウィンドウ**,、クリックして **オーケストレーションの種類**します。</span><span class="sxs-lookup"><span data-stu-id="2fbc1-105">With an orchestration open, on the **View** menu, click **Other Windows**,and then click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="2fbc1-106">展開、 **マルチパート メッセージの種類** ノード、Web メッセージの種類を順に展開します。</span><span class="sxs-lookup"><span data-stu-id="2fbc1-106">Expand the **Multi-part Message Types** node, and then expand a Web message type.</span></span>  
  
3.  <span data-ttu-id="2fbc1-107">メッセージ部分を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fbc1-107">Select a message part.</span></span>  
  
     <span data-ttu-id="2fbc1-108">形式で始まる Web メッセージ部分の署名 **\<*プロジェクトの既定の名前空間*\>.\<*Web 参照名*\>です。参照。\<*スキーマ ルート*\>** スキーマ型です。</span><span class="sxs-lookup"><span data-stu-id="2fbc1-108">A Web message part signature that begins as **\<*project default namespace*\>.\<*Web reference name*\>.Reference.\<*schema root*\>** is a schema type.</span></span> <span data-ttu-id="2fbc1-109"> **\<*スキーマ ルート*\>** 型の一部は、Web メッセージ部分を構築する Web 参照スキーマのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="2fbc1-109">The **\<*schema root*\>** part of the type is the root element of the Web reference schema that constructs the Web message part.</span></span> <span data-ttu-id="2fbc1-110">それ以外の場合、メッセージ部分の署名はプリミティブ .NET 型などが**System.String**または**System.Int32**です。</span><span class="sxs-lookup"><span data-stu-id="2fbc1-110">Otherwise, the message part signature is a primitive .NET type such as **System.String** or **System.Int32**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fbc1-111">参照</span><span class="sxs-lookup"><span data-stu-id="2fbc1-111">See Also</span></span>  
 [<span data-ttu-id="2fbc1-112">Web メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="2fbc1-112">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)