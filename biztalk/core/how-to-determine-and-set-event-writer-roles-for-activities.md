---
title: 決定し、アクティビティ イベント ライター ロールを設定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73bfe8ff-167a-4bf0-ab87-3926290d52d8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc3ff2fcc8ed4397db8d1eb8d5906cebd5c26af1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385258"
---
# <a name="how-to-determine-and-set-event-writer-roles-for-activities"></a>アクティビティのイベント ライター ロールを確認および設定する方法
BAM は、アクティビティにイベントを書き込むときに、2 つのセキュリティ モードを提供します。 個々 のアクティビティのイベントの書き込みアクセス許可を付与することができますか、展開済みのすべてのアクティビティのイベントの書き込みアクセス許可を付与することができます。  
  
 アクティビティ レベルのセキュリティは、BAM 定義を展開するときに作成されるアクティビティ イベント ライター ロールによって提供されます。 たとえば、CreditCard という名前のアクティビティの定義を展開する場合、BAM は bam_CreditCard_EventWriter という名前のイベント ライター ロールを作成します。 このロールは、アクティビティのイベントの書き込みアクセス許可を持っています。 ユーザー アクティビティのイベントの書き込みアクセス許可を付与するには、ロールにユーザーを追加します。  
  
 または、スーパー ロール BAM_EVENT_WRITER を持つすべてのアクティビティへの書き込みアクセス許可を追加することで、すべてのアクティビティに eve2nts を記述するユーザー権限を付与することができます。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、次の操作が必要です。  
  
-   アクティビティが展開されている BAMPrimaryImportDb への接続。  
  
-   データベースの DBO アクセスを許可します。  
  
### <a name="to-add-a-user-to-an-event-writer-role"></a>イベント ライター ロールにユーザーを追加するには  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008**、順にクリックします**SQL Server Management Studio**します。  
  
2.  **SQL サーバーへの接続**ダイアログ ボックスで、SQL Server と、適切な認証方式を選択し、順にクリックします**Connect**します。  
  
3.  **オブジェクト エクスプ ローラー**ペイン展開**データベース**、BAM プライマリ インポート データベースを選択します。  
  
4.  をクリックして、**新しいクエリ**ツールバーのアイコン。  
  
5.  次のコマンドをコピーし、クエリ ウィンドウに貼り付けます。 ドメイン名、ユーザー名、およびアクティビティ名のプレース ホルダーを適切な値に置き換えます。  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'bam_<activity name>_EventWriter', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  ロール名の大文字と小文字は区別されます。 アクティビティ名は大文字でも、アクティビティを展開するときに使用する場合は、一致する必要があります。  
  
6.  をクリックして、 **Execute**アイコンがツールバーにコマンドを実行する F5 キーを押します。  
  
### <a name="to-add-a-user-to-an-event-writer-super-role"></a>イベント ライター スーパー ロールにユーザーを追加するには  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008**、順にクリックします**SQL Server Management Studio**します。  
  
2.  **SQL サーバーへの接続**ダイアログ ボックスで、SQL Server と、適切な認証方式を選択し、順にクリックします**Connect**します。  
  
3.  **オブジェクト エクスプ ローラー**ペイン展開**データベース**、BAM プライマリ インポート データベースを選択します。  
  
4.  をクリックして、**新しいクエリ**ツールバーのアイコン。  
  
5.  次のコマンドをコピーし、クエリ ウィンドウに貼り付けます。 ユーザー名とドメインの名前を適切な値に置き換えます。  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'BAM_EVENT_WRITER', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  ロールの名前は大文字小文字を区別します。 指定されたイベント ライター ロールを指定する必要があります。  
  
6.  をクリックして、 **Execute**アイコンがツールバーにコマンドを実行する F5 キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM セキュリティの管理](../core/managing-bam-security.md)