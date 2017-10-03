---
title: "ホストの削除 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3df8719-27cb-4010-82e3-68226ab74b17
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fd5f54fa84ddb521444cfb3f2351a8062c4de00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="delete-a-host"></a>ホストを削除します。
ホストは、以下の状況でのみ削除できます。  
  
-   既定のホストではない。  
  
-   ホスト追跡を行う唯一のホストではない。  
  
-   アダプター ハンドラーをホストしてない。  
  
-   参加しているオーケストレーションがない。  
  
-   開始されているホスト インスタンスがない。  
  
-   ホストがクラスター化されていない。  
  
 ホストの詳細については、次を参照してください。[ホスト](../core/hosts.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 ホストの作成、ホスト プロパティの変更、およびホストの削除には、次のユーザー権利が必要です。  
  
-   BizTalk Server 管理者グループのメンバーである必要があります。  
  
-   SQL Server には次の権利が必要です。  
  
    -   BizTalk 追跡データベース (BizTalk DTADb)、メッセージ ボックス データベース (BizTalkMsgBoxDb)、および BAM プライマリ インポート データベース (BAMPrimaryImport) では、SQL Server の管理者であるか、SQL Server データベース ロールの db_owner または db_securityadmin のメンバーである必要があります。  
  
    -   メッセージ ボックス データベースが存在するすべてのコンピューターの sysadmin SQL Server ロールのメンバーであるか、すべてのメッセージ ボックス データベースの db_owner または db_ddladmin SQL Server ロールのメンバーである必要があります。  
  
## <a name="steps"></a>手順 
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)][BizTalk グループ]、をクリックして**プラットフォームの設定**、クリックして**ホスト**です。  
  
3.  詳細ウィンドウで、削除、およびをクリックするホストを右クリックして**削除**です。  
  
4.  **ホスト削除の確認**ダイアログ ボックスで、をクリックして**はい**です。  
  
## <a name="see-also"></a>参照  
-  [BizTalk ホストとホスト インスタンスの管理](../core/managing-biztalk-hosts-and-host-instances.md)   
-  [新しいホストを作成する方法](../core/how-to-create-a-new-host.md)   
-  [ホストのプロパティを変更する方法](../core/how-to-modify-host-properties.md)   
-  **MSBTS_Host (WMI)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]