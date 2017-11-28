---
title: "Windows Server 2003 SP1 および SP2 サービス拒否の状態チェックを無効化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8822c1e4-d146-4361-b25a-7b81cd5cdd3b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b33333efd055a659557513ecc8e0b53a42bc30ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="disabling-windows-server-2003-sp1-and-sp2-denial-of-service-checking"></a><span data-ttu-id="78ebc-102">Windows Server 2003 SP1 および SP2 サービス拒否の状態チェックを無効にします。</span><span class="sxs-lookup"><span data-stu-id="78ebc-102">Disabling Windows Server 2003 SP1 and SP2 Denial of Service Checking</span></span>
> [!NOTE]  
>  <span data-ttu-id="78ebc-103">このトピックでは、Windows Server 2003 にのみ適用します。</span><span class="sxs-lookup"><span data-stu-id="78ebc-103">This topic is applicable only for Windows Server 2003.</span></span>  
  
 <span data-ttu-id="78ebc-104">サービス チェックの Service Pack 2 および Windows Server 2003 Service Pack 1 の拒否を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="78ebc-104">You should disable the Windows Server 2003 Service Pack 1 and Service Pack 2 denial of service checking.</span></span> <span data-ttu-id="78ebc-105">高負荷状況によっては、サービスのチェックの Windows Server 2003 SP1 および SP2 拒否が起こる可能性がありますを誤って指定 TCP/IP 接続が有効、サービス拒否攻撃としてためにです。</span><span class="sxs-lookup"><span data-stu-id="78ebc-105">This is because under certain high-load scenarios, Windows Server 2003 SP1 and SP2 denial of service checking may incorrectly identify valid TCP/IP connections as a denial of service attack.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="78ebc-106">実際のサービス拒否攻撃から低下しないようにすることを確認したら、イントラネットの場合にのみ、この機能を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="78ebc-106">You should disable this feature only in an intranet scenario when you are sure you will not suffer from actual denial of service attacks.</span></span>  
  
## <a name="how-denial-of-service-can-affect-tcpip-connections"></a><span data-ttu-id="78ebc-107">サービス拒否攻撃が TCP/IP 接続に与える影響について</span><span class="sxs-lookup"><span data-stu-id="78ebc-107">How Denial of Service Can Affect TCP/IP Connections</span></span>  
 <span data-ttu-id="78ebc-108">Windows Server 2003 SP1 および SP2 は、サーバーへの同時 TCP/IP 接続のキューのサイズを小さくセキュリティ機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="78ebc-108">Windows Server 2003 SP1 and SP2 implement a security feature that reduces the size of the queue for concurrent TCP/IP connections to the server.</span></span> <span data-ttu-id="78ebc-109">この機能は、サービス拒否攻撃の回避に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="78ebc-109">This feature helps prevent denial of service attacks.</span></span> <span data-ttu-id="78ebc-110">負荷が高い状況で、TCP/IP プロトコルを Windows Server 2003 SP1 またはそれ以降の場合がありますを正しく識別されません TCP/IP 接続が有効、サービス拒否攻撃として。</span><span class="sxs-lookup"><span data-stu-id="78ebc-110">Under heavy load conditions, the TCP/IP protocol in Windows Server 2003 SP1 or later may incorrectly identify valid TCP/IP connections as a denial of service attack.</span></span> <span data-ttu-id="78ebc-111">これが発生するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が過負荷します。</span><span class="sxs-lookup"><span data-stu-id="78ebc-111">This may occur when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is under heavy load.</span></span>  
  
