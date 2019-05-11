---
title: フラット ファイル メッセージのトレーラー |Microsoft Docs
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
ms.openlocfilehash: d0f609ee7e4770fdc6f34bcd2ff8c11e5f10b6e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345366"
---
# <a name="flat-file-message-trailers"></a><span data-ttu-id="65f55-102">フラット ファイル メッセージのトレーラー</span><span class="sxs-lookup"><span data-stu-id="65f55-102">Flat File Message Trailers</span></span>
<span data-ttu-id="65f55-103">フラット ファイル インスタンス メッセージのヘッダーとで構成したフラット ファイル スキーマで、フラット ファイル逆アセンブラーでは、省略可能なフラット ファイル インスタンス メッセージ トレーラーの解析が制御される、**トレーラー スキーマ**デザイン時フラット ファイル逆アセンブラーのプロパティまたは**XMLNORM します。TrailerSpecName**メッセージ コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="65f55-103">As with flat file instance message headers, the parsing of the optional flat file instance message trailer by the flat file disassembler is controlled by the flat file schema that you have configured in the **Trailer schema** design-time property of the flat file disassembler or the **XMLNORM.TrailerSpecName** message context property.</span></span> <span data-ttu-id="65f55-104">これら 2 つのメソッドのいずれかを使用してスキーマが指定されていない場合、フラット ファイル逆アセンブラーは、フラット ファイル インスタンス メッセージにトレーラーが含まれていないと想定されます。</span><span class="sxs-lookup"><span data-stu-id="65f55-104">If you have not specified a schema using one of these two methods, the flat file disassembler will assume that the flat file instance message does not contain a trailer.</span></span>  
  
 <span data-ttu-id="65f55-105">フラット ファイル インスタンスに関連付けられたメッセージ コンテキストにデータの個々 の項目をコピーする、プロパティの昇格が使用することもできませんとは異なり、フラット ファイル インスタンス メッセージ ヘッダーのフラット ファイル インスタンス メッセージのトレーラーも保存でき、1 つの単位として復元メッセージの本文。</span><span class="sxs-lookup"><span data-stu-id="65f55-105">Unlike with flat file instance message headers, flat file instance message trailers can neither be saved and restored as a single unit, nor can they use property promotion to copy individual items of data to the message context associated with the flat file instance message body.</span></span> <span data-ttu-id="65f55-106">適切なスキーマを指定することでトレーラーを送信フラット ファイル インスタンス メッセージに追加するただし、**トレーラー スキーマ**フラット ファイル アセンブラーのデザイン時プロパティまたは**XMLNORM します。TrailerSpecName**メッセージ コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="65f55-106">However, a trailer can be added to an outbound flat file instance message by specifying the appropriate schema in the **Trailer schema** design-time property of the flat file assembler or the **XMLNORM.TrailerSpecName** message context property.</span></span> <span data-ttu-id="65f55-107">プロパティを降格、メッセージ コンテキストからフラット ファイル インスタンス メッセージの本文のか、対応するスキーマの既定値または固定値を指定することによって、トレーラーの可変部分を構成するデータを指定できます。</span><span class="sxs-lookup"><span data-stu-id="65f55-107">The data that constitutes the variable portion of the trailer can be specified using property demotion from the message context of the flat file instance message body, or by specifying default or fixed values in the corresponding schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65f55-108">参照</span><span class="sxs-lookup"><span data-stu-id="65f55-108">See Also</span></span>  
 <span data-ttu-id="65f55-109">[フラット ファイル メッセージのヘッダー](../core/flat-file-message-headers.md) </span><span class="sxs-lookup"><span data-stu-id="65f55-109">[Flat File Message Headers](../core/flat-file-message-headers.md) </span></span>  
 <span data-ttu-id="65f55-110">[フラット ファイル メッセージの本文](../core/flat-file-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="65f55-110">[Flat File Message Bodies](../core/flat-file-message-bodies.md) </span></span>  
 <span data-ttu-id="65f55-111">[フラット ファイル メッセージの構造](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="65f55-111">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 [<span data-ttu-id="65f55-112">フラット ファイル メッセージのスキーマを作成する方法</span><span class="sxs-lookup"><span data-stu-id="65f55-112">How to Create Schemas for Flat File Messages</span></span>](../core/how-to-create-schemas-for-flat-file-messages.md)