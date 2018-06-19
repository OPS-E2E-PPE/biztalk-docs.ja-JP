---
title: Biztalk の Siebel アダプターの SOAP アクションの構成 |Microsoft ドキュメント
description: Visual Studio で SOAP アクションを入力するか、Wcf-custom アダプターまたは Wcf-siebel アダプターの BizTalk アダプター パック (BAP) でを使用
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f22a4691-0355-4f08-a14e-e90a3c987ac0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b851aa0b26d80a43f5a839232298ace5507f471b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222562"
---
# <a name="configure-the-soap-action-for-siebel"></a>Siebel の SOAP アクションを構成します。
WCF ベースを使用して、Siebel システムで操作を実行する[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプターのユーザーは、SOAP アクションを指定する必要があります。 SOAP アクションは、どのようなアクションを実行する必要があります、アダプターに通信します。 デザイン時に、または実行時に SOAP アクションを指定することができます。 ただし、SOAP アクション両方デザイン時に指定し、実行時、デザイン時に指定されたアクションがオーバーライドされます。  
  
 SOAP アクションを指定する方法の詳細については、次を参照してください。 [WCF 送信アダプタ用の SOAP アクションの指定](../../core/specifying-soap-actions-for-wcf-send-adapters.md)です。
  
## <a name="enter-soap-action-at-design-time"></a>デザイン時に SOAP アクションを入力します。  
 デザイン時の式図形を含めることによって、オーケストレーションの一部として SOAP アクションを指定する必要があります。  
  
1.  BizTalk オーケストレーションが含まれる式図形からドラッグすることで、 **BizTalk オーケストレーション**ツールボックスします。  
  
2.  ダブルクリックして、**式**図形を BizTalk 式エディタを開きます。  
  
3.  BizTalk 式エディターで、アクションを指定します。 例:  
  
    ```  
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert"  
    ```  
  
     詳細については**式**図形と、BizTalk 式エディターを参照してください[式を作成する方法](../../core/how-to-create-expressions.md)です。  
  
## <a name="enter-soap-action-at-run-time"></a>SOAP アクションを実行時に入力してください。  
 実行時に、Wcf-custom または Wcf-siebel ポートのプロパティ ダイアログ ボックスの一部として SOAP アクションを指定する必要があります。  
  
#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a>WCF カスタム ポートの SOAP アクションを入力します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、順にクリック**送信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
4.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。  
  
5.  **アクション**テキスト ボックスで、操作の SOAP アクションを指定します。 次の方法では、アクションを指定できます。  
  
    -   **シングル アクション形式を使用して、** です。 Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。 例:  
  
        ```  
        http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
        ```  
  
    -   **アクション マッピング形式を使用して、** です。 1 つの WCF カスタム ポートを送信し、1 つ以上の操作のメッセージを受け取る場合は、この形式を使用します。 たとえば、1 つの WCF カスタム ポートを送信および (アカウント ビジネス コンポーネントで挿入操作の実行) する Op1、Op2 (を実行するアカウントのビジネス コンポーネントの更新操作) のメッセージを受け取る場合、SOAP アクションを指定できますでは、次に方法:  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update " />  
        </BtsActionMapping>  
        ```  
  
         このアプローチには、一連のアクションを指定して、そのため、同じポートを通過するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が実現します。  
  
         SOAP アクションの形式は操作ごとに異なります。 各操作のアクションの形式の詳細については、次を参照してください。[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)です。
  
#### <a name="enter-a-soap-action-for-the-wcf-siebel-port"></a>Wcf-siebel ポートの SOAP アクションを入力します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  Wcf-siebel アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 手順については、次を参照してください。 [Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)です。  
  
3.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、順にクリック**送信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4.  ポートのプロパティ ダイアログ ボックスから、**型**一覧から、以前に追加し、をクリックして選択、Wcf-siebel アダプター**構成**です。  
  
5.  ポートのプロパティ ダイアログ ボックスをクリックして、**全般**タブです。  
  
6.  **アクション**テキスト ボックスで、操作の SOAP アクションを指定します。 次の方法では、アクションを指定できます。  
  
    -   **シングル アクション形式を使用して、** です。 Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。 例:  
  
        ```  
        http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
        ```  
  
    -   **アクション マッピング形式を使用して、** です。 1 つの WCF カスタム ポートを送信し、1 つ以上の操作のメッセージを受け取る場合は、この形式を使用します。 たとえば、1 つの WCF カスタム ポートを送信および (アカウント ビジネス コンポーネントで挿入操作の実行) する Op1、Op2 (を実行するアカウントのビジネス コンポーネントの更新操作) のメッセージを受け取る場合、SOAP アクションを指定できますでは、次に方法:  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update " />  
        </BtsActionMapping>  
        ```  
  
         このアプローチには、一連のアクションを指定して、そのため、同じポートを通過するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が実現します。  
  
         SOAP アクションの形式は操作ごとに異なります。 各操作のアクションの形式の詳細については、次を参照してください。[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)です。
  
## <a name="see-also"></a>参照  
[Siebel アダプターと BizTalk アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)