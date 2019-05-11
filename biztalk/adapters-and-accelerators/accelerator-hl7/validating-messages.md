---
title: メッセージの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, acknowledgements
- messages, acknowledgements
- acknowledgements, validating
- validating, messages
- acknowledgements, messages
- messages, validating
ms.assetid: 7dba0f40-5e19-4598-82cb-22c71e9536c6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fde2a092499f3e5c4c90d16af4043b532131de47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286337"
---
# <a name="validating-messages"></a><span data-ttu-id="30fbc-102">メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="30fbc-102">Validating Messages</span></span>
<span data-ttu-id="30fbc-103">Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) エンコードされた ACK メッセージの受信メッセージの受信確認 (ACK) をアプリケーションから送信または取引先、HL7 への変換が必要な HL7 XML メッセージの形式でサポートしています。</span><span class="sxs-lookup"><span data-stu-id="30fbc-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) supports sending acknowledgments (ACK) for inbound messages from an application or trading partner in the form of an HL7 XML receipt that might need conversion to an HL7 encoded ACK message.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="30fbc-104">通常、関連する受信 (取引先パートナー形式) ドキュメントの仕様に対する受信メッセージを確認した後は、受信確認を生成します。</span><span class="sxs-lookup"><span data-stu-id="30fbc-104">typically generates a receipt after it checks the inbound message against the relevant inbound (trading-partner format) document specification.</span></span> <span data-ttu-id="30fbc-105">すべてのセグメントの検証に合格すると[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]アプリケーションへの同意を示す受信確認を返します。</span><span class="sxs-lookup"><span data-stu-id="30fbc-105">When all the segments pass validation, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] returns a receipt that indicates acceptance to the application.</span></span> <span data-ttu-id="30fbc-106">それ以外の場合、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エラーまたは障害/拒否を示す確認メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="30fbc-106">Otherwise, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates a receipt indicating error or failure/reject.</span></span>  
  
 <span data-ttu-id="30fbc-107">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ACK の送信が HL7 標準に対する構文と概略のエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="30fbc-107">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ACK transmission reports syntactical and schematic errors against the HL7 standard.</span></span> <span data-ttu-id="30fbc-108">検証が失敗した場合、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ドキュメントを保留中のメッセージ キューに配置し、拒否の詳細を示す確認メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="30fbc-108">If the validation fails, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] places the document in the suspended message queue and returns a receipt detailing the rejection.</span></span> <span data-ttu-id="30fbc-109">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーサーは、データ型、構文、およびスキーマの検証チェックを含む検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="30fbc-109">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] parser performs validation that involves checking data types, syntax, and the schema validation.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="30fbc-110">受信場所の詳細と共に解析中に発生したエラーについて概略を記録します。</span><span class="sxs-lookup"><span data-stu-id="30fbc-110">records any schematic errors that occur in parsing in the receipt along with the location details.</span></span>  
  
 <span data-ttu-id="30fbc-111">時間を構成、作成する必要がある、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ACK に対応するために必要なアーティファクト</span><span class="sxs-lookup"><span data-stu-id="30fbc-111">At configure time, you need to create the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] artifacts required for responding with an ACK.</span></span> <span data-ttu-id="30fbc-112">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーサーが HL7 正規 ACK XML インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="30fbc-112">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] parser creates the HL7 canonical ACK XML instance.</span></span> <span data-ttu-id="30fbc-113">BizTalk では、これを適切な BizTalk マップで必要なバージョン形式に変換し、変換先の形式を検証します。</span><span class="sxs-lookup"><span data-stu-id="30fbc-113">BizTalk converts this to the required version format in an appropriate BizTalk map and validates the destination format.</span></span> <span data-ttu-id="30fbc-114">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]シリアライザーは、HL7 でエンコードされたインスタンスにメッセージを変換します。</span><span class="sxs-lookup"><span data-stu-id="30fbc-114">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer then converts the message into an HL7-encoded instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30fbc-115">受信メッセージの区切り記号の間に競合があるしで指定された場合、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成し、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ACK メッセージを受信メッセージの同じ区切り記号を使用し、構成を上書きを生成します。設定。</span><span class="sxs-lookup"><span data-stu-id="30fbc-115">If there is a conflict between the delimiters of an inbound message and those specified in the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuration, then [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will generate an ACK message that uses the same delimiters of the inbound message and overrides the configuration settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30fbc-116">参照</span><span class="sxs-lookup"><span data-stu-id="30fbc-116">See Also</span></span>  
 <span data-ttu-id="30fbc-117">[作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="30fbc-117">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="30fbc-118">[プログラミング ガイド](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span><span class="sxs-lookup"><span data-stu-id="30fbc-118">[Programming Guide](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span></span>  
 [<span data-ttu-id="30fbc-119">ACK メッセージ モード</span><span class="sxs-lookup"><span data-stu-id="30fbc-119">ACK Message Modes</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)