---
title: グローバルまたはフォールバック アグリーメント プロパティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c375d03-6f22-4a67-9eac-d8896de2f7ee
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d44624a4f505cf7d3c4e53fe55e4203917cf41f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391081"
---
# <a name="configuring-global-or-fallback-agreement-properties"></a><span data-ttu-id="a479f-102">グローバルまたはフォールバック アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="a479f-102">Configuring Global or Fallback Agreement Properties</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a479f-103">インターチェンジに解決するためのアグリーメントは検出されないときにメッセージを処理するのにには、フォールバック アグリーメントのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="a479f-103">uses fallback agreement properties to process a message when it does not discover an agreement to resolve to for an interchange.</span></span> <span data-ttu-id="a479f-104">フォールバック アグリーメントのプロパティはアグリーメントがわかっている場合は使用されませんし、すべてのアグリーメントには適用されません。</span><span class="sxs-lookup"><span data-stu-id="a479f-104">Fallback agreement properties are not used when the agreement is known, and do not apply to any or all agreements.</span></span>  
  
 <span data-ttu-id="a479f-105">ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がメッセージを受信メッセージの送信者の情報と、アグリーメントの送信者の情報と一致させようとします。</span><span class="sxs-lookup"><span data-stu-id="a479f-105">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives a message, it attempts to match the sender information for an agreement with the sender information in the message.</span></span> <span data-ttu-id="a479f-106">送信者の情報は、X12 の ISA5 および ISA6 のデータ要素では、メッセージと EDIFACT の場合は UNB2.1 および UNB 2.2 データ要素です。</span><span class="sxs-lookup"><span data-stu-id="a479f-106">The sender information is in the ISA5 and ISA6 data elements for X12 message, and the UNB2.1 and UNB 2.2 data elements for EDIFACT.</span></span> <span data-ttu-id="a479f-107">契約の情報は、の一方向アグリーメント タブで、識別子 タブは、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="a479f-107">The agreement information is in the Identifier tabs in the one-way agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="a479f-108">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、契約書を検出しません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]フォールバック アグリーメント プロパティを使用して名前空間を決定し、メッセージを処理し、受信確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="a479f-108">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does not discover the agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the fallback agreement properties to determine the namespace, process the message, and send any acknowledgments.</span></span>  
  
 <span data-ttu-id="a479f-109">ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アグリーメントに関連付けられている送信ポートと送信を照合することによってポートにメッセージが解決されるアグリーメントが、メッセージ ボックス内の XML メッセージにサブスクライブ メッセージを送信し、EDI 送信パイプラインを決定します。</span><span class="sxs-lookup"><span data-stu-id="a479f-109">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends a message, the EDI send pipeline determines the agreement that the message resolves to by matching the send port that subscribes to the XML message in the MessageBox, with the send port associated with the agreement.</span></span> <span data-ttu-id="a479f-110">送信ポートは、アグリーメントに関連付けられていない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を送信するためのメッセージを処理するフォールバック アグリーメントのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="a479f-110">If the send port is not associated with an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the fallback agreement properties to process the message for sending.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a479f-111">送信ポートの関連付けはアグリーメントの解決を行う方法の 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="a479f-111">Send port association is only one way of doing agreement resolution.</span></span> <span data-ttu-id="a479f-112">送信メッセージのアグリーメントの解決の詳細については、次を参照してください。[アグリーメントの解決と送信 EDI メッセージのスキーマ決定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="a479f-112">For more information about agreement resolution for outgoing messages, see [Agreement Resolution and Schema Determination for Outgoing EDI Messages](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a479f-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a479f-113">In This Section</span></span>  
  
-   [<span data-ttu-id="a479f-114">X12 フォールバック アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="a479f-114">Configuring X12 Fallback Agreement Properties</span></span>](../core/configuring-x12-fallback-agreement-properties.md)  
  
-   [<span data-ttu-id="a479f-115">EDIFACT フォールバック アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="a479f-115">Configuring EDIFACT Fallback Agreement Properties</span></span>](../core/configuring-edifact-fallback-agreement-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="a479f-116">参照</span><span class="sxs-lookup"><span data-stu-id="a479f-116">See Also</span></span>  
 [<span data-ttu-id="a479f-117">EDI 処理におけるアグリーメントのロール</span><span class="sxs-lookup"><span data-stu-id="a479f-117">The Role of Agreements in EDI Processing</span></span>](../core/the-role-of-agreements-in-edi-processing.md)