---
title: BizTalk Server ホスト インスタンスを SQL Server フェールオーバー時の動作 |Microsoft ドキュメント
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
ms.openlocfilehash: f244ce0fe00fe05f73db5f43ec867254b7a61fb7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231250"
---
# <a name="behavior-of-biztalk-server-host-instances-during-sql-server-failover"></a>SQL Server フェールオーバー時の BizTalk Server ホスト インスタンスの動作
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のクラスター化インスタンスに格納されている [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データベースは、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] のクラスター化インスタンスにフェールオーバーが発生した場合、一時的に使用できなくなります。 このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースが使用できなくなった場合の、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に関連するホスト インスタンスの動作について説明します。  
  
## <a name="behavior-of-in-process-host-instances-during-sql-server-failover"></a>SQL Server フェールオーバー時のインプロセス ホスト インスタンスの動作  
 場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースが使用できない状態のプロセスのインスタンス、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストされるリサイクルされるまでにへの接続、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を復元します。 接続を 1 回、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースが復元されたら、そのドキュメントの処理が正常に再開します。  
  
## <a name="behavior-of-isolated-host-instances-during-sql-server-failover"></a>SQL Server フェールオーバー時の分離ホスト インスタンスの動作  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースが使用できなくなった場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ホストの分離インスタンスは一時停止し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーション ログに次のようなエラーが生成されます。  
  
```  
All receive locations are being temporarily disabled because either   
the MessageBox or Configuration database is not available.   
When these databases become available, the receive locations will be automatically enabled.  
```  
  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データベースへの接続が復旧すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーション ログに次のような情報メッセージが書き込まれ、ドキュメント処理は通常どおり再開されます。  
  
```  
All receive locations are being enabled because both the MessageBox and Configuration databases are back online.  
```  
  
## <a name="see-also"></a>参照  
 [ホスト](../core/hosts.md)