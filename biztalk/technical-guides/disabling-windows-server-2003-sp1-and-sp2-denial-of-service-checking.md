---
title: Windows Server 2003 SP1 および SP2 サービス拒否チェックの無効化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8822c1e4-d146-4361-b25a-7b81cd5cdd3b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8a4d25a694c74c9d5667995b4d70866fc021e3e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305749"
---
# <a name="disabling-windows-server-2003-sp1-and-sp2-denial-of-service-checking"></a><span data-ttu-id="115bd-102">Windows Server 2003 SP1 および SP2 サービス拒否チェックの無効化</span><span class="sxs-lookup"><span data-stu-id="115bd-102">Disabling Windows Server 2003 SP1 and SP2 Denial of Service Checking</span></span>
> [!NOTE]  
>  <span data-ttu-id="115bd-103">このトピックでは、Windows Server 2003 にのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="115bd-103">This topic is applicable only for Windows Server 2003.</span></span>  
  
 <span data-ttu-id="115bd-104">サービス チェックの Windows Server 2003 Service Pack 1 および Service Pack 2 の拒否を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="115bd-104">You should disable the Windows Server 2003 Service Pack 1 and Service Pack 2 denial of service checking.</span></span> <span data-ttu-id="115bd-105">これは、ため、一部の負荷が高いシナリオで Windows Server 2003 SP1 および SP2 サービス チェックの拒否が起こる可能性があります誤認する有効な TCP/IP 接続として、サービス拒否攻撃です。</span><span class="sxs-lookup"><span data-stu-id="115bd-105">This is because under certain high-load scenarios, Windows Server 2003 SP1 and SP2 denial of service checking may incorrectly identify valid TCP/IP connections as a denial of service attack.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="115bd-106">実際のサービス拒否攻撃から低下しないようにすることを確認したら、イントラネットのシナリオでのみこの機能を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="115bd-106">You should disable this feature only in an intranet scenario when you are sure you will not suffer from actual denial of service attacks.</span></span>  
  
## <a name="how-denial-of-service-can-affect-tcpip-connections"></a><span data-ttu-id="115bd-107">サービス拒否が TCP/IP 接続に影響を与える</span><span class="sxs-lookup"><span data-stu-id="115bd-107">How Denial of Service Can Affect TCP/IP Connections</span></span>  
 <span data-ttu-id="115bd-108">Windows Server 2003 SP1 および SP2 は、サーバーへの同時 TCP/IP 接続のキューのサイズを小さくセキュリティ機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="115bd-108">Windows Server 2003 SP1 and SP2 implement a security feature that reduces the size of the queue for concurrent TCP/IP connections to the server.</span></span> <span data-ttu-id="115bd-109">この機能は、サービス拒否攻撃の回避に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="115bd-109">This feature helps prevent denial of service attacks.</span></span> <span data-ttu-id="115bd-110">負荷条件下で Windows Server 2003 SP1 またはそれ以降は、TCP/IP プロトコル可能性がありますを正しく識別しない有効な TCP/IP 接続をサービス拒否攻撃として。</span><span class="sxs-lookup"><span data-stu-id="115bd-110">Under heavy load conditions, the TCP/IP protocol in Windows Server 2003 SP1 or later may incorrectly identify valid TCP/IP connections as a denial of service attack.</span></span> <span data-ttu-id="115bd-111">これが発生するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が過負荷。</span><span class="sxs-lookup"><span data-stu-id="115bd-111">This may occur when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is under heavy load.</span></span>  
  
