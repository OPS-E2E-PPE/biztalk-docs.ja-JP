---
title: BizTalk で Oracle データベースの SOAP アクションの構成 |Microsoft ドキュメント
description: Visual Studio で SOAP アクションを入力するか、Wcf-custom アダプターまたは Wcf-oracledb アダプターの BizTalk アダプター パック (BAP) でを使用
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0d21cca-3907-4f99-af76-c1e7286e1bcf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2577a221385cdef2e210798b3e8170433ff0e48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215402"
---
# <a name="configure-the-soap-action-for-oracle-database"></a>Oracle データベースの SOAP アクションを構成します。
WCF ベースを使用して Oracle データベースで任意の操作を完了する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプターのユーザーは、SOAP アクションを入力する必要があります。 SOAP アクションは、どのような操作を完了する必要があるアダプターに通信します。 デザイン時に、または実行時に SOAP アクションを入力することができます。 ただし、入力 SOAP アクション両方デザイン時に時刻を実行すると、デザイン時に入力するアクションはオーバーライドされます。  
  
 SOAP アクションを指定する方法の詳細については、次を参照してください。 [WCF 送信アダプタ用の SOAP アクションの指定](../../core/specifying-soap-actions-for-wcf-send-adapters.md)です。  
  
## <a name="enter-soap-action-from-visual-studio"></a>Visual Studio からの SOAP アクションを入力します。  
 Visual Studio から、必要がありますを指定する SOAP アクションのオーケストレーションの一部としてを使用して、**式**図形です。  
  
1.  BizTalk オーケストレーションが含まれる、**式**図形からドラッグすることで、 **BizTalk オーケストレーション**ツールボックスします。  
  
2.  ダブルクリックして、**式**図形を BizTalk 式エディタを開きます。  
  
3.  BizTalk 式エディターで、アクションを指定します。 例:  
  
    ```
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"  
    ```  
  
     詳細については**式**図形と、BizTalk 式エディターを参照してください[式を作成する方法](../../core/how-to-create-expressions.md)です。  
  
## <a name="enter-soap-action-from-biztalk-server-administration"></a>BizTalk Server 管理コンソールからの SOAP アクションを入力します。  
 BizTalk Server 管理コンソールで、Wcf-custom または Wcf-oracledb ポートの構成の一部として SOAP アクションを指定する必要があります。 

#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a>WCF カスタム ポートの SOAP アクションを入力します。  
 
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開**送信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
4.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。  
  
5.  **アクション**テキスト ボックスで、操作の SOAP アクションを指定します。 次の方法では、アクションを指定できます。  
  
    -   **シングル アクション形式を使用して、** です。 Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。 例:  
  
        ```  
        http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
        ```  
  
    -   **アクション マッピング形式を使用して、** です。 1 つの WCF カスタム ポートを送信し、1 つ以上の操作のメッセージを受け取る場合は、この形式を使用します。 たとえば、1 つの WCF カスタム ポートを送信および (レコードを挿入する、EMP テーブル内) Op1、Op2 (レコードを更新する、EMP テーブル内) のメッセージを受け取る場合、SOAP アクションは、次のように指定できます。  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
        </BtsActionMapping>  
        ```  
  
         このアプローチには、一連のアクションを指定して、そのため、同じポートを通過するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が実現します。  
  
         SOAP アクションの形式は操作ごとに異なります。 各操作のアクションの形式の詳細については、次を参照してください。[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)です。  
  
#### <a name="enter-a-soap-action-for-the-wcf-oracledb-port"></a>Wcf-oracledb ポートの SOAP アクションを入力します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  Wcf-oracledb アダプターを BizTalk Server 管理コンソールに追加します。 手順については、次を参照してください。 [BizTalk Server 管理コンソールへの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)です。  
  
3.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開**送信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する Wcf-oracledb ポートを選択し、をクリックして**構成**です。  
  
5.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。  
  
6.  **アクション**テキスト ボックスで、操作の SOAP アクションを指定します。 次の方法では、アクションを指定できます。  
  
    -   **シングル アクション形式を使用して、** です。 Wcf-oracledb、送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。 例:  
  
        ```  
        http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
        ```  
  
    -   **アクション マッピング形式を使用して、** です。 1 つの Wcf-oracledb ポートを送信および複数の操作のメッセージを受け取る場合は、この形式を使用します。 たとえば、1 つの Wcf-oracledb ポートは、(レコードを挿入する、EMP テーブル内) Op1、Op2 (レコードを更新する、EMP テーブル内) のメッセージを送受信場合、SOAP アクションは次のように指定できます。  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
        </BtsActionMapping>  
        ```  
  
         このアプローチには、一連のアクションを指定して、そのため、同じポートを通過するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が実現します。  
  
         SOAP アクションの形式は操作ごとに異なります。 各操作のアクションの形式の詳細については、次を参照してください。[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)です。
  
## <a name="see-also"></a>参照  
[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)