## <a name="modifying-the-registry-entry"></a><span data-ttu-id="78ebc-112">レジストリ エントリを変更します。</span><span class="sxs-lookup"><span data-stu-id="78ebc-112">Modifying the Registry Entry</span></span>  
 <span data-ttu-id="78ebc-113">詳細については、Microsoft サポート技術情報の記事 899599 を参照してください["BizTalk Server ホスト インスタンスが失敗し、BizTalk Server ベースのサーバーが大量のドキュメントを処理するときに一般的なネットワーク エラーがアプリケーション ログに書き込まれます"。](http://go.microsoft.com/fwlink/?LinkId=158860) (http://go.microsoft.com/fwlink/?LinkId=158860)。</span><span class="sxs-lookup"><span data-stu-id="78ebc-113">For more information, see Microsoft Knowledge Base article 899599, ["A BizTalk Server Host instance fails, and a 'General Network' error is written to the Application log when the BizTalk Server-based server processes a high volume of documents"](http://go.microsoft.com/fwlink/?LinkId=158860) (http://go.microsoft.com/fwlink/?LinkId=158860).</span></span> <span data-ttu-id="78ebc-114">作成するのには、この記事の手順に従って、 **SynAttackProtect**をホストする SQL Server を実行しているコンピューター上のレジストリ エントリ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースおよび実行しているコンピューターで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Windows Server で実行されています。2003 SP1 またはそれ以降。</span><span class="sxs-lookup"><span data-stu-id="78ebc-114">Follow the instructions in this article to create the **SynAttackProtect** registry entry on computers running SQL Server that host [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases and on any computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that are running Windows Server 2003 SP1 or later.</span></span>  
  
## <a name="tuning-registry-settings-that-govern-the-level-of-denial-of-service-attack-protection"></a><span data-ttu-id="78ebc-115">サービス拒否攻撃攻撃保護のレベルを制御するレジストリ設定のチューニング</span><span class="sxs-lookup"><span data-stu-id="78ebc-115">Tuning Registry Settings that Govern the Level of Denial of Service Attack Protection</span></span>  
 <span data-ttu-id="78ebc-116">特定のシナリオでは、サービス拒否攻撃保護の管理が、サービスの機能の拒否攻撃が適用されるどの程度積極的に削減できます。</span><span class="sxs-lookup"><span data-stu-id="78ebc-116">In certain scenarios you may want to maintain denial of service protection but reduce how aggressively the denial of service functionality is applied.</span></span> <span data-ttu-id="78ebc-117">次の手順に従って保護機能のサービスの拒否の既定の動作を調整できます。</span><span class="sxs-lookup"><span data-stu-id="78ebc-117">It is possible to tune the default behavior of the denial of service protection feature by following these steps:</span></span>  
  
1.  <span data-ttu-id="78ebc-118">いることを確認、 **SynAttackProtect**レジストリ エントリがの REG_DWORD 値に設定されている**1** 」の説明に従って[http://go.microsoft.com/fwlink/?LinkId=111477](http://go.microsoft.com/fwlink/?LinkId=111477)です。</span><span class="sxs-lookup"><span data-stu-id="78ebc-118">Ensure that the **SynAttackProtect** registry entry is set to a REG_DWORD value of **1** as described at [http://go.microsoft.com/fwlink/?LinkId=111477](http://go.microsoft.com/fwlink/?LinkId=111477).</span></span>  
  
2.  <span data-ttu-id="78ebc-119">構成、 **TcpMaxHalfOpen**レジストリ エントリの説明に従って[http://go.microsoft.com/fwlink/?LinkId=111478](http://go.microsoft.com/fwlink/?LinkId=111478)です。</span><span class="sxs-lookup"><span data-stu-id="78ebc-119">Configure the **TcpMaxHalfOpen** registry entry as described at [http://go.microsoft.com/fwlink/?LinkId=111478](http://go.microsoft.com/fwlink/?LinkId=111478).</span></span>  
  
3.  <span data-ttu-id="78ebc-120">構成、 **TcpMaxHalfOpenRetried**レジストリ エントリの説明に従って[http://go.microsoft.com/fwlink/?LinkId=111479](http://go.microsoft.com/fwlink/?LinkId=111479)です。</span><span class="sxs-lookup"><span data-stu-id="78ebc-120">Configure the **TcpMaxHalfOpenRetried** registry entry as described at [http://go.microsoft.com/fwlink/?LinkId=111479](http://go.microsoft.com/fwlink/?LinkId=111479).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78ebc-121">参照</span><span class="sxs-lookup"><span data-stu-id="78ebc-121">See Also</span></span>  
 [<span data-ttu-id="78ebc-122">運用の準備のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="78ebc-122">Operational Readiness Checklists</span></span>](../technical-guides/operational-readiness-checklists.md)