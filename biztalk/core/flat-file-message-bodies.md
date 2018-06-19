---
title: フラット ファイル メッセージの本文 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 097e49a1-75d2-44a4-9372-d78de7b7597c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de8748d9a36c817f7db8fed96a59c8d2bd7dda2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246786"
---
# <a name="flat-file-message-bodies"></a><span data-ttu-id="21cf3-102">フラット ファイル メッセージの本文</span><span class="sxs-lookup"><span data-stu-id="21cf3-102">Flat File Message Bodies</span></span>
<span data-ttu-id="21cf3-103">フラット ファイル インスタンス メッセージの本文で必要となる部分は、フラット ファイル逆アセンブラーによって 1 つ以上の XML インスタンス メッセージに変換されます。</span><span class="sxs-lookup"><span data-stu-id="21cf3-103">A flat file instance message body, which is required, is what the flat file disassembler processes into one or more XML instance messages.</span></span> <span data-ttu-id="21cf3-104">受信フラット ファイル インスタンス メッセージの本文に含まれるデータを把握するには、本文に対応するフラット ファイル スキーマにフラット ファイル逆アセンブラーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21cf3-104">To know what data to expect in an inbound flat file instance message body, you must configure the flat file disassembler with the flat file schema that corresponds to the body.</span></span> <span data-ttu-id="21cf3-105">使用して、スキーマを指定することができます、**ドキュメント スキーマ**フラット ファイル逆アセンブラーのデザイン時プロパティまたは**XMLNORM です。DocumentSpecName**メッセージ コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="21cf3-105">You can specify the schema by using the **Document schema** design-time property of the flat file disassembler or the **XMLNORM.DocumentSpecName** message context property.</span></span> <span data-ttu-id="21cf3-106">フラット ファイル インスタンス メッセージには本文部分が必要であるため、これらの 2 つの方法のいずれかを使用して、適切なスキーマを構成してください。</span><span class="sxs-lookup"><span data-stu-id="21cf3-106">Because flat file instance messages must have a body part, you must configure the appropriate schema using one of these two methods.</span></span>  
  
 <span data-ttu-id="21cf3-107">送信フラット ファイル インスタンス メッセージを処理する場合、フラット ファイル アセンブラーは、インスタンス メッセージの本文に対して、適切なフラット ファイル スキーマを動的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="21cf3-107">For outbound flat file instance messages, the flat file assembler can dynamically determine the appropriate flat file schema for the body of the instance message.</span></span> <span data-ttu-id="21cf3-108">フラット ファイル アセンブラーは、メッセージの種類から適切なスキーマを決定します。スキーマは、メッセージのターゲットの名前空間およびルート要素名 (両方とも送信メッセージの XML バージョンに必要) の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="21cf3-108">The flat file assembler determines the appropriate schema from the message type, which is a combination of the target namespace and the name of the root element, both of which must be present in the XML version of the outbound message.</span></span> <span data-ttu-id="21cf3-109">構成して使用するフラット ファイル スキーマを明示的に構成する代わりに、**ドキュメント スキーマ**、フラット ファイル アセンブラーのデザイン時プロパティまたは**XMLNORM です。DocumentSpecName**メッセージ コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="21cf3-109">Alternatively, you can explicitly configure the flat file schema to be used by configuring the **Document schema** design-time property of the flat file assembler or the **XMLNORM.DocumentSpecName** message context property.</span></span>  
  
 <span data-ttu-id="21cf3-110">受信フラット ファイル インスタンス メッセージの本文に含まれるデータは、対応するメッセージ コンテキストにコピーできます。これを行うには、受信インスタンス メッセージを処理するためにフラット ファイル逆アセンブラーが使用するフラット ファイル スキーマで、プロパティの昇格を指定します。</span><span class="sxs-lookup"><span data-stu-id="21cf3-110">Data found in inbound flat file instance message bodies can be copied to the corresponding message context by specifying property promotion in the flat file schema being used by the flat file disassembler to process the inbound instance message.</span></span> <span data-ttu-id="21cf3-111">同様に、メッセージ コンテキストのデータを、送信フラット ファイル インスタンスにコピーすることもできます。これを行うには、送信メッセージを処理するためにフラット ファイル アセンブラーが使用するフラット ファイル スキーマで、プロパティの降格を指定します。</span><span class="sxs-lookup"><span data-stu-id="21cf3-111">Likewise, data in the message context can be copied back into outbound flat file instance messages by specifying property demotion in the flat file schema being used by the flat file assembler to process the outbound message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21cf3-112">参照</span><span class="sxs-lookup"><span data-stu-id="21cf3-112">See Also</span></span>  
 <span data-ttu-id="21cf3-113">[フラット ファイル メッセージのヘッダー](../core/flat-file-message-headers.md) </span><span class="sxs-lookup"><span data-stu-id="21cf3-113">[Flat File Message Headers](../core/flat-file-message-headers.md) </span></span>  
 <span data-ttu-id="21cf3-114">[フラット ファイル メッセージのトレーラー](../core/flat-file-message-trailers.md) </span><span class="sxs-lookup"><span data-stu-id="21cf3-114">[Flat File Message Trailers](../core/flat-file-message-trailers.md) </span></span>  
 <span data-ttu-id="21cf3-115">[フラット ファイル メッセージの構造](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="21cf3-115">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 [<span data-ttu-id="21cf3-116">フラット ファイル メッセージのスキーマを作成する方法</span><span class="sxs-lookup"><span data-stu-id="21cf3-116">How to Create Schemas for Flat File Messages</span></span>](../core/how-to-create-schemas-for-flat-file-messages.md)