---
title: フラット ファイル メッセージの本文 |Microsoft Docs
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
ms.openlocfilehash: 0ef973fca636f4e75f05e26638a841e9e51d39b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387950"
---
# <a name="flat-file-message-bodies"></a><span data-ttu-id="af24d-102">フラット ファイル メッセージの本文</span><span class="sxs-lookup"><span data-stu-id="af24d-102">Flat File Message Bodies</span></span>
<span data-ttu-id="af24d-103">フラット ファイル インスタンス メッセージの本文は必須では、フラット ファイル逆アセンブラーの処理を 1 つまたは複数の XML インスタンス メッセージにです。</span><span class="sxs-lookup"><span data-stu-id="af24d-103">A flat file instance message body, which is required, is what the flat file disassembler processes into one or more XML instance messages.</span></span> <span data-ttu-id="af24d-104">受信フラット ファイル インスタンス メッセージの本文に含まれるデータを把握するには、本文に対応するフラット ファイル スキーマのフラット ファイル逆アセンブラーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af24d-104">To know what data to expect in an inbound flat file instance message body, you must configure the flat file disassembler with the flat file schema that corresponds to the body.</span></span> <span data-ttu-id="af24d-105">使用して、スキーマを指定することができます、**ドキュメント スキーマ**フラット ファイル逆アセンブラーのデザイン時プロパティまたは**XMLNORM します。DocumentSpecName**メッセージ コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="af24d-105">You can specify the schema by using the **Document schema** design-time property of the flat file disassembler or the **XMLNORM.DocumentSpecName** message context property.</span></span> <span data-ttu-id="af24d-106">フラット ファイル インスタンス メッセージにはボディ部を設定する必要がありますので、これら 2 つのメソッドのいずれかを使用して、適切なスキーマを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af24d-106">Because flat file instance messages must have a body part, you must configure the appropriate schema using one of these two methods.</span></span>  
  
 <span data-ttu-id="af24d-107">送信フラット ファイル インスタンス メッセージの場合、フラット ファイル アセンブラーは、インスタンス メッセージの本文の適切なフラット ファイル スキーマを動的に決定することができます。</span><span class="sxs-lookup"><span data-stu-id="af24d-107">For outbound flat file instance messages, the flat file assembler can dynamically determine the appropriate flat file schema for the body of the instance message.</span></span> <span data-ttu-id="af24d-108">フラット ファイル アセンブラーは、送信メッセージの XML バージョンに存在する必要があります、ルート要素の名前とターゲットの名前空間の組み合わせは、メッセージの種類から適切なスキーマを決定します。</span><span class="sxs-lookup"><span data-stu-id="af24d-108">The flat file assembler determines the appropriate schema from the message type, which is a combination of the target namespace and the name of the root element, both of which must be present in the XML version of the outbound message.</span></span> <span data-ttu-id="af24d-109">構成して使用するフラット ファイル スキーマを明示的に構成する代わりに、**ドキュメント スキーマ**フラット ファイル アセンブラーのデザイン時プロパティまたは**XMLNORM します。DocumentSpecName**メッセージ コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="af24d-109">Alternatively, you can explicitly configure the flat file schema to be used by configuring the **Document schema** design-time property of the flat file assembler or the **XMLNORM.DocumentSpecName** message context property.</span></span>  
  
 <span data-ttu-id="af24d-110">受信フラット ファイル インスタンス メッセージの本文内のデータは、受信インスタンス メッセージを処理するフラット ファイル逆アセンブラーが使用するフラット ファイル スキーマのプロパティの昇格を指定することで、対応するメッセージ コンテキストにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="af24d-110">Data found in inbound flat file instance message bodies can be copied to the corresponding message context by specifying property promotion in the flat file schema being used by the flat file disassembler to process the inbound instance message.</span></span> <span data-ttu-id="af24d-111">同様に、送信メッセージを処理するフラット ファイル アセンブラーが使用するフラット ファイル スキーマのプロパティの降格を指定することで、送信フラット ファイル インスタンス メッセージにメッセージ コンテキスト内のデータをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="af24d-111">Likewise, data in the message context can be copied back into outbound flat file instance messages by specifying property demotion in the flat file schema being used by the flat file assembler to process the outbound message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af24d-112">参照</span><span class="sxs-lookup"><span data-stu-id="af24d-112">See Also</span></span>  
 <span data-ttu-id="af24d-113">[フラット ファイル メッセージのヘッダー](../core/flat-file-message-headers.md) </span><span class="sxs-lookup"><span data-stu-id="af24d-113">[Flat File Message Headers](../core/flat-file-message-headers.md) </span></span>  
 <span data-ttu-id="af24d-114">[フラット ファイル メッセージのトレーラー](../core/flat-file-message-trailers.md) </span><span class="sxs-lookup"><span data-stu-id="af24d-114">[Flat File Message Trailers](../core/flat-file-message-trailers.md) </span></span>  
 <span data-ttu-id="af24d-115">[フラット ファイル メッセージの構造](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="af24d-115">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 [<span data-ttu-id="af24d-116">フラット ファイル メッセージのスキーマを作成する方法</span><span class="sxs-lookup"><span data-stu-id="af24d-116">How to Create Schemas for Flat File Messages</span></span>](../core/how-to-create-schemas-for-flat-file-messages.md)