---
title: Biztalk WCF カスタム アダプターと SAP アダプターを使用してポートを構成する |Microsoft ドキュメント
description: MySAP アダプターの BizTalk アダプター パック (BAP) を使用して SAP からのメッセージの送受信に WCF カスタム ポートを作成します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3962456-e9ac-4575-8266-b35e892dd428
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66770264e2f76a589080cf86476448c2716b8897
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217738"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-sap-adapter"></a>Wcf-custom アダプターおよび SAP アダプターを使用してポートを構成します。
このトピックでは、Wcf-custom 送信ポートと受信ポートを使用して SAP システムの送信および受信の操作を実行する方法の説明、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators グループまたは BizTalk Operators グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ ユーザー権限](../../core/minimum-security-user-rights.md)です。 
  
## <a name="deploy-adapters-to-send-messages-to-sap"></a>SAP にメッセージを送信アダプターを展開します。  
完了を Wcf-custom を構成するのには、次の手順送信ポートを使用して SAP システムにメッセージを送信するため、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  展開するアプリケーションを展開し、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
4.  右クリック**送信ポート**、 をポイント**新規**、し、ポートの種類によっては、BizTalk Server と SAP システム間の通信モードを構成する をポイントします。  
  
5.  **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
6.  **型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
7.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  クリックして、**全般**] タブで、し、[、**アドレス (URI)** フィールドで、SAP システムの接続 URI を指定します。 接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
    2.  **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 参照してください[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)各操作のアクションの一覧についてはします。 たとえばに、RFC_CUSTOMER_GET を呼び出すアクションは次のようになります。  
  
        ```  
        http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
        ```  
  
    3.  クリックして、**バインド** タブとの間、**バインディングの種類**ドロップダウン リストで、 **sapBinding**です。 によって公開されている別のバインディング プロパティを指定することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 バインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
    4.  クリックして、**資格情報**タブし、次のいずれかの操作します。  
  
        -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名と、SAP システムへの接続にパスワードを指定します。  
  
        -   選択、**を使用してシングル サインオン**オプション、および SSO 関連アプリケーションを指定します。  
  
             BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [SAP アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)です。
  
             戻るには、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
8.  **送信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**です。  
  
9. 手順 4 で静的な一方向送信ポートを選択した場合は、送信パイプラインを指定します。 **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
10. 選択した場合**静的な送信請求-応答ポート**手順 4 で、指定の送信および受信パイプラインです。  
  
    1.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
    2.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
11. **[OK]** をクリックします。  
  
## <a name="deploy-adapters-to-receive-messages-from-sap"></a>SAP からメッセージを受信アダプターを展開します。
Wcf-custom を構成する次の手順を使用して SAP システムからメッセージを受信するためのポートの受信完了、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  展開するアプリケーションを展開し、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
4.  右クリック**受信ポート**、指す**新規**、 をクリック**一方向の受信ポート**または**要求-応答受信ポート**に応じて、BizTalk Server と SAP システム間の通信のモードです。  
  
5.  **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  
  
6.  **受信場所** タブで、をクリックして**新規**です。 **受信場所のプロパティ** ダイアログ ボックスが表示されます。  
  
7.  **受信場所のプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  受信場所の名前を指定します。  
  
    2.  **型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
8.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  クリックして、**全般**] タブで、し、[、**アドレス (URI)** フィールドで、SAP システムの接続 URI を指定します。 接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
    2.  クリックして、**バインド** タブとの間、**バインディングの種類**ドロップダウン リストで、 **sapBinding**です。 バインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
    3.  クリックして、**他**タブをクリックし、次のいずれかの操作します。  
  
        -   選択**ユーザー アカウント**ユーザー名と、SAP システムへの接続にパスワードを指定します。  
  
        -   選択**から資格情報を取得関連アプリケーション**オプション、および関連アプリケーションを指定します。  
  
             BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [SAP アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)です。
  
             をクリックして**OK**に戻るには、**受信場所のプロパティ** ダイアログ ボックス。  
  
9. **受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**です。  
  
10. 選択した場合**一方向の受信ポート**手順 4 で、受信パイプラインを指定します。 **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
11. 選択した場合**要求-応答受信ポート**手順 4 で、指定の送信および受信パイプラインです。  
  
    1.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
    2.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
12. をクリックして**OK i**n、**受信場所のプロパティ** ダイアログ ボックス。  
  
13. をクリックして**OK**で、**受信ポートのプロパティ** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
[SAP アダプターを物理ポートのバインドを手動で構成します。](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)