---
title: BizTalk での Oracle データベースの SOAP アクションの構成 |Microsoft Docs
description: Visual Studio での SOAP アクションの入力または BizTalk アダプター パック (BAP) で、Wcf-custom または Wcf-oracledb アダプターを使用して、
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
ms.openlocfilehash: fe8b1b2c1043551b692530dcff4b8fdf49a44b54
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994675"
---
# <a name="configure-the-soap-action-for-oracle-database"></a>Oracle データベースの SOAP アクションを構成します。
WCF ベースを使用して Oracle データベースで任意の操作を完了する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプターのユーザーは、SOAP アクションを入力する必要があります。 SOAP アクションは、どのような操作を完了する必要があります、アダプターに通信します。 デザイン時または実行時に SOAP アクションを入力することができます。 ただし、SOAP アクション両方デザイン時の入力時間を実行すると、デザイン時に入力するアクションはオーバーライドされます。  
  
 SOAP アクションを指定する方法については、次を参照してください。 [WCF 送信アダプター用の SOAP アクションを指定する](../../core/specifying-soap-actions-for-wcf-send-adapters.md)します。  
  
## <a name="enter-soap-action-from-visual-studio"></a>Visual Studio からの SOAP アクションを入力します。  
 Visual studio でする必要がありますアクションを指定する、SOAP、オーケストレーションの一部としてを使用して、**式**図形。  
  
1.  BizTalk オーケストレーションで含める、**式**図形からドラッグすることで、 **BizTalk オーケストレーション**ツールボックス。  
  
2.  ダブルクリックして、**式**図形、BizTalk 式エディターを開きます。  
  
3.  BizTalk 式エディタで、アクションを指定します。 以下に例を示します。  
  
    ```
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"  
    ```  
  
     詳細については**式**図形と、BizTalk 式エディタでを参照してください[式を作成する方法](../../core/how-to-create-expressions.md)します。  
  
## <a name="enter-soap-action-from-biztalk-server-administration"></a>BizTalk Server 管理からの SOAP アクションを入力します。  
 BizTalk Server 管理コンソールで、Wcf-custom または Wcf-oracledb ポート構成の一部として SOAP アクションを指定する必要があります。 

#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a>WCF カスタム ポートの SOAP アクションを入力します。  
 
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**をクリックして、ポートを作成するアプリケーションを展開し、**送信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  
  
4. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。  
  
5. **アクション**テキスト ボックスで、操作の SOAP アクションを指定します。 次の方法では、アクションを指定できます。  
  
   -   **シングル アクション形式を使用して**します。 Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。 以下に例を示します。  
  
       ```  
       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
       ```  
  
   -   **アクション マッピング形式を使用して**します。 1 つの WCF カスタム ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。 たとえば、送受信 (EMP テーブル内のレコードを挿入) するための Op1 と Op2 (EMP テーブル内のレコードを更新) するメッセージを受信する 1 つの WCF カスタム ポートを SOAP アクションは次のように指定できます。  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
       </BtsActionMapping>  
       ```  
  
        このアプローチには、一連のアクションを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が提供されます。  
  
        SOAP アクションの形式は操作ごとに異なります。 各操作のアクションの形式の詳細については、次を参照してください。[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)します。  
  
#### <a name="enter-a-soap-action-for-the-wcf-oracledb-port"></a>Wcf-oracledb ポートの SOAP アクションを入力します。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. Wcf-oracledb アダプターを BizTalk Server 管理コンソールに追加します。 手順については、次を参照してください。[を BizTalk Server 管理コンソールの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)します。  
  
3. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**をクリックして、ポートを作成するアプリケーションを展開し、**送信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4. ポートのプロパティ ダイアログ ボックスから、**型**ボックスの一覧は、先ほど追加した Wcf-oracledb ポートを選択し、順にクリックします**構成**します。  
  
5. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。  
  
6. **アクション**テキスト ボックスで、操作の SOAP アクションを指定します。 次の方法では、アクションを指定できます。  
  
   -   **シングル アクション形式を使用して**します。 Wcf-oracledb、送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。 以下に例を示します。  
  
       ```  
       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
       ```  
  
   -   **アクション マッピング形式を使用して**します。 1 つの Wcf-oracledb ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。 たとえば、送受信 (EMP テーブル内のレコードを挿入) するための Op1 と Op2 (EMP テーブル内のレコードを更新) するメッセージを受信する 1 つの Wcf-oracledb ポート、SOAP アクションは次のように指定できます。  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
       </BtsActionMapping>  
       ```  
  
        このアプローチには、一連のアクションを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が提供されます。  
  
        SOAP アクションの形式は操作ごとに異なります。 各操作のアクションの形式の詳細については、次を参照してください。[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)します。
  
## <a name="see-also"></a>参照  
[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)