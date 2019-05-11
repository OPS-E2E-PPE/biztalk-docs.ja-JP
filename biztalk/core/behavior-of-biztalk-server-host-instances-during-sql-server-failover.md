---
title: BizTalk Server ホスト インスタンスを SQL Server フェールオーバー時の動作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5642417-d27f-4539-a369-5fa11bec4a4f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4cd4f60d37ecf994b258991bb1b0947c2f28d7bc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358222"
---
# <a name="behavior-of-biztalk-server-host-instances-during-sql-server-failover"></a><span data-ttu-id="b3280-102">BizTalk Server ホスト インスタンスを SQL Server フェールオーバー時の動作</span><span class="sxs-lookup"><span data-stu-id="b3280-102">Behavior of BizTalk Server Host Instances during SQL Server Failover</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="b3280-103">Microsoft のクラスター化インスタンスに格納されているデータベース[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]が一時的に使用しない場合のクラスター化されたインスタンス[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]フェールオーバーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b3280-103">databases housed on a clustered instance of Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are temporarily unavailable if the clustered instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] experiences a failover.</span></span> <span data-ttu-id="b3280-104">このセクションに関連付けられているホスト インスタンスの動作について説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ときに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースは利用できません。</span><span class="sxs-lookup"><span data-stu-id="b3280-104">This section documents the behavior of the host instances associated with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] when the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are unavailable.</span></span>  
  
## <a name="behavior-of-in-process-host-instances-during-sql-server-failover"></a><span data-ttu-id="b3280-105">SQL Server フェールオーバー時のインプロセス ホスト インスタンスの動作</span><span class="sxs-lookup"><span data-stu-id="b3280-105">Behavior of In-Process Host Instances during SQL Server Failover</span></span>  
 <span data-ttu-id="b3280-106">場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースが使用できない場合のインプロセス インスタンス、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]への接続までのホストが再利用されます、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]が復元されます。</span><span class="sxs-lookup"><span data-stu-id="b3280-106">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are unavailable, then an in-process instance of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host will be recycled until the connection to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] is restored.</span></span> <span data-ttu-id="b3280-107">接続を 1 回、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースの復元、ドキュメントの処理が正常に再開します。</span><span class="sxs-lookup"><span data-stu-id="b3280-107">Once the connection to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases is restored, document processing resumes normally.</span></span>  
  
## <a name="behavior-of-isolated-host-instances-during-sql-server-failover"></a><span data-ttu-id="b3280-108">SQL Server フェールオーバー時の分離ホスト インスタンスの動作</span><span class="sxs-lookup"><span data-stu-id="b3280-108">Behavior of Isolated Host Instances During SQL Server Failover</span></span>  
 <span data-ttu-id="b3280-109">場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースが使用できない場合は、分離されたインスタンス、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストは一時停止しで、次のようなエラーが生成されます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション ログ。</span><span class="sxs-lookup"><span data-stu-id="b3280-109">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are unavailable, then an isolated instance of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host will pause and an error similar to the following will be generated in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application log:</span></span>  
  
```  
All receive locations are being temporarily disabled because either   
the MessageBox or Configuration database is not available.   
When these databases become available, the receive locations will be automatically enabled.  
```  
  
 <span data-ttu-id="b3280-110">接続を 1 回、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースの復元に、次のような情報メッセージが書き込まれます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション ログや再開を正常に処理ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="b3280-110">Once the connection to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases is restored an informational message similar to the following is written to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application log and document processing resumes normally:</span></span>  
  
```  
All receive locations are being enabled because both the MessageBox and Configuration databases are back online.  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3280-111">参照</span><span class="sxs-lookup"><span data-stu-id="b3280-111">See Also</span></span>  
 [<span data-ttu-id="b3280-112">ホスト</span><span class="sxs-lookup"><span data-stu-id="b3280-112">Hosts</span></span>](../core/hosts.md)