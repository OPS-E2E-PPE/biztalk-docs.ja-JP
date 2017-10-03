---
title: "BizTalk Server ホスト インスタンスを SQL Server フェールオーバー時の動作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5642417-d27f-4539-a369-5fa11bec4a4f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f244ce0fe00fe05f73db5f43ec867254b7a61fb7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="behavior-of-biztalk-server-host-instances-during-sql-server-failover"></a><span data-ttu-id="f89f2-102">SQL Server フェールオーバー時の BizTalk Server ホスト インスタンスの動作</span><span class="sxs-lookup"><span data-stu-id="f89f2-102">Behavior of BizTalk Server Host Instances during SQL Server Failover</span></span>
<span data-ttu-id="f89f2-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のクラスター化インスタンスに格納されている [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データベースは、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] のクラスター化インスタンスにフェールオーバーが発生した場合、一時的に使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f89f2-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases housed on a clustered instance of Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are temporarily unavailable if the clustered instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] experiences a failover.</span></span> <span data-ttu-id="f89f2-104">このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースが使用できなくなった場合の、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に関連するホスト インスタンスの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="f89f2-104">This section documents the behavior of the host instances associated with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] when the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are unavailable.</span></span>  
  
## <a name="behavior-of-in-process-host-instances-during-sql-server-failover"></a><span data-ttu-id="f89f2-105">SQL Server フェールオーバー時のインプロセス ホスト インスタンスの動作</span><span class="sxs-lookup"><span data-stu-id="f89f2-105">Behavior of In-Process Host Instances during SQL Server Failover</span></span>  
 <span data-ttu-id="f89f2-106">場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースが使用できない状態のプロセスのインスタンス、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストされるリサイクルされるまでにへの接続、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を復元します。</span><span class="sxs-lookup"><span data-stu-id="f89f2-106">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are unavailable, then an in-process instance of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host will be recycled until the connection to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] is restored.</span></span> <span data-ttu-id="f89f2-107">接続を 1 回、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースが復元されたら、そのドキュメントの処理が正常に再開します。</span><span class="sxs-lookup"><span data-stu-id="f89f2-107">Once the connection to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases is restored, document processing resumes normally.</span></span>  
  
## <a name="behavior-of-isolated-host-instances-during-sql-server-failover"></a><span data-ttu-id="f89f2-108">SQL Server フェールオーバー時の分離ホスト インスタンスの動作</span><span class="sxs-lookup"><span data-stu-id="f89f2-108">Behavior of Isolated Host Instances During SQL Server Failover</span></span>  
 <span data-ttu-id="f89f2-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースが使用できなくなった場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ホストの分離インスタンスは一時停止し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーション ログに次のようなエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f89f2-109">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are unavailable, then an isolated instance of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host will pause and an error similar to the following will be generated in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application log:</span></span>  
  
```  
All receive locations are being temporarily disabled because either   
the MessageBox or Configuration database is not available.   
When these databases become available, the receive locations will be automatically enabled.  
```  
  
 <span data-ttu-id="f89f2-110">[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データベースへの接続が復旧すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーション ログに次のような情報メッセージが書き込まれ、ドキュメント処理は通常どおり再開されます。</span><span class="sxs-lookup"><span data-stu-id="f89f2-110">Once the connection to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases is restored an informational message similar to the following is written to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application log and document processing resumes normally:</span></span>  
  
```  
All receive locations are being enabled because both the MessageBox and Configuration databases are back online.  
```  
  
## <a name="see-also"></a><span data-ttu-id="f89f2-111">参照</span><span class="sxs-lookup"><span data-stu-id="f89f2-111">See Also</span></span>  
 [<span data-ttu-id="f89f2-112">ホスト</span><span class="sxs-lookup"><span data-stu-id="f89f2-112">Hosts</span></span>](../core/hosts.md)