---
title: "バックアップおよび SQL Server ログインを復元する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 847c3a3d-0d97-415b-893e-4ba173085bae
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54fa6a51a27f82add8a96c613e36f5ed7ce88e87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-and-restore-sql-server-logins"></a>SQL Server ログインのバックアップ方法と復元方法
バックアップを作成し、BizTalk Server に関連付けられている SQL Server ログインを復元します。  
  
## <a name="biztalk-server-sql-server-security-logins"></a>BizTalk Server SQL Server セキュリティ ログイン  
 下記の SQL Server セキュリティ ログインは BizTalk Server と関連付けられています。 さらに、作成した BizTalk Server アプリケーションと関連付けられたログインが存在することもあります。 BizTalk Server データベースを新しいサーバーか SQL Server の新しいインスタンスに移動するときは、ログインをバックアップし復元する必要があります。  
  
-   BizTalk Application Users  
  
-   BizTalk 分離ホスト ユーザー  
  
-   BizTalk Server 管理者  
  
-   BizTalk Server オペレータ  
  
-   SSO 管理者  

## <a name="prerequisites"></a>前提条件  
メンバーである必要がある必要があります、**管理者**バックアップおよびログインを復元する場所の SQL Server のセキュリティ ロール。  
  
## <a name="back-up-a-login-using-a-script"></a>スクリプトを使用してログインをバックアップします。  
  
1.  開いている**SQL Server Management Studio**です。  
  
2.  展開**セキュリティ**の一覧を展開および**ログイン**です。  
  
3.  では、バックアップ スクリプトを作成し、選択するログインを右クリックして**ログインをスクリプト**です。  
  
4.  選択**Create**のいずれかを選択し、**新しいクエリ エディター ウィンドウ**、**ファイル**、または**クリップボード**スクリプトの宛先を選択します。 通常、変換先は、ファイルが、 **.sql**拡張機能です。  
  
5.  スクリプト化するログインごとに手順 3. 以降を繰り返します。 スクリプト化が必要なログインを決定するには、BizTalk Server 関連ログインの一覧を参照してください。  
  
## <a name="restore-a-login-from-a-script"></a>スクリプトからログインを復元します。  
  
1.  開いている**SQL Server Management Studio**です。  
  
2.  **ファイル**] メニューの [**開く**をスクリプト化されたログインを含むファイルです。  
  
3.  ログインを作成するスクリプトを実行します。