---
title: "判断し、アクティビティ イベント ライター ロールを設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73bfe8ff-167a-4bf0-ab87-3926290d52d8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc9fa663d395fc36205e137da374f17cb9470521
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-determine-and-set-event-writer-roles-for-activities"></a>アクティビティのイベント ライター ロールを確認および設定する方法
アクティビティにイベントを書き込む場合、BAM は 2 つのセキュリティ モードを提供します。 個別のアクティビティへのイベントの書き込みアクセス許可を与えることも、展開されているすべてのアクティビティへのイベントの書き込みアクセス許可を与えることもできます。  
  
 アクティビティ レベルのセキュリティは、BAM 定義を展開するときに作成されるアクティビティ イベント ライター ロールで提供されます。 たとえば、CreditCard という名前のアクティビティの定義を展開すると、BAM は、bam_CreditCard_EventWriter という名前のイベント ライター ロールを作成します。 このロールは、アクティビティにイベントを書き込むためのアクセス許可を持っています。 アクティビティにイベントを書き込むためのアクセス許可をユーザーに与えるには、ユーザーをこのロールに追加します。  
  
 代わりに、スーパー ロール BAM_EVENT_WRITER にすべてのアクティビティへの書き込みアクセス許可を持つに追加して、すべての活動に eve2nts を書き込み権限をユーザーに付与できます。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、以下の条件が揃っている必要があります。  
  
-   アクティビティが展開されている BAMPrimaryImportDb への接続  
  
-   データベースへの DBO アクセス許可  
  
### <a name="to-add-a-user-to-an-event-writer-role"></a>イベント ライター ロールにユーザーを追加するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008**、順にクリック**SQL Server Management Studio**です。  
  
2.  **SQL Server への接続**ダイアログ ボックスでは、SQL Server および適切な認証方法を選択し、をクリックして**接続**です。  
  
3.  **オブジェクト エクスプ ローラー**ペインを展開**データベース**、BAM プライマリ インポート データベースを選択します。  
  
4.  クリックして、**新しいクエリ**ツールバーのアイコン。  
  
5.  次のコマンドをコピーし、クエリ ウィンドウに貼り付けます。 ドメイン名、ユーザー名、およびアクティビティ名のプレースホルダーを適切な値で置き換えます。  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'bam_<activity name>_EventWriter', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  ロール名の大文字と小文字は区別されます。 アクティビティ名も大文字と小文字が区別されます。つまり、アクティビティ名は、アクティビティを展開するときに使用した大文字小文字と一致する必要があります。  
  
6.  クリックして、 **Execute**アイコン、ツールバーまたはコマンドを実行する場合は F5 キーを押します。  
  
### <a name="to-add-a-user-to-an-event-writer-super-role"></a>イベント ライター スーパー ロールにユーザーを追加するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008**、順にクリック**SQL Server Management Studio**です。  
  
2.  **SQL Server への接続**ダイアログ ボックスでは、SQL Server および適切な認証方法を選択し、をクリックして**接続**です。  
  
3.  **オブジェクト エクスプ ローラー**ペインを展開**データベース**、BAM プライマリ インポート データベースを選択します。  
  
4.  クリックして、**新しいクエリ**ツールバーのアイコン。  
  
5.  次のコマンドをコピーし、クエリ ウィンドウに貼り付けます。 ドメイン名およびユーザー名を適切な値で置き換えます。  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'BAM_EVENT_WRITER', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  ロールの名前は大文字小文字を区別します。 イベント ライター ロールは指定されているとおりに指定する必要があります。  
  
6.  クリックして、 **Execute**アイコン、ツールバーまたはコマンドを実行する場合は F5 キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM セキュリティの管理](../core/managing-bam-security.md)