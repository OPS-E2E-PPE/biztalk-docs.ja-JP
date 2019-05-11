---
title: SQL アダプターを使用した Windows 認証を使用して SQL Server への接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45c54b2a-e056-496f-9f10-f19b6a3ca1a6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6a96137243612042c8283ec5e5d15ced9d1d83b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369903"
---
# <a name="connect-to-sql-server-using-windows-authentication-with-the-sql-adapter"></a>SQL アダプターを使用した Windows 認証を使用して SQL Server に接続します。
[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]アダプター クライアントが SQL Server との接続を確立するために Windows 認証を使用できるようにします。 Windows 認証を使用するには、アダプター クライアントは、空のユーザー名とパスワードを入力する必要があります。 

Visual Studio 内で Windows 認証を使用して SQL Server に接続するを参照してください。 [Consume Adapter Service アドインを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)します。  
  
 SQL Server への接続に Windows 認証を使用するアダプターのクライアントを有効にするのには、SQL Server を実行しているコンピューター上のユーザーの Windows 認証を有効にします。  

> [!TIP]
> 場合は、SQL Server では、SQL Server Management Studio がインストールされていない、[ダウンロード SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)、し、インストールします。 
 
## <a name="add-the-user-in-sql-server"></a>SQL Server でユーザーを追加します。  
  
1.  SQL Server Management Studio を開きます。 **サーバーへの接続**を選択します**データベース エンジン**、入力、SQL**サーバー名**、し、サーバーに接続する管理者の資格情報を入力します。  

    **[接続]** を選択します。
  
2.  **オブジェクト エクスプ ローラー**、SQL Server を展開し、**セキュリティ**、右クリック**ログイン**、し、**新しいログイン**します。  
  
3.  **ログイン名**、Windows ユーザー名を入力、`domain\username`形式。  

    > [!NOTE]
    >* を BizTalk でこのアダプターを使用する場合、ログイン名を入力すると、は、ホスト インスタンス アカウントの id です。  
    >
    >* を .NET コードでこのアダプターを使用する場合、ログイン名を入力すると、はそのプロセスの id です。
  
4.  選択**ユーザー マッピング**(左側のウィンドウ)。 ユーザーに関連付けるデータベースを選択します。 一般的な BizTalk ユーザーは、次のデータベースを関連付ける必要があります。 

* BizTalkDTADb
* BizTalkMgmtDb
* BizTalkMsgBoxDb
* BTAHL7
* SSODB

5. **データベース ロールのメンバーシップ**ボックスで、 **db_owner**のすべての BizTalk データベース。  

    > [!NOTE]
    > [サーバーと SQL server データベース ロール](https://msdn.microsoft.com/library/bb669065.aspx)の役割に対する良い情報を提供します。 
  
6. **[OK]** を選択して変更を保存します。
  
   ユーザーを接続して SQL Server を使用する認証にユーザーを追加した後、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、空のユーザー名とパスワードを使用してログを記録します。  



## <a name="see-also"></a>参照  
 [SQL Server への接続を作成する](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)