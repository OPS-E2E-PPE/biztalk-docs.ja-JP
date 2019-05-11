---
title: 攻撃のサービス拒否攻撃を緩和 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IPSec, message protection
- messages, size
- security, configuring
- Authentication Required property
- security, Internet Information Services (IIS) Lockdown Tool
- security, Denial of Service attacks
- discretionary access control lists (DACLs)
- IPSec, data protection
- Internet Information Services (IIS) Lockdown Tool
- Denial of Service attacks
ms.assetid: f39c0d0a-b890-4c48-874d-5cafbc71473c
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9595bf828a1960f50090371232f25282fed21b6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394421"
---
# <a name="mitigating-denial-of-service-attacks"></a><span data-ttu-id="2349c-102">攻撃のサービス拒否攻撃の緩和</span><span class="sxs-lookup"><span data-stu-id="2349c-102">Mitigating Denial of Service Attacks</span></span>
<span data-ttu-id="2349c-103">BizTalk server とサービスの拒否攻撃からサービスを保護するために、次の軽減策の手法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2349c-103">It is recommended to use the following mitigation techniques to help protect your BizTalk servers and services against Denial of Service attacks.</span></span> <span data-ttu-id="2349c-104">これらの緩和方法のうちは環境に適したを決める必要があります。</span><span class="sxs-lookup"><span data-stu-id="2349c-104">You must decide which of these mitigation techniques are appropriate for your environment.</span></span>  
  
-   <span data-ttu-id="2349c-105">**受信ポートの Authentication Required プロパティを使用します。**</span><span class="sxs-lookup"><span data-stu-id="2349c-105">**Use the Authentication Required property in the receive port.**</span></span> <span data-ttu-id="2349c-106">不明なまたは未解決のパーティ (Guest) から来た場合でも既定では、BizTalk がメッセージ ボックス データベースに受信したすべてのメッセージを送信します。BizTalk Server に多数のメッセージを送信し、飽和状態になる (いっぱいになる) 攻撃者の可能性を軽減するために、メッセージ ボックス データベースを使用できます、**に必要な認証**のみ受信する受信ポートのプロパティBizTalk Server はパーティから送信されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2349c-106">By default, BizTalk sends all the messages it receives to the MessageBox database, even if they come from an unknown or unresolved party (Guest.) To mitigate the potential of an attacker sending a large number of messages to BizTalk Server and flooding (filling) the MessageBox database, you can use the **Authentication Required** property in the receive port to only receive messages that come from parties BizTalk Server knows.</span></span> <span data-ttu-id="2349c-107">不明なパーティから送られたメッセージを削除するか、それらを中断することができます。</span><span class="sxs-lookup"><span data-stu-id="2349c-107">You can choose either to drop the messages coming from an unknown party or to suspend them.</span></span> <span data-ttu-id="2349c-108">詳細については、**に必要な認証**プロパティを参照してください[メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)します。</span><span class="sxs-lookup"><span data-stu-id="2349c-108">For more information about the **Authentication Required** property, see [Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md).</span></span> <span data-ttu-id="2349c-109">加え、**に必要な認証**プロパティ、ファイアウォール ポートのフィルタ リングまたは IP アドレスがサービス拒否攻撃から保護するためにブロックなどの外部メカニズムの使用を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2349c-109">In addition to the **Authentication Required** property, you should consider the use of an external mechanism such as firewall port filtering or IP-address blocking to protect against Denial of Service attacks.</span></span>  
  
-   <span data-ttu-id="2349c-110">**BizTalk が受信できるメッセージのサイズを制限します。**</span><span class="sxs-lookup"><span data-stu-id="2349c-110">**Limit the size of the messages that BizTalk can receive.**</span></span> <span data-ttu-id="2349c-111">たとえば、使用すると、SOAP 受信アダプター maxRequestLength 属性を設定して非常に大きいサイズのメッセージの受信を回避できます、 \<httpRuntime\>可能なサイズに要素。</span><span class="sxs-lookup"><span data-stu-id="2349c-111">For example, when you use the SOAP receive adapter, you can avoid receiving very large messages size by setting the maxRequestLength attribute in the \<httpRuntime\> element to an acceptable size.</span></span> <span data-ttu-id="2349c-112">\<HttpRuntime\>にある Machine.config ファイルで要素が定義されている、 \<*ドライブ*\>:\\<*Windowsディレクトリ*\>\Microsoft.NET\Framework\vX.X.XXXXX\CONFIG ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="2349c-112">The \<httpRuntime\> element is defined in the Machine.config file, which is located in the \<*drive*\>:\\<*Windows directory*\>\Microsoft.NET\Framework\vX.X.XXXXX\CONFIG directory.</span></span> <span data-ttu-id="2349c-113">詳細については\<httpRuntime\>要素では、Microsoft MSDN Web サイトを参照して[ http://go.microsoft.com/fwlink/?LinkId=60948](http://go.microsoft.com/fwlink/?LinkId=60948)します。</span><span class="sxs-lookup"><span data-stu-id="2349c-113">For more information about \<httpRuntime\> element, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkId=60948](http://go.microsoft.com/fwlink/?LinkId=60948).</span></span>  
  
-   <span data-ttu-id="2349c-114">**強力な Dacl を使用して受信場所です。**</span><span class="sxs-lookup"><span data-stu-id="2349c-114">**Use strong DACLs for receive locations.**</span></span> <span data-ttu-id="2349c-115">受信場所の格納場所で、強力な随意アクセス制御リスト (Dacl) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2349c-115">It is recommended that you use strong discretionary access control lists (DACLs) in the drop locations for the receive locations.</span></span> <span data-ttu-id="2349c-116">たとえば、許可されたユーザーだけがこの場所でメッセージをドロップできるように元のファイルの受信場所がメッセージを取得するディレクトリに強力な Dacl を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2349c-116">For example, you must use strong DACLs in the directory from which the file receive location picks up messages, so that only authorized users can drop messages in this location.</span></span>  
  
-   <span data-ttu-id="2349c-117">**IPSec を使用します。**</span><span class="sxs-lookup"><span data-stu-id="2349c-117">**Use IPSec.**</span></span> <span data-ttu-id="2349c-118">表示されない場合、ハードウェアまたはソフトウェア ファイアウォールを使用して、別の BizTalk Server が 1 つのサーバーから転送には、メッセージとデータを保護するためにインターネット プロトコル セキュリティ (IPSec) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="2349c-118">If you do not use hardware or software firewalls, use Internet Protocol security (IPSec) to help protect the messages and data as BizTalk Server transfers it from one server to another.</span></span> <span data-ttu-id="2349c-119">IPSec の詳細については、Microsoft ダウンロード センターを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=60949](http://go.microsoft.com/fwlink/?LinkId=60949)します。</span><span class="sxs-lookup"><span data-stu-id="2349c-119">For more information about IPSec, see the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkId=60949](http://go.microsoft.com/fwlink/?LinkId=60949).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2349c-120">参照</span><span class="sxs-lookup"><span data-stu-id="2349c-120">See Also</span></span>  
 <span data-ttu-id="2349c-121">[潜在的な脅威を識別します。](../core/identifying-potential-threats.md) </span><span class="sxs-lookup"><span data-stu-id="2349c-121">[Identifying Potential Threats](../core/identifying-potential-threats.md) </span></span>  
 [<span data-ttu-id="2349c-122">セキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="2349c-122">Planning for Security</span></span>](../core/planning-for-security.md)