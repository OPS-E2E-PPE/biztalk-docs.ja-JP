---
title: "Biztalk SQL アダプターの SOAP アクションの構成 |Microsoft ドキュメント"
description: "Visual Studio で SOAP アクションを入力または BizTalk アダプター パック (BAP) で、Wcf-custom アダプターまたは WCF SQL アダプターを使用してください"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: acd7f60b-c27f-4988-a67c-e56ef8d38f66
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4e342353b13848cca1c332d4568f541e59924cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-soap-action-for-the-sql-adapter"></a>SQL アダプタの SOAP アクションを構成します。
WCF ベースを使用して SQL Server で操作を実行する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、SOAP アクションを指定する必要があります。 SOAP アクションは、どのようなアクションを実行する必要があります、アダプターに通信します。 SOAP アクションのいずれかを指定する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]またはから、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 ただし、両方の場所からの SOAP アクションを指定する場合、アクション指定したから[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]は上書きされます。  
  
 SOAP アクションを指定する方法の詳細については、次を参照してください。 [WCF 送信アダプタ用の SOAP アクションの指定](../../core/specifying-soap-actions-for-wcf-send-adapters.md)です。
  
## <a name="enter-the-soap-action-in-visual-studio"></a>Visual Studio での SOAP アクションを入力します。  
 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、オーケストレーションの一部として使用して SOAP アクションを指定する必要があります、**式**図形です。  
  
1.  BizTalk オーケストレーションが含まれる、**式**図形からドラッグすることで、 **BizTalk オーケストレーション**ツールボックスします。  
  
2.  ダブルクリックして、**式**図形を BizTalk 式エディタを開きます。  
  
3.  BizTalk 式エディタで、アクションを指定します。 例:  
  
    ```  
    OutboundMessage(WCF.Action)="TableOp/Insert/dbo/Employee"  
    ```  
  
     詳細については、**式**図形および BizTalk 式エディターを参照してください[式を作成する方法](../../core/how-to-create-expressions.md)です。
  
## <a name="enter-the-soap-action-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールからの SOAP アクションを入力します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または WCF SQL ポートの構成の一部として SOAP アクションを指定することができます。  
  
### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a>WCF カスタム ポートの SOAP アクションを入力します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、順にクリック**送信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
4.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。  
  
5.  **アクション**テキスト ボックスで、操作の SOAP アクションを指定します。 次の方法では、アクションを指定できます。  
  
    -   **シングル アクション形式を使用して、**です。 Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。 例:  
  
        ```  
        TableOp/Insert/dbo/Employee  
        ```  
  
    -   **アクション マッピング形式を使用して、**です。 1 つの WCF カスタム ポートを送信し、1 つ以上の操作のメッセージを受け取る場合は、この形式を使用します。 たとえば、1 つの WCF カスタム ポートを送信および (レコードを挿入する Employee テーブルの) Op1、Op2 (レコードを更新する Employee テーブル) のメッセージを受け取る場合、SOAP アクションは、次のように指定できます。  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="TableOp/Insert/dbo/Employee" />  
          <Operation Name="Op2" Action="TableOp/Update/dbo/Employee" />  
        </BtsActionMapping>  
        ```  
  
         アクション マッピングのアプローチでは、アクションのセットを指定して、そのため、同じポートを通過するさまざまなアクションの種類に属しているメッセージの有効化に関して柔軟性を提供します。  
  
         SOAP アクションの形式は操作ごとに異なります。 各操作の操作の形式の詳細については、次を参照してください。[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)です。
  
### <a name="enter-a-soap-action-for-the-wcf-sql-port"></a>WCF SQL ポートの SOAP アクションを入力します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  WCF-SQL アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 手順については、次を参照してください。 [SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)です。  
  
3.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、順にクリック**送信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する WCF-SQL アダプターを選択し、をクリックして**構成**です。  
  
5.  トランスポートのプロパティ ダイアログ ボックスをクリックして、**全般**タブです。  
  
6.  **アクション**テキスト ボックスで、操作の SOAP アクションを指定します。 次の方法では、アクションを指定できます。  
  
    -   **シングル アクション形式を使用して、**です。 WCF SQL 送信ポートし、1 つの操作のメッセージが表示される場合は、この形式を使用します。 例:  
  
        ```  
        TableOp/Insert/dbo/Employee  
        ```  
  
    -   **アクション マッピング形式を使用して、**です。 1 つの WCF SQL ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。 たとえば、1 つの WCF SQL ポートは、(レコードを挿入する Employee テーブルの) Op1、Op2 (レコードを更新する Employee テーブル) のメッセージを送受信場合、SOAP アクションは次のように指定できます。  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="TableOp/Insert/dbo/Employee" />  
          <Operation Name="Op2" Action="TableOp/Update/dbo/Employee" />  
        </BtsActionMapping>  
        ```  
  
         アクション マッピングのアプローチでは、アクションのセットを指定して、そのため、同じポートを通過するさまざまなアクションの種類に属しているメッセージの有効化に関して柔軟性を提供します。  
  
         SOAP アクションの形式は操作ごとに異なります。 各操作の操作の形式の詳細については、次を参照してください。[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)です。
  
## <a name="see-also"></a>参照  
[SQL アダプタを BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)