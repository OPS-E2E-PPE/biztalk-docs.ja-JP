---
title: "攻撃のサービス拒否攻撃を緩和 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a02e3eddcd43acf67e8e928e1a8f172c0019c616
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="mitigating-denial-of-service-attacks"></a><span data-ttu-id="c5233-102">攻撃のサービス拒否攻撃の緩和</span><span class="sxs-lookup"><span data-stu-id="c5233-102">Mitigating Denial of Service Attacks</span></span>
<span data-ttu-id="c5233-103">サービスの拒否攻撃から BizTalk Server とサービスを保護するには、次の緩和方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c5233-103">It is recommended to use the following mitigation techniques to help protect your BizTalk servers and services against Denial of Service attacks.</span></span> <span data-ttu-id="c5233-104">どの緩和方法が環境に適しているのかを判断してください。</span><span class="sxs-lookup"><span data-stu-id="c5233-104">You must decide which of these mitigation techniques are appropriate for your environment.</span></span>  
  
-   <span data-ttu-id="c5233-105">**受信ポートの Authentication Required プロパティを使用します。**</span><span class="sxs-lookup"><span data-stu-id="c5233-105">**Use the Authentication Required property in the receive port.**</span></span> <span data-ttu-id="c5233-106">既定では、BizTalk はメッセージ ボックス データベースに受信したすべてのメッセージを送信します。メッセージの送信元が不明なパーティまたは未解決のパーティ (ゲスト) である場合も同様です。BizTalk Server に大量のメッセージを送信して、いっぱいになる (いっぱい) 攻撃者の可能性を軽減するために、メッセージ ボックス データベースを使えば、**認証を必要と**のみ受信する受信ポートのプロパティBizTalk Server はパーティから送信されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="c5233-106">By default, BizTalk sends all the messages it receives to the MessageBox database, even if they come from an unknown or unresolved party (Guest.) To mitigate the potential of an attacker sending a large number of messages to BizTalk Server and flooding (filling) the MessageBox database, you can use the **Authentication Required** property in the receive port to only receive messages that come from parties BizTalk Server knows.</span></span> <span data-ttu-id="c5233-107">不明なパーティからのメッセージをドロップするか、それらのメッセージを保留するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c5233-107">You can choose either to drop the messages coming from an unknown party or to suspend them.</span></span> <span data-ttu-id="c5233-108">詳細については、 **Authentication Required**プロパティを参照してください[メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)です。</span><span class="sxs-lookup"><span data-stu-id="c5233-108">For more information about the **Authentication Required** property, see [Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md).</span></span> <span data-ttu-id="c5233-109">加え、 **Authentication Required**プロパティ、ファイアウォール ポートのフィルタ リングまたは IP アドレスのサービス拒否攻撃を防ぐためにブロックなどの外部メカニズムの使用を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5233-109">In addition to the **Authentication Required** property, you should consider the use of an external mechanism such as firewall port filtering or IP-address blocking to protect against Denial of Service attacks.</span></span>  
  
-   <span data-ttu-id="c5233-110">**BizTalk が受信できるメッセージのサイズを制限します。**</span><span class="sxs-lookup"><span data-stu-id="c5233-110">**Limit the size of the messages that BizTalk can receive.**</span></span> <span data-ttu-id="c5233-111">たとえばを使用するときに、SOAP 受信アダプター maxRequestLength 属性を設定して非常に大きいサイズのメッセージの受信を避けることができます、 \<httpRuntime\>可能なサイズに要素。</span><span class="sxs-lookup"><span data-stu-id="c5233-111">For example, when you use the SOAP receive adapter, you can avoid receiving very large messages size by setting the maxRequestLength attribute in the \<httpRuntime\> element to an acceptable size.</span></span> <span data-ttu-id="c5233-112">\<HttpRuntime\>にある Machine.config ファイルに要素が定義されている、 \<*ドライブ*\>:\\<*Windowsディレクトリ*\>\Microsoft.NET\Framework\vX.X.XXXXX\CONFIG ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="c5233-112">The \<httpRuntime\> element is defined in the Machine.config file, which is located in the \<*drive*\>:\\<*Windows directory*\>\Microsoft.NET\Framework\vX.X.XXXXX\CONFIG directory.</span></span> <span data-ttu-id="c5233-113">詳細については\<httpRuntime\>要素、Microsoft MSDN Web サイトを参照して[http://go.microsoft.com/fwlink/?LinkId=60948](http://go.microsoft.com/fwlink/?LinkId=60948)です。</span><span class="sxs-lookup"><span data-stu-id="c5233-113">For more information about \<httpRuntime\> element, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkId=60948](http://go.microsoft.com/fwlink/?LinkId=60948).</span></span>  
  
-   <span data-ttu-id="c5233-114">**強力な Dacl を使用するには、場所が表示されます。**</span><span class="sxs-lookup"><span data-stu-id="c5233-114">**Use strong DACLs for receive locations.**</span></span> <span data-ttu-id="c5233-115">受信場所のドロップ場所には強力な随意アクセス制御リスト (DACL) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c5233-115">It is recommended that you use strong discretionary access control lists (DACLs) in the drop locations for the receive locations.</span></span> <span data-ttu-id="c5233-116">たとえば、認証されたユーザーだけがこの場所にメッセージをドロップできるように、ファイルの受信場所がメッセージを取得するディレクトリに強力な DACL を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5233-116">For example, you must use strong DACLs in the directory from which the file receive location picks up messages, so that only authorized users can drop messages in this location.</span></span>  
  
-   <span data-ttu-id="c5233-117">**IPSec を使用します。**</span><span class="sxs-lookup"><span data-stu-id="c5233-117">**Use IPSec.**</span></span> <span data-ttu-id="c5233-118">ハードウェアとソフトウェアのファイアウォールをどちらも使用しない場合、あるサーバーから別のサーバーにメッセージとデータを移動するときに、インターネット プロトコル セキュリティ (IPSec) を使用してメッセージとデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="c5233-118">If you do not use hardware or software firewalls, use Internet Protocol security (IPSec) to help protect the messages and data as BizTalk Server transfers it from one server to another.</span></span> <span data-ttu-id="c5233-119">IPSec の詳細については、Microsoft ダウンロード センターを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=60949](http://go.microsoft.com/fwlink/?LinkId=60949)です。</span><span class="sxs-lookup"><span data-stu-id="c5233-119">For more information about IPSec, see the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkId=60949](http://go.microsoft.com/fwlink/?LinkId=60949).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5233-120">参照</span><span class="sxs-lookup"><span data-stu-id="c5233-120">See Also</span></span>  
 <span data-ttu-id="c5233-121">[潜在的な脅威を識別します。](../core/identifying-potential-threats.md) </span><span class="sxs-lookup"><span data-stu-id="c5233-121">[Identifying Potential Threats](../core/identifying-potential-threats.md) </span></span>  
 [<span data-ttu-id="c5233-122">セキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="c5233-122">Planning for Security</span></span>](../core/planning-for-security.md)