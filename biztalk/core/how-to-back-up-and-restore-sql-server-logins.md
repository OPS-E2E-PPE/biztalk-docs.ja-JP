---
title: バックアップおよび SQL Server ログインを復元する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 847c3a3d-0d97-415b-893e-4ba173085bae
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87634ca9e9f8bbd3cc7508ce0bcfe54e5154ca0f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387109"
---
# <a name="how-to-back-up-and-restore-sql-server-logins"></a>バックアップおよび SQL Server ログインを復元する方法
バックアップし、BizTalk Server に関連付けられている SQL Server ログインを復元します。  
  
## <a name="biztalk-server-sql-server-security-logins"></a>BizTalk Server SQL Server セキュリティ ログイン  
 以下に示す SQL Server セキュリティ ログインは、BizTalk Server に関連付けられます。 追加のログインを作成した BizTalk Server アプリケーションに関連付けられているがあります。 ログインをバックアップし、新しいサーバーまたは SQL Server の新しいインスタンスを BizTalk Server データベースを移動する場合、それらを復元する必要があります。  
  
-   BizTalk Application Users  
  
-   BizTalk 分離ホスト ユーザー  
  
-   BizTalk Server 管理者  
  
-   BizTalk Server オペレータ  
  
-   SSO 管理者  

## <a name="prerequisites"></a>前提条件  
メンバーである必要がありますが、**管理者**バックアップおよびログインを復元する場所の SQL Server のセキュリティ ロール。  
  
## <a name="back-up-a-login-using-a-script"></a>バックアップ スクリプトを使用してログインします。  
  
1.  **SQL Server Management Studio** を開きます。  
  
2.  展開**セキュリティ**の一覧を展開および**ログイン**します。  
  
3.  バックアップ スクリプトを作成し、選択するログインを右クリックして**ログインをスクリプト**します。  
  
4.  選択**Create**、しのいずれかを選択します**新しいクエリ エディター ウィンドウ**、**ファイル**、または**クリップボード**をスクリプトの宛先を選択します。 コピー先のファイルは、通常、 **.sql**拡張機能。  
  
5.  スクリプトを作成ログインごとに手順 3 からこの手順を繰り返します。 一覧を参照してください。 BizTalk Server 関連ログイン スクリプトを作成する必要がありますを決定するログイン。  
  
## <a name="restore-a-login-from-a-script"></a>スクリプトからログインを復元します。  
  
1.  **SQL Server Management Studio** を開きます。  
  
2.  **ファイル**] メニューの [**オープン**スクリプト化されたログインを含むファイル。  
  
3.  ログインを作成するスクリプトを実行します。