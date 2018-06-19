---
title: フラット ファイル メッセージのトレーラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfe115a5-4fdc-4779-94f3-437b5a06fbd4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cbeaef3f23de3cb89d873413964cd331ec23f43
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246290"
---
# <a name="flat-file-message-trailers"></a><span data-ttu-id="ec6bb-102">フラット ファイル メッセージのトレーラー</span><span class="sxs-lookup"><span data-stu-id="ec6bb-102">Flat File Message Trailers</span></span>
<span data-ttu-id="ec6bb-103">フラット ファイル インスタンス メッセージのヘッダーのフラット ファイル逆アセンブラーでは、省略可能なフラット ファイル インスタンス メッセージ トレーラーの解析で構成したフラット ファイル スキーマによって制御されるよう、**トレーラー スキーマ**デザイン時フラット ファイル逆アセンブラーのプロパティまたは**XMLNORM です。TrailerSpecName**メッセージ コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="ec6bb-103">As with flat file instance message headers, the parsing of the optional flat file instance message trailer by the flat file disassembler is controlled by the flat file schema that you have configured in the **Trailer schema** design-time property of the flat file disassembler or the **XMLNORM.TrailerSpecName** message context property.</span></span> <span data-ttu-id="ec6bb-104">いずれかの方法を使用してスキーマを指定しなかった場合、フラット ファイル逆アセンブラーは、フラット ファイル インスタンス メッセージにトレーラーが含まれないと見なします。</span><span class="sxs-lookup"><span data-stu-id="ec6bb-104">If you have not specified a schema using one of these two methods, the flat file disassembler will assume that the flat file instance message does not contain a trailer.</span></span>  
  
 <span data-ttu-id="ec6bb-105">フラット ファイル インスタンス メッセージのヘッダーとは異なり、フラット ファイル インスタンス メッセージのトレーラーは、1 つの単位として保存および復元できません。また、プロパティの昇格を使用して、フラット ファイル インスタンス メッセージの本文に関連付けられているメッセージ コンテキストにデータの各項目をコピーすることもできません。</span><span class="sxs-lookup"><span data-stu-id="ec6bb-105">Unlike with flat file instance message headers, flat file instance message trailers can neither be saved and restored as a single unit, nor can they use property promotion to copy individual items of data to the message context associated with the flat file instance message body.</span></span> <span data-ttu-id="ec6bb-106">ただし、トレーラーに追加できます送信フラット ファイル インスタンス メッセージ内の適切なスキーマを指定することによって、**トレーラー スキーマ**、フラット ファイル アセンブラーのデザイン時プロパティまたは**XMLNORM です。TrailerSpecName**メッセージ コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="ec6bb-106">However, a trailer can be added to an outbound flat file instance message by specifying the appropriate schema in the **Trailer schema** design-time property of the flat file assembler or the **XMLNORM.TrailerSpecName** message context property.</span></span> <span data-ttu-id="ec6bb-107">トレーラーの可変部分を構成するデータは、フラット ファイル インスタンス メッセージの本文のメッセージ コンテキストからプロパティを降格することにより指定できます。または、対応するスキーマの既定値 (あるいは固定値) でも指定できます。</span><span class="sxs-lookup"><span data-stu-id="ec6bb-107">The data that constitutes the variable portion of the trailer can be specified using property demotion from the message context of the flat file instance message body, or by specifying default or fixed values in the corresponding schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec6bb-108">参照</span><span class="sxs-lookup"><span data-stu-id="ec6bb-108">See Also</span></span>  
 <span data-ttu-id="ec6bb-109">[フラット ファイル メッセージのヘッダー](../core/flat-file-message-headers.md) </span><span class="sxs-lookup"><span data-stu-id="ec6bb-109">[Flat File Message Headers](../core/flat-file-message-headers.md) </span></span>  
 <span data-ttu-id="ec6bb-110">[フラット ファイル メッセージの本文](../core/flat-file-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="ec6bb-110">[Flat File Message Bodies](../core/flat-file-message-bodies.md) </span></span>  
 <span data-ttu-id="ec6bb-111">[フラット ファイル メッセージの構造](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="ec6bb-111">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 [<span data-ttu-id="ec6bb-112">フラット ファイル メッセージのスキーマを作成する方法</span><span class="sxs-lookup"><span data-stu-id="ec6bb-112">How to Create Schemas for Flat File Messages</span></span>](../core/how-to-create-schemas-for-flat-file-messages.md)