---
title: ウォーム バックアップから運用環境の復元 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bda14b8-b3cc-4a5e-a353-fca5885fd594
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43d3c2d771d26ffef720f256945e157b335141ed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291281"
---
# <a name="restoring-production-from-a-warm-backup"></a>ウォーム バックアップから運用環境の復元
ソース システムには、信頼性の低いになると、ソース、ターゲット データベースを復元すること勧めします。 ソース コピー先からデータベースを復元する次の手順を実行します。  
  
### <a name="to-restore-the-databases-from-the-destination-to-the-source-follow-these-steps"></a>ソースに、ターゲット データベースを復元するには、以下の手順  
  
1. ソース (運用) 上のすべてのバックアップ ジョブを無効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。  
  
2. すべての復元ジョブが移行先のディザスター リカバリー (DR) を完了するまで待機[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。  
  
3. 宛先 (DR) のすべての復元ジョブを無効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。  
  
4. STOPATMARK (DR) の接続先であるすべてのデータベースを復元[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。  
  
5. すべて停止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]すべての BizTalk server 上のサービスです。  
  
6. すべて削除[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-ソース (運用) 上のデータベースに関連[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。  
  
7. 変換先 (DR) 上のすべてのデータベースの (完全) をバックアップ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。  
  
8. すべての復元 (完全)[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース バックアップ手順 7. で、ソース (運用)[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。  
  
9. マスター シークレット サーバーを含むすべての BizTalk server を再起動します。  
  
10. すべて削除[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-変換先 (DR) 上のデータベースに関連[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。  
  
11. ソースのバックアップ ジョブを有効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。  
  
12. 宛先 (DR) の復元ジョブを有効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。  
  
## <a name="see-also"></a>参照  
 [バックアップおよび Restore2 に関する詳細情報](../technical-guides/advanced-information-about-backup-and-restore2.md)