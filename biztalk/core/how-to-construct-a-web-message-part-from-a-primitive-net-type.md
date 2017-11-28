---
title: "プリミティブ .NET 型から Web メッセージ部分を構築する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, Web messages
- Web messages, Message Assignment shape [Orchestration Designer]
- Web messages, creating
- Message Assignment shape [Orchestration Designer], Web messages
- Web messages, parts
- Web messages, .NET types
ms.assetid: 1fe52412-d2bc-484c-8925-c7ff3ca7704b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991970d5b0d40da1ec00b54919d2742cfd48353c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-construct-a-web-message-part-from-a-primitive-net-type"></a><span data-ttu-id="a04be-102">プリミティブ .NET 型から Web メッセージ部分を構築する方法</span><span class="sxs-lookup"><span data-stu-id="a04be-102">How to Construct a Web Message Part from a Primitive .NET Type</span></span>
<span data-ttu-id="a04be-103">使用して、プリミティブ .NET 型から Web メッセージ部分を作成する、**メッセージの割り当て**図形です。</span><span class="sxs-lookup"><span data-stu-id="a04be-103">You create a Web message part from a primitive .NET type by using a **Message Assignment** shape.</span></span> <span data-ttu-id="a04be-104">Web メッセージ部分を設定する .NET ヘルパー クラスを使用して、プリミティブ .NET 型からその部分を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a04be-104">Alternatively, you can create a Web message part from a primitive .NET type by using a .NET helper class to set the parts.</span></span> <span data-ttu-id="a04be-105">.NET クラスを使用してメッセージの種類を作成する方法の詳細については、次を参照してください。[ユーザー コードでメッセージを構築する](../core/constructing-messages-in-user-code.md)です。</span><span class="sxs-lookup"><span data-stu-id="a04be-105">For more information on creating message types by using a .NET class, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
### <a name="to-construct-a-web-message-part-from-a-primitive-net-type"></a><span data-ttu-id="a04be-106">プリミティブ .NET 型から Web メッセージ部分を構築するには</span><span class="sxs-lookup"><span data-stu-id="a04be-106">To construct a Web message part from a primitive .NET type</span></span>  
  
1.  <span data-ttu-id="a04be-107">オーケストレーションを開き、開き、**ツールボックス** をクリックし、 **BizTalk オーケストレーション**タブです。</span><span class="sxs-lookup"><span data-stu-id="a04be-107">With an orchestration open, open the **Toolbox** and click the **BizTalk Orchestrations** tab.</span></span>  
  
2.  <span data-ttu-id="a04be-108">ドラッグ、**メッセージの構築**オーケストレーションへの図形です。</span><span class="sxs-lookup"><span data-stu-id="a04be-108">Drag a **Construct Message** shape to the orchestration.</span></span>  
  
3.  <span data-ttu-id="a04be-109">編集、**メッセージ構築**プロパティを Web メッセージの種類用に作成したメッセージ インスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a04be-109">Edit the **Message Constructed** property to include the message instance that you created for the Web message type.</span></span>  
  
4.  <span data-ttu-id="a04be-110">ドラッグ、**メッセージの割り当て**図形の上に、**メッセージの構築**図形です。</span><span class="sxs-lookup"><span data-stu-id="a04be-110">Drag a **Message Assignment** shape onto the **Construct Message** shape.</span></span>  
  
5.  <span data-ttu-id="a04be-111">ダブルクリックして、**メッセージの割り当て**図形を BizTalk 式エディタを開きます。</span><span class="sxs-lookup"><span data-stu-id="a04be-111">Double-click the **Message Assignment** shape to open the BizTalk Expression Editor.</span></span>  
  
6.  <span data-ttu-id="a04be-112">[BizTalk 式エディタ] ボックスで、Web メッセージの種類の部分を必要な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="a04be-112">Set the parts of the Web message type to their required values in the BizTalk Expression Editor box.</span></span>  
  
     <span data-ttu-id="a04be-113">たとえば、次のコードは式を文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="a04be-113">For example, the following code sets the expression to a string:</span></span>  
  
    ```  
    ItemAvailRequestInstance.Item_ID = "This is Item_ID.";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a04be-114">参照</span><span class="sxs-lookup"><span data-stu-id="a04be-114">See Also</span></span>  
 [<span data-ttu-id="a04be-115">Web メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="a04be-115">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)