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
ms.openlocfilehash: c1ea4d8356aa5812958e2ba9690dfbf8cc414dd5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336673"
---
# <a name="how-to-manually-purge-data-from-the-messagebox-database-in-a-test-environment"></a>テスト環境でメッセージ ボックス データベースから手動でデータを削除する方法
実行時に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発またはテスト環境では、メッセージ ボックス データベースに格納されているデータは通常ビジネス クリティカルな「ライブ」データであり削除される可能性があります。 これらのシナリオでは、メッセージ ボックス データベースからデータを消去するため「クイックとダーティ」メソッドがあります。 Bts_CleanupMsgbox ストアド プロシージャを使用してメッセージ ボックス データベースからデータを手動で削除するには、このトピックの手順に従います。  
  
> [!NOTE]
>  これらの手順は、テスト環境でのみ実行する必要があります。 運用環境で BizTalk メッセージ ボックス データベースを手動で削除することはサポートされていません。  
  
### <a name="to-stop-biztalk-services"></a>BizTalk サービスを停止するには  
  
1.  サービス コンソールから BizTalk サービスのすべてのインスタンスを停止します。  
  
2.  分離ホスト (たとえば、HTTP、SOAP、または WCF など) で、アダプターを実行する場合は、コマンド プロンプトから IISRESET を実行して IIS を再起動します。  
  
3.  実行している任意のカスタム分離アダプターをシャット ダウンします。  
  
### <a name="to-create-and-execute-the-btscleanupmsgbox-stored-procedure-using-sql-server-2008"></a>作成し、実行、bts_CleanupMsgbox ストアド プロシージャの SQL Server 2008 の使用  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。  
  
2. **SQL サーバーへの接続**ダイアログ ボックスで、SQL server と、適切な認証方式を選択し、順にクリックします**Connect**します。  
  
3. **利用可能なデータベース**ドロップダウン リストで、BizTalk メッセージ ボックス データベースを選択 (**BizTalkMsgBoxDB**既定)。  
  
4. をクリックして、**新しいクエリ**ツールバーのアイコン。  
  
5. 開く、 **msgbox_cleanup_logic.sql** SQL Server Management Studio からのファイル。 Msgbox_cleanup_logic.sql ファイルにある、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BizTalk Server コンピューターの schema \ ディレクトリです。  
  
6. をクリックして、**クエリの実行**bts_CleanupMsgbox を作成するスクリプトを実行するツールバーのアイコンをストアド プロシージャ。 Bts_CleanupMsgbox ストアド プロシージャは、dbo.bts_CleanupMsgbox としてストアド プロシージャの一覧で表示できます。  
  
7. をクリックして、**新しいクエリ**ツールバーのアイコン。  
  
8. 新しいクエリ ウィンドウには、次のコマンドを貼り付けます。  
  
   ```  
   exec bts_CleanupMsgbox  
   ```  
  
9. をクリックして、**クエリの実行**bts_CleanupMsgbox を実行するには、ツールバーのアイコンには、プロシージャが格納されています。  
  
   > [!IMPORTANT]
   >  実行している実稼働サーバーでの bts_CleanupMsgbox ストアド プロシージャを実行しない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 テスト環境でのみ、bts_CleanupMsgbox ストアド プロシージャを実行する必要があります。 実行、bts_CleanupMsgbox ストアド プロシージャ、運用環境ではサポートされません。  
  
10. 必要に応じて、BizTalk サービスを再起動します。  
  
## <a name="considerations-when-running-the-btscleanupmsgbox-stored-procedure"></a>ストアド プロシージャを bts_CleanupMsgbox の実行時の考慮事項  
 次の考慮事項は、実行、bts_CleanupMsgbox ストアド プロシージャに適用されます。  
  
1.  BizTalk データベース スキーマを更新するテスト システムに修正プログラムをインストールする場合、修正プログラムでは、このストアド プロシージャの空のバージョンで、bts_CleanupMsgbox ストアド プロシージャが上書きされます。 この場合、bts_CleanupMsgbox ストアド プロシージャを再作成には、このトピックで説明した手順を実行する必要があります。  
  
2.  新しいメッセージ ボックス データベースを作成する場合、bts_CleanupMsgbox ストアド プロシージャは空にして、bts_CleanupMsgbox ストアド プロシージャを再作成するには、このトピックで説明する手順を実行する必要があります。  
  
3.  Bts_CleanupMsgbox ストアド プロシージャの使用は**はサポートされていません**実稼働システムにします。 このストアド プロシージャは、メッセージ ボックス データベースにデータをすべて削除されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースからデータを削除する方法](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)