## <a name="modifying-the-registry-entry"></a><span data-ttu-id="115bd-112">レジストリ エントリを変更します。</span><span class="sxs-lookup"><span data-stu-id="115bd-112">Modifying the Registry Entry</span></span>  
 <span data-ttu-id="115bd-113">詳細については、マイクロソフト サポート技術情報記事 899599 を参照してください["BizTalk Server ホスト インスタンスが失敗すると、BizTalk Server ベースのサーバーは、大量のドキュメントを処理するときに、"一般的なネットワーク"エラーがアプリケーション ログに書き込まれます"。](http://go.microsoft.com/fwlink/?LinkId=158860) (<http://go.microsoft.com/fwlink/?LinkId=158860>).</span><span class="sxs-lookup"><span data-stu-id="115bd-113">For more information, see Microsoft Knowledge Base article 899599, ["A BizTalk Server Host instance fails, and a 'General Network' error is written to the Application log when the BizTalk Server-based server processes a high volume of documents"](http://go.microsoft.com/fwlink/?LinkId=158860) (<http://go.microsoft.com/fwlink/?LinkId=158860>).</span></span> <span data-ttu-id="115bd-114">作成するのには、この記事の手順に従って、 **SynAttackProtect**をホストする SQL Server を実行しているコンピューター上のレジストリ エントリ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースおよび実行しているコンピューターで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Windows Server を実行しています。2003 SP1 またはそれ以降。</span><span class="sxs-lookup"><span data-stu-id="115bd-114">Follow the instructions in this article to create the **SynAttackProtect** registry entry on computers running SQL Server that host [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases and on any computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that are running Windows Server 2003 SP1 or later.</span></span>  
  
## <a name="tuning-registry-settings-that-govern-the-level-of-denial-of-service-attack-protection"></a><span data-ttu-id="115bd-115">拒否の攻撃からサービスの保護のレベルを制御するレジストリ設定のチューニング</span><span class="sxs-lookup"><span data-stu-id="115bd-115">Tuning Registry Settings that Govern the Level of Denial of Service Attack Protection</span></span>  
 <span data-ttu-id="115bd-116">特定のシナリオでは、サービス拒否攻撃保護の管理がどの程度積極的にサービスの機能の拒否が適用されるを削減することがあります。</span><span class="sxs-lookup"><span data-stu-id="115bd-116">In certain scenarios you may want to maintain denial of service protection but reduce how aggressively the denial of service functionality is applied.</span></span> <span data-ttu-id="115bd-117">次の手順に従って保護機能をサービス拒否型の既定の動作を調整することができます。</span><span class="sxs-lookup"><span data-stu-id="115bd-117">It is possible to tune the default behavior of the denial of service protection feature by following these steps:</span></span>  
  
1.  <span data-ttu-id="115bd-118">いることを確認、 **SynAttackProtect**レジストリ エントリの REG_DWORD 値に設定されます**1** 」の説明に従って[ http://go.microsoft.com/fwlink/?LinkId=111477](http://go.microsoft.com/fwlink/?LinkId=111477)します。</span><span class="sxs-lookup"><span data-stu-id="115bd-118">Ensure that the **SynAttackProtect** registry entry is set to a REG_DWORD value of **1** as described at [http://go.microsoft.com/fwlink/?LinkId=111477](http://go.microsoft.com/fwlink/?LinkId=111477).</span></span>  
  
2.  <span data-ttu-id="115bd-119">構成、 **TcpMaxHalfOpen**レジストリ エントリで説明されている[ http://go.microsoft.com/fwlink/?LinkId=111478](http://go.microsoft.com/fwlink/?LinkId=111478)します。</span><span class="sxs-lookup"><span data-stu-id="115bd-119">Configure the **TcpMaxHalfOpen** registry entry as described at [http://go.microsoft.com/fwlink/?LinkId=111478](http://go.microsoft.com/fwlink/?LinkId=111478).</span></span>  
  
3.  <span data-ttu-id="115bd-120">構成、 **TcpMaxHalfOpenRetried**レジストリ エントリで説明されている[ http://go.microsoft.com/fwlink/?LinkId=111479](http://go.microsoft.com/fwlink/?LinkId=111479)します。</span><span class="sxs-lookup"><span data-stu-id="115bd-120">Configure the **TcpMaxHalfOpenRetried** registry entry as described at [http://go.microsoft.com/fwlink/?LinkId=111479](http://go.microsoft.com/fwlink/?LinkId=111479).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="115bd-121">参照</span><span class="sxs-lookup"><span data-stu-id="115bd-121">See Also</span></span>  
 [<span data-ttu-id="115bd-122">運用準備チェックリスト</span><span class="sxs-lookup"><span data-stu-id="115bd-122">Operational Readiness Checklists</span></span>](../technical-guides/operational-readiness-checklists.md)