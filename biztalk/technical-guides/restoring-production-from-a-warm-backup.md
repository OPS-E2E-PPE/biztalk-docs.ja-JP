---
title: "ウォーム バックアップから運用環境の復元 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2bda14b8-b3cc-4a5e-a353-fca5885fd594
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e590b4eccb6ee946a915ff1f3a0265bbfe977e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="restoring-production-from-a-warm-backup"></a>ウォーム バックアップから運用環境の復元
ソース システムの信頼性の低いになると、そのソースに、ターゲット データベースを復元する可能性があります。 データベースを復元するターゲットからソースへの次の手順を実行します。  
  
### <a name="to-restore-the-databases-from-the-destination-to-the-source-follow-these-steps"></a>ターゲットからソースへのデータベースを復元するには、以下の手順  
  
1.  ソース (運用環境) 上のすべてのバックアップ ジョブを無効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。  
  
2.  すべての復元ジョブが移行先の災害復旧 (DR) で完了するまで待機[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。  
  
3.  移行先 (DR) 上のすべての復元ジョブを無効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。  
  
4.  STOPATMARK 先 (DR) にあるすべてのデータベースを復元[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。  
  
5.  すべて停止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]すべての BizTalk server 上のサービスです。  
  
6.  すべてを削除[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-ソース (運用環境) 上のデータベースの関連[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。  
  
7.  (完全) すべてのデータベースをバックアップ先 (DR)[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。  
  
8.  すべての復元 (完全)[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース バックアップ手順 7. で、ソース (運用)[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。  
  
9. マスター シークレット サーバーを含むすべての BizTalk server を再起動します。  
  
10. すべてを削除[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-移行先 (DR) 上のデータベースの関連[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。  
  
11. ソースのバックアップ ジョブを有効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。  
  
12. 宛先 (DR) の復元ジョブを有効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。  
  
## <a name="see-also"></a>参照  
 [バックアップおよび Restore2 に関する詳細情報](../technical-guides/advanced-information-about-backup-and-restore2.md)