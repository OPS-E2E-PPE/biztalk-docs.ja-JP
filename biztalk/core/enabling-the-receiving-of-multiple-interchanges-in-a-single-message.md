---
title: インターチェンジの 1 つのメッセージで複数の受信を有効にする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c98bcd2e-495a-49d8-a471-6e23b1e161f9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77af57fb4a72e2e0c039b512d4e6f30659ccedd5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006851"
---
# <a name="enabling-the-receiving-of-multiple-interchanges-in-a-single-message"></a><span data-ttu-id="89229-102">単一メッセージ内の複数インターチェンジの受信を可能にする</span><span class="sxs-lookup"><span data-stu-id="89229-102">Enabling the Receiving of Multiple Interchanges in a Single Message</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="89229-103"> は、複数のインターチェンジを含むメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="89229-103"> can process a message that contains multiple interchanges.</span></span> <span data-ttu-id="89229-104">X12 メッセージには、複数の ISA ヘッダーと IEA トレーラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="89229-104">For an X12 message, such a message would include multiple ISA headers and IEA trailers.</span></span> <span data-ttu-id="89229-105">EDIFACT メッセージには、複数の UNA/UNB ヘッダーと UNZ トレーラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="89229-105">For an EDIFACT message, such a message would include multiple UNA/UNB headers and UNZ trailers.</span></span>  
  
 <span data-ttu-id="89229-106">設定する必要があります、単一メッセージ内の複数のインターチェンジを解析するには、EdiReceive または AS2EdiReceive パイプラインで EDI 逆アセンブラを有効にする、 **DetectMID**パイプライン プロパティを**True**します。</span><span class="sxs-lookup"><span data-stu-id="89229-106">To enable the EDI Disassembler in the EdiReceive or AS2EdiReceive pipeline to parse multiple interchanges in a single message, you must set the **DetectMID** pipeline property to **True**.</span></span> <span data-ttu-id="89229-107">(MID は Mmultiple Interchange Disassembling の略称です)。このプロパティは、既定では True に設定されています。</span><span class="sxs-lookup"><span data-stu-id="89229-107">(MID stands for multiple interchange disassembling.) This property is set to True by default.</span></span>  
  
 <span data-ttu-id="89229-108">EDI 逆アセンブラーを含む受信パイプラインが、複数のインターチェンジを含むメッセージを受信すると、逆アセンブラーが、各インターチェンジをインターチェンジ ヘッダーからインターチェンジ トレーラーまで解析します。</span><span class="sxs-lookup"><span data-stu-id="89229-108">When the receive pipeline that includes the EDI Disassembler receives a message with multiple interchange, the Disassembler will parse each interchange from the interchange header to the interchange trailer.</span></span> <span data-ttu-id="89229-109">この処理は、次のルールに従って行われます。</span><span class="sxs-lookup"><span data-stu-id="89229-109">This processing is done according to the following rules:</span></span>  
  
- <span data-ttu-id="89229-110">同じメッセージ内にあるすべてのインターチェンジに対して、同じ種類のエンコード (X12 または EDIFACT) が使用されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="89229-110">All interchanges in the same message must be of the same encoding type, either X12 or EDIFACT.</span></span> <span data-ttu-id="89229-111">メッセージ内のインターチェンジに複数の種類のエンコードが使用されている場合、EDI 逆アセンブラーは、メッセージ内の最初のインターチェンジと同じ種類のエンコードが使用されているすべてのインターチェンジを処理します。</span><span class="sxs-lookup"><span data-stu-id="89229-111">If the message contains interchanges of more than one encoding type, the EDI Disassembler will process all interchanges that have the same encoding type as the first interchange in the message.</span></span> <span data-ttu-id="89229-112">逆アセンブラーは、最初のインターチェンジに使用されているエンコードと異なる種類のエンコードが使用されているインターチェンジはすべて無視します。</span><span class="sxs-lookup"><span data-stu-id="89229-112">The Disassembler will ignore all interchanges that are of a different encoding type from the first interchange.</span></span>  
  
- <span data-ttu-id="89229-113">EDI 逆アセンブラーは、インターチェンジのインターチェンジ トレーラーと、その次のインターチェンジのインターチェンジ ヘッダーの間にある文字をすべて無視します。</span><span class="sxs-lookup"><span data-stu-id="89229-113">The EDI Disassembler will ignore any character between the interchange trailer of one interchange and the interchange heading of the next interchange.</span></span>  
  
- <span data-ttu-id="89229-114">いずれかを選択して認証を有効にした場合、**認証が失敗した場合は、メッセージを削除**または**認証が失敗した場合は、メッセージを保持する**し、受信ポートのプロパティ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]されますメッセージ内の複数のインターチェンジのいずれかが失敗した場合は、メッセージ全体を中断します。</span><span class="sxs-lookup"><span data-stu-id="89229-114">If you enable authentication by selecting either the **Drop messages if authentication fails** or the **Keep messages if authentication fails** property for the receive port, then [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the entire message if any one of the multiple interchanges in the message fails.</span></span>  
  
- <span data-ttu-id="89229-115">認証を有効にした場合、同じメッセージ内にアグリーメントに対して解決されないインターチェンジが 1 つでも存在すると、メッセージ内のすべてのインターチェンジが中断され、アグリーメントに対して解決されたインターチェンジについても受信確認は返されません。</span><span class="sxs-lookup"><span data-stu-id="89229-115">If you enable authentication, and if any one interchange in the same message does not resolve to an agreement, then all interchanges in the message will be suspended, and no acknowledgments will be returned, even for those interchanges that did resolve to an agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="89229-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="89229-116">Prerequisites</span></span>  
 <span data-ttu-id="89229-117">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="89229-117">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-enable-the-receiving-of-multiple-interchanges-in-a-message"></a><span data-ttu-id="89229-118">メッセージ内の複数のインターチェンジの受信を可能にするには</span><span class="sxs-lookup"><span data-stu-id="89229-118">To enable the receiving of multiple interchanges in a message</span></span>  
  
1. <span data-ttu-id="89229-119">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**受信場所**ノードで、複数の受信を可能にする受信場所がインターチェンジの 1 つのメッセージで、クリックして右クリック**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="89229-119">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **Receive Locations** node, right-click the receive location that you want to enable to receive multiple interchange in a single message, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="89229-120">受信パイプライン (EdiReceive または AS2EdiReceive のいずれか) の横にある省略記号をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89229-120">Click the ellipses next to the receive pipeline (which must be either EdiReceive or AS2EdiReceive).</span></span>  
  
3. <span data-ttu-id="89229-121">**パイプラインの構成**ダイアログ ボックスで、セット、 **DetectMID**パイプライン プロパティを**True**します。</span><span class="sxs-lookup"><span data-stu-id="89229-121">In the **Configure Pipeline** dialog box, set the **DetectMID** pipeline property to **True**.</span></span>  
  
4. <span data-ttu-id="89229-122">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="89229-122">Click **OK**, then click **OK** again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89229-123">参照</span><span class="sxs-lookup"><span data-stu-id="89229-123">See Also</span></span>  
 [<span data-ttu-id="89229-124">EDI ソリューションのポートの構成</span><span class="sxs-lookup"><span data-stu-id="89229-124">Configuring Ports for an EDI Solution</span></span>](../core/configuring-ports-for-an-edi-solution.md)