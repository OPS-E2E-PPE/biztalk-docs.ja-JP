---
title: BizTalk での Siebel アダプターの SOAP アクションの構成 |Microsoft Docs
description: Visual Studio での SOAP アクションの入力または BizTalk アダプター パック (BAP) で、Wcf-custom または Wcf-siebel アダプターを使用して、
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
ms.openlocfilehash: fb945aba089e0c57e42e846cec765ae48b10d433
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022248"
---
# <a name="configure-the-soap-action-for-siebel"></a>Siebel の SOAP アクションを構成します。
WCF ベースを使用して Siebel システムに対して任意の操作を実行する[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプターのユーザーは、SOAP アクションを指定する必要があります。 SOAP アクションは、どのようなアクションが実行されるアダプターに通信します。 デザイン時または実行時に SOAP アクションを指定することができます。 ただし、SOAP アクション両方デザイン時に指定する時間を実行すると、デザイン時に指定されたアクションは上書きされます。  
  
 SOAP アクションを指定する方法については、[WCF 送信アダプター用の SOAP アクションを指定する](../../core/specifying-soap-actions-for-wcf-send-adapters.md)を参照してください。
  
## <a name="enter-soap-action-at-design-time"></a>デザイン時に SOAP アクションを入力します。  
 式図形を含めることによって、デザイン時のオーケストレーションの一部として SOAP アクションを指定する必要があります。  
  
1.  Biztalk オーケストレーションはからドラッグすることで、式図形を含める、 **BizTalk オーケストレーション**ツールボックスです。  
  
2.  ダブルクリックして、**式**図形、BizTalk 式エディターを開きます。  
  
3.  BizTalk 式エディタで、アクションを指定します。 以下に例を示します。  
  
    ```  
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert"  
    ```  
  
     詳細については**式**図形と、BizTalk 式エディタでを参照してください[式を作成する方法](../../core/how-to-create-expressions.md)します。  
  
## <a name="enter-soap-action-at-run-time"></a>実行時に SOAP アクションを入力します。  
 実行時に、Wcf-custom または Wcf-siebel ポートのプロパティ ダイアログ ボックスの一部として SOAP アクションを指定する必要があります。  
  
#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a>WCF カスタム ポートの SOAP アクションを入力します。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、 をクリックし、**送信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  
  
4. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。  
  
5. **アクション**テキスト ボックスで、操作の SOAP アクションを指定します。 次の方法では、アクションを指定できます。  
  
   -   **シングル アクション形式を使用して**します。 Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。 以下に例を示します。  
  
       ```  
       http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
       ```  
  
   -   **アクション マッピング形式を使用して**します。 1 つの WCF カスタム ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。 たとえば、送受信 (アカウントのビジネス コンポーネントに対して、挿入操作を実行) を Op1 と Op2 (アカウントのビジネス コンポーネントに対する更新操作を実行) にメッセージを受け取る 1 つの WCF カスタム ポートを SOAP アクションで指定できます、次方法:  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update " />  
       </BtsActionMapping>  
       ```  
  
        このアプローチには、一連のアクションを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が提供されます。  
  
        SOAP アクションの形式は操作ごとに異なります。 各操作のアクションの形式の詳細については、[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)を参照してください。
  
#### <a name="enter-a-soap-action-for-the-wcf-siebel-port"></a>Wcf-siebel ポートの SOAP アクションを入力します。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. Wcf-siebel アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、[Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)を参照してください。  
  
3. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、 をクリックし、**送信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リスト、選択、Wcf-siebel アダプター以前では、追加し、をクリックし、**構成**します。  
  
5. ポートのプロパティ ダイアログ ボックスでをクリックして、**全般**タブ。  
  
6. **アクション**テキスト ボックスで、操作の SOAP アクションを指定します。 次の方法では、アクションを指定できます。  
  
   -   **シングル アクション形式を使用して**します。 Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。 以下に例を示します。  
  
       ```  
       http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
       ```  
  
   -   **アクション マッピング形式を使用して**します。 1 つの WCF カスタム ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。 たとえば、送受信 (アカウントのビジネス コンポーネントに対して、挿入操作を実行) を Op1 と Op2 (アカウントのビジネス コンポーネントに対する更新操作を実行) にメッセージを受け取る 1 つの WCF カスタム ポートを SOAP アクションで指定できます、次方法:  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update " />  
       </BtsActionMapping>  
       ```  
  
        このアプローチには、一連のアクションを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が提供されます。  
  
        SOAP アクションの形式は操作ごとに異なります。 各操作のアクションの形式の詳細については、[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)を参照してください。
  
## <a name="see-also"></a>参照  
[Siebel アダプターを使用した BizTalk アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)