---
title: BizTalk での SAP システムの SOAP アクションの構成 |Microsoft Docs
description: 式図形に SOAP アクションを入力するか、BizTalk アダプター パック (BAP) で、Wcf-custom または WCF-SAP アダプターを使用して、
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76084bc5-7a10-4c4c-be22-bee83779a011
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 963c4b3c8d8287b430774813487e924837880a01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004875"
---
# <a name="configure-the-soap-action-for-the-sap-system"></a>SAP システムの SOAP アクションを構成します。
WCF ベースを使用して SAP システムの操作を実行する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプターのユーザーは、SOAP アクションを指定する必要があります。 SOAP アクションは、どのようなアクションが実行されるアダプターに通信します。 デザイン時または実行時に SOAP アクションを指定することができます。 ただし、SOAP アクション両方デザイン時に指定する時間を実行すると、デザイン時に指定されたアクションは上書きされます。  
  
 SOAP アクションを指定する方法については、[WCF 送信アダプター用の SOAP アクションを指定する](../../core/specifying-soap-actions-for-wcf-send-adapters.md)を参照してください。
  
## <a name="enter-soap-action-at-design-time"></a>デザイン時に SOAP アクションを入力します。  
 式図形を含めることによって、デザイン時のオーケストレーションの一部として SOAP アクションを指定する必要があります。  
  
 
1.  BizTalk オーケストレーションで式図形を含めるからドラッグすることで、 **BizTalk オーケストレーション**ツールボックスです。  
  
2.  ダブルクリックして、**式**図形、BizTalk 式エディターを開きます。  
  
3.  BizTalk 式エディタで、アクションを指定します。 以下に例を示します。  
  
    ```  
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET"  
    ```  
  
     詳細については、**式**図形と、BizTalk 式エディタでを参照してください[式を作成する方法](../../core/how-to-create-expressions.md)します。
  
## <a name="enter-soap-action-at-run-time"></a>実行時に SOAP アクションを入力します。  
 実行時に、Wcf-custom または WCF SAP ポートの構成の一部として SOAP アクションを指定できます。  
  
### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a>WCF カスタム ポートの SOAP アクションを入力します。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、 をクリックし、**送信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  
  
4. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。  
  
5. **アクション**テキスト ボックスで、操作の SOAP アクションを指定します。 次の方法では、アクションを指定できます。  
  
   -   **シングル アクション形式を使用して**します。 Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。 以下に例を示します。  
  
       ```  
       http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
       ```  
  
   -   **アクション マッピング形式を使用して**します。 1 つの WCF カスタム ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。 たとえば、送受信 (RFC_CUSTOMER_GET RFC を呼び出す) を Op1 と Op2 (BAPI_SALESORDER_CREATEFROMDAT2 BAPI を呼び出す) へのメッセージを受け取る 1 つの WCF カスタム ポートを SOAP アクションは次のように指定できます。  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2" />  
       </BtsActionMapping>  
       ```  
  
        このアプローチには、一連のアクションを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が提供されます。  
  
        SOAP アクションの形式は操作ごとに異なります。 各操作のアクションの形式の詳細については、[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)を参照してください。
  
### <a name="enter-a-soap-action-for-the-wcf-sap-port"></a>WCF SAP ポートの SOAP アクションを入力します。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. WCF-SAP アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、[SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)を参照してください。  
  
3. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、 をクリックし、**送信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した WCF-SAP アダプターを選択し、順にクリックします**構成**します。  
  
5. トランスポートのプロパティ ダイアログ ボックスでをクリックして、**全般**タブ。  
  
6. **アクション**テキスト ボックスで、操作の SOAP アクションを指定します。 次の方法では、アクションを指定できます。  
  
   -   **シングル アクション形式を使用して**します。 Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。 以下に例を示します。  
  
       ```  
       http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
       ```  
  
   -   **アクション マッピング形式を使用して**します。 1 つの WCF カスタム ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。 たとえば、送受信 (RFC_CUSTOMER_GET RFC を呼び出す) を Op1 と Op2 (BAPI_SALESORDER_CREATEFROMDAT2 BAPI を呼び出す) へのメッセージを受け取る 1 つの WCF カスタム ポートを SOAP アクションは次のように指定できます。  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2" />  
       </BtsActionMapping>  
       ```  
  
        このアプローチには、一連のアクションを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が提供されます。  
  
        SOAP アクションの形式は操作ごとに異なります。 各操作のアクションの形式の詳細については、[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)を参照してください。
  
## <a name="see-also"></a>参照  
[SAP アプリケーションを作成するための構成要素](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)