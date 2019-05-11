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
# <a name="behavior-of-biztalk-server-host-instances-during-sql-server-failover"></a>BizTalk Server ホスト インスタンスを SQL Server フェールオーバー時の動作
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Microsoft のクラスター化インスタンスに格納されているデータベース[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]が一時的に使用しない場合のクラスター化されたインスタンス[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]フェールオーバーが発生しました。 このセクションに関連付けられているホスト インスタンスの動作について説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ときに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースは利用できません。  
  
## <a name="behavior-of-in-process-host-instances-during-sql-server-failover"></a>SQL Server フェールオーバー時のインプロセス ホスト インスタンスの動作  
 場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースが使用できない場合のインプロセス インスタンス、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]への接続までのホストが再利用されます、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]が復元されます。 接続を 1 回、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースの復元、ドキュメントの処理が正常に再開します。  
  
## <a name="behavior-of-isolated-host-instances-during-sql-server-failover"></a>SQL Server フェールオーバー時の分離ホスト インスタンスの動作  
 場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースが使用できない場合は、分離されたインスタンス、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストは一時停止しで、次のようなエラーが生成されます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション ログ。  
  
```  
All receive locations are being temporarily disabled because either   
the MessageBox or Configuration database is not available.   
When these databases become available, the receive locations will be automatically enabled.  
```  
  
 接続を 1 回、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースの復元に、次のような情報メッセージが書き込まれます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション ログや再開を正常に処理ドキュメント。  
  
```  
All receive locations are being enabled because both the MessageBox and Configuration databases are back online.  
```  
  
## <a name="see-also"></a>参照  
 [ホスト](../core/hosts.md)