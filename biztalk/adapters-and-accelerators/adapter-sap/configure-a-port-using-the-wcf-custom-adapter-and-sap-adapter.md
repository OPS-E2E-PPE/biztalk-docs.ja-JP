---
title: Biztalk WCF カスタム アダプターと SAP アダプターを使用してポートの構成 |Microsoft Docs
description: 送信または mySAP アダプターの BizTalk アダプター パック (BAP) を使用して SAP からメッセージを受信する WCF カスタム ポートを作成します。
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
ms.openlocfilehash: 9baf552efc102d13b83b28f5c5b0c473147b2812
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982947"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-sap-adapter"></a>Wcf-custom アダプターと SAP アダプターを使用してポートを構成します。
このトピックでは構成 Wcf-custom 送信ポートと受信ポートを使用して SAP システムでの送信および受信の操作を実行する方法を手順については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最小セキュリティ ユーザー権限](../../core/minimum-security-user-rights.md)します。 
  
## <a name="deploy-adapters-to-send-messages-to-sap"></a>SAP にメッセージを送信アダプターを展開します。  
WCF カスタムを構成するのには、次の手順送信ポートを使用して SAP システムにメッセージを送信するための完全な[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
3. 展開するアプリケーションを展開し、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
4. 右クリックし**送信ポート**、 をポイント**新規**、BizTalk Server と SAP システム間の通信のモードによって構成するポートの種類 をポイントします。  
  
5. **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
6. **型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  
  
7. **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1. をクリックして、**全般** タブで、し、**アドレス (URI)** フィールドに、SAP システムの接続 URI を指定します。 接続 URI の詳細については、[SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)を参照してください。  
  
   2. **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)の各操作のアクションの一覧。 たとえばに、RFC_CUSTOMER_GET を呼び出すアクションは次のようになります。  
  
      ```  
      http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
      ```  
  
   3. をクリックして、**バインド** タブとの間、**バインドの種類**ドロップダウン リストで、 **sapBinding**します。 によって公開されるさまざまなバインドのプロパティを指定することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 バインド プロパティの詳細については、[mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)を参照してください。  
  
   4. をクリックして、**資格情報**タブし、次のいずれかの操作を行います。  
  
      -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と SAP システムへの接続にパスワードを指定します。  
  
      -   選択、**使用してシングル サインオン**オプション、および SSO 関連アプリケーションを指定します。  
  
           BizTalk Server に関するセキュリティの詳細については、[SAP アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)を参照してください。
  
           戻る、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして **[ok]** します。  
  
8. **送信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。  
  
9. 手順 4 で静的な一方向送信ポートを選択した場合は、送信パイプラインを指定します。 **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
10. 選択した場合**静的な送信請求-応答ポート**手順 4 で、指定の送信および受信パイプライン。  
  
    1.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
    2.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
11. **[OK]** をクリックします。  
  
## <a name="deploy-adapters-to-receive-messages-from-sap"></a>SAP からメッセージを受信アダプターを展開します。
WCF カスタムを構成するのには、次の手順を使用して SAP システムからメッセージを受信するためのポートの受信完了、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
3. 展開するアプリケーションを展開し、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
4. 右クリックして**受信ポート**、 をポイント**新規**、 をクリック**一方向の受信ポート**または**要求-応答受信ポート**に応じて、BizTalk Server と SAP システム間の通信のモードです。  
  
5. **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  
  
6. **受信場所**] タブで [**新規**します。 **受信場所のプロパティ** ダイアログ ボックスが表示されます。  
  
7. **受信場所のプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1.  受信場所の名前を指定します。  
  
   2.  **型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  
  
8. **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1.  をクリックして、**全般** タブで、し、**アドレス (URI)** フィールドに、SAP システムの接続 URI を指定します。 接続 URI の詳細については、[SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)を参照してください。  
  
   2.  をクリックして、**バインド** タブとの間、**バインドの種類**ドロップダウン リストで、 **sapBinding**します。 バインド プロパティの詳細については、[mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)を参照してください。  
  
   3.  をクリックして、**他**タブをクリックし、次のいずれかの操作を行います。  
  
       -   選択**ユーザー アカウント**ユーザー名と SAP システムへの接続にパスワードを指定します。  
  
       -   選択**関連アプリケーションから資格情報を Get**オプション、および関連アプリケーションを指定します。  
  
            BizTalk Server に関するセキュリティの詳細については、[SAP アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)を参照してください。
  
            をクリックして**OK**に戻る、**受信場所のプロパティ** ダイアログ ボックス。  
  
9. **受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。  
  
10. 選択した場合**一方向の受信ポート**手順 4 で、受信パイプラインを指定します。 **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
11. 選択した場合**要求-応答受信ポート**手順 4 で、指定の送信および受信パイプライン。  
  
    1.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
    2.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
12. クリックして**OK i**n、**受信場所のプロパティ** ダイアログ ボックス。  
  
13. クリックして**OK**で、**受信ポートのプロパティ** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
[SAP アダプターを物理ポートのバインドを手動で構成します。](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)