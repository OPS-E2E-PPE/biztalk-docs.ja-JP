---
title: "グローバルまたはフォールバック アグリーメント プロパティの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c375d03-6f22-4a67-9eac-d8896de2f7ee
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eb693a17cad17eadaf0d005d12075dde30daa33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-global-or-fallback-agreement-properties"></a><span data-ttu-id="ab5ba-102">グローバルまたはフォールバック アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="ab5ba-102">Configuring Global or Fallback Agreement Properties</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ab5ba-103"> は、インターチェンジの解決に使用するためのアグリーメントが見つからない場合、フォールバック アグリーメント プロパティを使用してメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="ab5ba-103"> uses fallback agreement properties to process a message when it does not discover an agreement to resolve to for an interchange.</span></span> <span data-ttu-id="ab5ba-104">フォールバック アグリーメント プロパティは、アグリーメントがわかっているときは使用されず、すべてのアグリーメントに適用されるものではありません。</span><span class="sxs-lookup"><span data-stu-id="ab5ba-104">Fallback agreement properties are not used when the agreement is known, and do not apply to any or all agreements.</span></span>  
  
 <span data-ttu-id="ab5ba-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はメッセージを受信すると、アグリーメントの送信者の情報とメッセージの送信者の情報を照合しようと試みます。</span><span class="sxs-lookup"><span data-stu-id="ab5ba-105">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives a message, it attempts to match the sender information for an agreement with the sender information in the message.</span></span> <span data-ttu-id="ab5ba-106">送信者の情報は、X12 メッセージの場合は IS5 および IS6 データ要素に格納され、EDIFACT の場合は UNB2.1 および UNB 2.2 データ要素に格納されています。</span><span class="sxs-lookup"><span data-stu-id="ab5ba-106">The sender information is in the ISA5 and ISA6 data elements for X12 message, and the UNB2.1 and UNB 2.2 data elements for EDIFACT.</span></span> <span data-ttu-id="ab5ba-107">契約情報は、の一方向アグリーメント タブにある識別子タブには、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ab5ba-107">The agreement information is in the Identifier tabs in the one-way agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="ab5ba-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がアグリーメントを見つけられない場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はフォールバック アグリーメント プロパティを使用して名前空間を決定し、メッセージを処理して、受信確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="ab5ba-108">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does not discover the agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the fallback agreement properties to determine the namespace, process the message, and send any acknowledgments.</span></span>  
  
 <span data-ttu-id="ab5ba-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がメッセージを送信するとき、EDI 送信パイプラインが、メッセージ ボックスの XML メッセージをサブスクライブしている送信ポートとアグリーメントに関連付けられている送信ポートを照合することにより、メッセージの解決に使用するアグリーメントを特定します。</span><span class="sxs-lookup"><span data-stu-id="ab5ba-109">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends a message, the EDI send pipeline determines the agreement that the message resolves to by matching the send port that subscribes to the XML message in the MessageBox, with the send port associated with the agreement.</span></span> <span data-ttu-id="ab5ba-110">送信ポートがアグリーメントに関連付けられていない場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はフォールバック アグリーメント プロパティを使用して、メッセージを送信するために処理します。</span><span class="sxs-lookup"><span data-stu-id="ab5ba-110">If the send port is not associated with an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the fallback agreement properties to process the message for sending.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab5ba-111">送信ポートの関連付けは、アグリーメントを解決する 1 つの方法にすぎません。</span><span class="sxs-lookup"><span data-stu-id="ab5ba-111">Send port association is only one way of doing agreement resolution.</span></span> <span data-ttu-id="ab5ba-112">送信メッセージのアグリーメントの解決の詳細については、次を参照してください。[アグリーメントの解決と送信 EDI メッセージのスキーマの決定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="ab5ba-112">For more information about agreement resolution for outgoing messages, see [Agreement Resolution and Schema Determination for Outgoing EDI Messages](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ab5ba-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ab5ba-113">In This Section</span></span>  
  
-   [<span data-ttu-id="ab5ba-114">設定の X12 フォールバック アグリーメントのプロパティ</span><span class="sxs-lookup"><span data-stu-id="ab5ba-114">Configuring X12 Fallback Agreement Properties</span></span>](../core/configuring-x12-fallback-agreement-properties.md)  
  
-   [<span data-ttu-id="ab5ba-115">EDIFACT フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="ab5ba-115">Configuring EDIFACT Fallback Agreement Properties</span></span>](../core/configuring-edifact-fallback-agreement-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="ab5ba-116">参照</span><span class="sxs-lookup"><span data-stu-id="ab5ba-116">See Also</span></span>  
 [<span data-ttu-id="ab5ba-117">EDI 処理におけるアグリーメントのロール</span><span class="sxs-lookup"><span data-stu-id="ab5ba-117">The Role of Agreements in EDI Processing</span></span>](../core/the-role-of-agreements-in-edi-processing.md)