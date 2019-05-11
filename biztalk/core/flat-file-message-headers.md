---
title: フラット ファイル メッセージのヘッダー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1981daaf-149a-426d-9a2f-5fcf64bce185
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e4914bb5efa806cc16072b6beb96c4d53f6e7ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387917"
---
# <a name="flat-file-message-headers"></a><span data-ttu-id="d259c-102">フラット ファイル メッセージのヘッダー</span><span class="sxs-lookup"><span data-stu-id="d259c-102">Flat File Message Headers</span></span>
<span data-ttu-id="d259c-103">構成したフラット ファイル スキーマによって制御されますが、フラット ファイル逆アセンブラーでは、省略可能なフラット ファイル インスタンス メッセージ ヘッダーの解析、**ヘッダー スキーマ**フラット ファイル逆アセンブラーのデザイン時プロパティまたは**XMLNORM します。HeaderSpecName**メッセージ コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d259c-103">The parsing of the optional flat file instance message header by the flat file disassembler is controlled by the flat file schema that you have configured in the **Header schema** design-time property of the flat file disassembler or the **XMLNORM.HeaderSpecName** message context property.</span></span> <span data-ttu-id="d259c-104">これら 2 つのメソッドのいずれかを使用してスキーマが指定されていない場合、フラット ファイル逆アセンブラー、フラット ファイル インスタンス メッセージにヘッダーが含まれていないこと前提としています。</span><span class="sxs-lookup"><span data-stu-id="d259c-104">If you have not specified a schema using one of these two methods, the flat file disassembler assumes that the flat file instance message does not contain a header.</span></span>  

## <a name="outbound-messages"></a><span data-ttu-id="d259c-105">送信メッセージ</span><span class="sxs-lookup"><span data-stu-id="d259c-105">Outbound messages</span></span>  
 <span data-ttu-id="d259c-106">内の適切なスキーマを指定することで、ヘッダーを生成するために、フラット ファイル アセンブラーを構成する送信フラット ファイル インスタンス メッセージの場合、その**ヘッダー仕様名**デザイン時プロパティまたは**XMLNORM します。HeaderSpecName**メッセージ コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d259c-106">For outbound flat file instance messages, you can configure the flat file assembler to produce a header by specifying the appropriate schema in its **Header Specification Name** design-time property or the **XMLNORM.HeaderSpecName** message context property.</span></span> <span data-ttu-id="d259c-107">メッセージ コンテキスト プロパティを設定する方法についての詳細については、次を参照してください。**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d259c-107">For more information about setting message context properties, see **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  

## <a name="inbound-messages"></a><span data-ttu-id="d259c-108">受信メッセージ</span><span class="sxs-lookup"><span data-stu-id="d259c-108">Inbound messages</span></span>  
 <span data-ttu-id="d259c-109">受信フラット ファイル インスタンス メッセージのヘッダー内のデータを空白を保持し、2 つの方法で使用されることができます。</span><span class="sxs-lookup"><span data-stu-id="d259c-109">Data found in inbound flat file instance message headers can be preserved and utilized in two different ways.</span></span> <span data-ttu-id="d259c-110">最初に、フラット ファイル インスタンス メッセージのヘッダーは、対応する送信フラット ファイル インスタンス メッセージのヘッダーとして後で復元の本文のメッセージ コンテキスト内で完全に保存できます。</span><span class="sxs-lookup"><span data-stu-id="d259c-110">First, flat file instance message headers can be saved in their entirety within the message context of the body for later restoration as the header of a corresponding outbound flat file instance message.</span></span> <span data-ttu-id="d259c-111">使用することができます、 **Preserve ヘッダー**ヘッダーを保持することを指定する受信パイプラインのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="d259c-111">You can use the **Preserve header** property of the receive pipeline to specify that the header should be preserved.</span></span> <span data-ttu-id="d259c-112">保存したヘッダーが送信メッセージで使用される場合は、ヘッダーがフラット ファイル アセンブラーで指定します。</span><span class="sxs-lookup"><span data-stu-id="d259c-112">And if a header is specified in the flat file assembler, the preserved header will be used on the outbound message.</span></span>  
  
 <span data-ttu-id="d259c-113">フラット ファイル インスタンス メッセージのヘッダーからのデータの第 2 に、個々 のアイテムは、対応するスキーマのフィールドの 1 つ以上のプロパティの昇格を指定することで、フラット ファイル メッセージの本文に関連付けられているメッセージ コンテキストにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="d259c-113">Second, individual items of data from a flat file instance message header can be copied to the message context associated with the flat file message body by specifying property promotion for one or more of the fields in the corresponding schema.</span></span> <span data-ttu-id="d259c-114">プロパティの昇格の詳細については、次を参照してください。[プロパティの昇格](../core/promoting-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="d259c-114">For more information about promoting properties, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d259c-115">参照</span><span class="sxs-lookup"><span data-stu-id="d259c-115">See Also</span></span>  
 <span data-ttu-id="d259c-116">[フラット ファイル メッセージの本文](../core/flat-file-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="d259c-116">[Flat File Message Bodies](../core/flat-file-message-bodies.md) </span></span>  
 <span data-ttu-id="d259c-117">[フラット ファイル メッセージのトレーラー](../core/flat-file-message-trailers.md) </span><span class="sxs-lookup"><span data-stu-id="d259c-117">[Flat File Message Trailers](../core/flat-file-message-trailers.md) </span></span>  
 <span data-ttu-id="d259c-118">[フラット ファイル メッセージの構造](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="d259c-118">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 [<span data-ttu-id="d259c-119">フラット ファイル メッセージのスキーマを作成する方法</span><span class="sxs-lookup"><span data-stu-id="d259c-119">How to Create Schemas for Flat File Messages</span></span>](../core/how-to-create-schemas-for-flat-file-messages.md)