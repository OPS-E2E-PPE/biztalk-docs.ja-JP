---
title: フラット ファイル メッセージのヘッダー |Microsoft ドキュメント
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
ms.openlocfilehash: 271e9fe74d0a55f4b3ff5271861d24474fffaf37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246354"
---
# <a name="flat-file-message-headers"></a><span data-ttu-id="18a13-102">フラット ファイル メッセージのヘッダー</span><span class="sxs-lookup"><span data-stu-id="18a13-102">Flat File Message Headers</span></span>
<span data-ttu-id="18a13-103">構成したフラット ファイル スキーマによって制御されますが、フラット ファイル逆アセンブラーでは、省略可能なフラット ファイル インスタンス メッセージ ヘッダーの解析、**ヘッダー スキーマ**フラット ファイル逆アセンブラーのデザイン時プロパティまたは**XMLNORM です。HeaderSpecName**メッセージ コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="18a13-103">The parsing of the optional flat file instance message header by the flat file disassembler is controlled by the flat file schema that you have configured in the **Header schema** design-time property of the flat file disassembler or the **XMLNORM.HeaderSpecName** message context property.</span></span> <span data-ttu-id="18a13-104">いずれかの方法を使用してスキーマを指定しなかった場合、フラット ファイル逆アセンブラーは、フラット ファイル インスタンス メッセージにヘッダーが含まれないと想定します。</span><span class="sxs-lookup"><span data-stu-id="18a13-104">If you have not specified a schema using one of these two methods, the flat file disassembler assumes that the flat file instance message does not contain a header.</span></span>  

## <a name="outbound-messages"></a><span data-ttu-id="18a13-105">送信メッセージ</span><span class="sxs-lookup"><span data-stu-id="18a13-105">Outbound messages</span></span>  
 <span data-ttu-id="18a13-106">適切なスキーマを指定することで、ヘッダーを生成するために、フラット ファイル アセンブラーを構成する送信フラット ファイル インスタンス メッセージの場合、その**ヘッダー仕様名**デザイン時のプロパティまたは**XMLNORM です。HeaderSpecName**メッセージ コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="18a13-106">For outbound flat file instance messages, you can configure the flat file assembler to produce a header by specifying the appropriate schema in its **Header Specification Name** design-time property or the **XMLNORM.HeaderSpecName** message context property.</span></span> <span data-ttu-id="18a13-107">メッセージ コンテキスト プロパティの設定の詳細については、次を参照してください。**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="18a13-107">For more information about setting message context properties, see **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  

## <a name="inbound-messages"></a><span data-ttu-id="18a13-108">受信メッセージ</span><span class="sxs-lookup"><span data-stu-id="18a13-108">Inbound messages</span></span>  
 <span data-ttu-id="18a13-109">受信フラット ファイル インスタンス メッセージのヘッダーのデータは、2 つの異なる方法で保存して使用できます。</span><span class="sxs-lookup"><span data-stu-id="18a13-109">Data found in inbound flat file instance message headers can be preserved and utilized in two different ways.</span></span> <span data-ttu-id="18a13-110">最初の方法として、フラット ファイル インスタンス メッセージのヘッダーは、対応する送信フラット ファイル インスタンス メッセージのヘッダーとして後で復元するために、メッセージ コンテキストの本文にすべて保存できます。</span><span class="sxs-lookup"><span data-stu-id="18a13-110">First, flat file instance message headers can be saved in their entirety within the message context of the body for later restoration as the header of a corresponding outbound flat file instance message.</span></span> <span data-ttu-id="18a13-111">使用することができます、 **Preserve ヘッダー**ヘッダーを保持することを指定する受信パイプラインのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="18a13-111">You can use the **Preserve header** property of the receive pipeline to specify that the header should be preserved.</span></span> <span data-ttu-id="18a13-112">ヘッダーがフラット ファイル アセンブラーで指定されている場合、保存されているヘッダーが送信メッセージで使用されます。</span><span class="sxs-lookup"><span data-stu-id="18a13-112">And if a header is specified in the flat file assembler, the preserved header will be used on the outbound message.</span></span>  
  
 <span data-ttu-id="18a13-113">2 つ目の方法として、対応するスキーマの 1 つ以上のフィールドのプロパティの昇格を指定して、フラット ファイル インスタンス メッセージ ヘッダーのデータの各項目をフラット ファイル メッセージ本文に関連付けられているメッセージ コンテキストにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="18a13-113">Second, individual items of data from a flat file instance message header can be copied to the message context associated with the flat file message body by specifying property promotion for one or more of the fields in the corresponding schema.</span></span> <span data-ttu-id="18a13-114">プロパティの昇格の詳細については、次を参照してください。[プロパティの昇格](../core/promoting-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="18a13-114">For more information about promoting properties, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18a13-115">参照</span><span class="sxs-lookup"><span data-stu-id="18a13-115">See Also</span></span>  
 <span data-ttu-id="18a13-116">[フラット ファイル メッセージの本文](../core/flat-file-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="18a13-116">[Flat File Message Bodies](../core/flat-file-message-bodies.md) </span></span>  
 <span data-ttu-id="18a13-117">[フラット ファイル メッセージのトレーラー](../core/flat-file-message-trailers.md) </span><span class="sxs-lookup"><span data-stu-id="18a13-117">[Flat File Message Trailers](../core/flat-file-message-trailers.md) </span></span>  
 <span data-ttu-id="18a13-118">[フラット ファイル メッセージの構造](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="18a13-118">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 [<span data-ttu-id="18a13-119">フラット ファイル メッセージのスキーマを作成する方法</span><span class="sxs-lookup"><span data-stu-id="18a13-119">How to Create Schemas for Flat File Messages</span></span>](../core/how-to-create-schemas-for-flat-file-messages.md)