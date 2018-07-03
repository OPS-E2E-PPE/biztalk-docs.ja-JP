---
title: テスト環境でメッセージ ボックス データベースからデータを手動で削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 398991a9-344a-487a-a817-dfc97d48ebe6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5282ad864e5c2d4f47b541b59d608087f090f935
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979735"
---
# <a name="how-to-manually-purge-data-from-the-messagebox-database-in-a-test-environment"></a>テスト環境でメッセージ ボックス データベースから手動でデータを削除する方法
開発環境またはテスト環境で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行する場合、メッセージ ボックス データベースに格納されているデータは、通常、ビジネスで重要な "実際の" データではないので、削除することができます。 このようなシナリオでは、メッセージ ボックス データベースからデータを削除するための簡単な方法が必要になる場合があります。 bts_CleanupMsgbox ストアド プロシージャを使用して、メッセージ ボックス データベースから手動でデータを削除するには、このトピックの手順に従ってください。  
  
> [!NOTE]
>  以下の手順は、テスト環境でのみ実行してください。 運用環境で BizTalk メッセージ ボックス データベースのデータを手動で削除することはサポートされていません。  
  
### <a name="to-stop-biztalk-services"></a>BizTalk サービスを停止するには  
  
1.  サービス コンソールから BizTalk サービスのすべてのインスタンスを停止します。  
  
2.  分離ホストでアダプターを実行している場合 (HTTP、SOAP、WCF など) は、コマンド プロンプトから IISRESET を実行して IIS を再起動します。  
  
3.  実行中のカスタム分離アダプターをすべてシャットダウンします。  
  
### <a name="to-create-and-execute-the-btscleanupmsgbox-stored-procedure-using-sql-server-2008"></a>SQL Server 2008 を使用して bts_CleanupMsgbox ストアド プロシージャを作成および実行するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。  
  
2. **SQL サーバーへの接続**ダイアログ ボックスで、SQL server と、適切な認証方式を選択し、順にクリックします**Connect**します。  
  
3. **利用可能なデータベース**ドロップダウン リストで、BizTalk メッセージ ボックス データベースを選択 (**BizTalkMsgBoxDB**既定)。  
  
4. をクリックして、**新しいクエリ**ツールバーのアイコン。  
  
5. 開く、 **msgbox_cleanup_logic.sql** SQL Server Management Studio からのファイル。 msgbox_cleanup_logic.sql ファイルは、BizTalk Server コンピューターの [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\ ディレクトリにあります。  
  
6. をクリックして、**クエリの実行**bts_CleanupMsgbox を作成するスクリプトを実行するツールバーのアイコンをストアド プロシージャ。 これで、bts_CleanupMsgbox ストアド プロシージャが、ストアド プロシージャの一覧に dbo.bts_CleanupMsgbox として表示されるようになります。  
  
7. をクリックして、**新しいクエリ**ツールバーのアイコン。  
  
8. 次のコマンドを新しいクエリ ウィンドウに貼り付けます。  
  
   ```  
   exec bts_CleanupMsgbox  
   ```  
  
9. をクリックして、**クエリの実行**bts_CleanupMsgbox を実行するには、ツールバーのアイコンには、プロシージャが格納されています。  
  
   > [!IMPORTANT]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行している運用サーバーでは、bts_CleanupMsgbox ストアド プロシージャを実行しないでください。 bts_CleanupMsgbox ストアド プロシージャは、テスト環境でのみ実行してください。 運用環境での bts_CleanupMsgbox ストアド プロシージャの実行はサポートされていません。  
  
10. 必要に応じて、BizTalk サービスを再開します。  
  
## <a name="considerations-when-running-the-btscleanupmsgbox-stored-procedure"></a>bts_CleanupMsgbox ストアド プロシージャを実行する際の考慮事項  
 bts_CleanupMsgbox ストアド プロシージャを実行する際の考慮事項は、次のとおりです。  
  
1.  BizTalk データベース スキーマを更新する修正プログラムをテスト システムにインストールする場合、修正プログラムによって、bts_CleanupMsgbox ストアド プロシージャに、このストアド プロシージャの空のバージョンが上書きされることがあります。 この場合、このトピックで説明した手順に従って、bts_CleanupMsgbox ストアド プロシージャを再作成する必要があります。  
  
2.  新しいメッセージ ボックス データベースを作成した場合、bts_CleanupMsgbox ストアド プロシージャは空であり、このトピックで説明した手順に従って、bts_CleanupMsgbox ストアド プロシージャを再作成する必要があります。  
  
3.  Bts_CleanupMsgbox ストアド プロシージャの使用は**はサポートされていません**実稼働システムにします。 このストアド プロシージャは、メッセージ ボックス データベース内のすべてのデータを削除します。  
  
## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースからデータを削除する方法](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)