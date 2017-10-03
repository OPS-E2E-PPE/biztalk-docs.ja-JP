---
title: "SQL アダプタで Windows 認証を使用して SQL Server への接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45c54b2a-e056-496f-9f10-f19b6a3ca1a6
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db7d0cbe07155d09085091d995b524b3058c0bf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-sql-server-using-windows-authentication-with-the-sql-adapter"></a>SQL アダプタで Windows 認証を使用して SQL Server への接続します。
[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] SQL サーバーとの接続を確立するために Windows 認証を使用するアダプターのクライアントを有効にします。 Windows 認証を使用するには、アダプターのクライアントは、空のユーザー名とパスワードを入力してください。 

Visual Studio 内で Windows 認証を使用して SQL Server に接続するを参照してください。 [アダプター サービスのアドインを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)です。  
  
 SQL Server への接続に Windows 認証を使用するアダプターのクライアントを有効にするには、SQL Server を実行しているコンピューター上のユーザーの Windows 認証を有効にします。  

> [!TIP]
> 場合は、SQL Server では、SQL Server Management Studio がインストールされていない、[ダウンロード SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)、し、インストールします。 
 
## <a name="add-the-user-in-sql-server"></a>SQL Server でユーザーを追加します。  
  
1.  SQL Server Management Studio を開きます。 **サーバーへの接続**を選択**データベース エンジン**、入力、SQL**サーバー名**サーバーに接続する管理者の資格情報を入力します。  

    **[接続]**を選択します。
  
2.  **オブジェクト エクスプ ローラー**、SQL Server を展開し、**セキュリティ**を右クリックして**ログイン**、し、**新しいログイン**です。  
  
3.  **ログイン名**で Windows ユーザー名を入力、`domain\username`形式です。  

    > [!NOTE]
    >* BizTalk で、このアダプターを使用している場合は、ホスト インスタンス アカウントの id は入力すると、ログイン名です。  
    >
    >* .NET コードでこのアダプターを使用している場合は、そのプロセスの id は入力すると、ログイン名です。
  
4.  選択**ユーザー マッピング**(左側のウィンドウ)。 ユーザーに関連付けるデータベースを選択します。 一般的な BizTalk ユーザーは、次のデータベースに関連付けする必要があります。 

* BizTalkDTADb
* BizTalkMgmtDb
* BizTalkMsgBoxDb
* BTAHL7
* SSODB

5. **データベース ロールのメンバーシップ**ボックスで、 **db_owner**すべての BizTalk データベース。  

    > [!NOTE]
    > [サーバーと SQL server データベース ロール](https://msdn.microsoft.com/library/bb669065.aspx)の役割に対する良い情報を提供します。 
  
6.  **[OK]** を選択して変更を保存します。
  
 ユーザーが接続し、SQL Server を使用する認証ユーザーを追加した後、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、空のユーザー名とパスワードを使用してログを記録します。  



## <a name="see-also"></a>参照  
 [SQL Server への接続を作成します。](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)