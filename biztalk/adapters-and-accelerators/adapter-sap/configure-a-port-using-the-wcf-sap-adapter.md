---
title: WCF-SAP アダプターを使用して biztalk ポートの構成 |Microsoft Docs
description: 送信または mySAP アダプターの BizTalk アダプター パック (BAP) を使用して SAP からメッセージを受信する WCF SAP ポートを作成します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 420683f8-2516-4c65-895d-fe535824d450
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e9d701851183e4c328317479d23951118b223d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373866"
---
# <a name="configure-a-port-using-the-wcf-sap-adapter"></a>WCF-SAP アダプターを使用してポートを構成します。
このトピックでは、SAP で WCF を構成する方法については送受信ポートを使用して SAP システムに送信および受信操作を実行する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)します。
  
## <a name="deploy-adapters-to-send-messages-to-sap"></a>SAP にメッセージを送信アダプターを展開します。  
完全な WCF SAP を構成するのには、次の手順送信ポートを使用して SAP システムにメッセージを送信するため、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. WCF-SAP アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、次を参照してください。 [SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)します。  
  
3. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
4. 展開するアプリケーションを展開し、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
5. 右クリックし**送信ポート**、 をポイント**新規**、BizTalk Server と SAP システム間の通信のモードによって構成するポートの種類 をポイントします。  
  
6. **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
7. **型**ドロップダウン リストでは、先ほど追加した WCF-SAP アダプターを選択し、順にクリックします**構成**します。  
  
8. トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。  
  
   1. をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
   2. **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)の各操作のアクションの一覧。 たとえばに、RFC_CUSTOMER_GET を呼び出すアクションは次のようになります。  
  
      ```  
      http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
      ```  
  
   3. をクリックして、**バインド** タブでバインドによって公開されるプロパティの値を指定し、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 バインド プロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  
  
      > [!NOTE]
      >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。 たとえば、バインディングのプロパティに関連する受信操作をご利用いただけません受信操作には、受信ポートの構成が必要とするために、送信ポートを構成するときに。  
  
   4. をクリックして、**資格情報**タブし、次のいずれかの操作を行います。  
  
   -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と SAP システムへの接続にパスワードを指定します。  
  
   -   選択、**使用してシングル サインオン**オプション、および SSO 関連アプリケーションを指定します。  
  
        BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [SAP アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)します。  
  
        戻る、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして **[ok]** します。  
  
9. **送信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。  
  
10. 作成した場合、**静的な一方向送信ポート**手順 5 で、送信パイプラインを指定します。 **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
11. 作成した場合、**静的な送信請求-応答ポート**手順 5 で、指定の送信および受信パイプライン。  
  
    1.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
    2.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
12. **[OK]** をクリックします。  
  
## <a name="deploy-adapters-to-receive-messages-from-sap"></a>SAP からメッセージを受信アダプターを展開します。  
WCF SAP を構成するのには、次の手順を使用して SAP システムからメッセージを受信するためのポートの受信完了、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. WCF-SAP アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、次を参照してください。 [SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)します。  
  
3. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
4. 展開するアプリケーションを展開し、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
5. 右クリックして**受信ポート**、 をポイント**新規**、 をクリック**一方向の受信ポート**または**要求-応答受信ポート**に応じて、BizTalk Server と SAP システム間の通信のモードです。  
  
6. **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  
  
7. **受信場所**] タブで [**新規**します。 **受信場所のプロパティ** ダイアログ ボックスが表示されます。  
  
8. **受信場所のプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1.  受信場所の名前を指定します。  
  
   2.  **型**ドロップダウン リストでは、先ほど追加した WCF-SAP アダプターを選択し、順にクリックします**構成**します。  
  
9. トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。  
  
   1. をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
   2. をクリックして、**バインド** タブとの間、**バインドの種類**ドロップダウン リストで、 **sapBinding**します。 バインド プロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  
  
      > [!NOTE]
      >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。 たとえば、バインディングのプロパティに関連する受信操作をご利用いただけません受信操作には、受信ポートの構成が必要とするために、送信ポートを構成するときに。  
  
   3. をクリックして、**他**タブをクリックし、次のいずれかの操作を行います。  
  
   4. 選択**ユーザー アカウント**ユーザー名と SAP システムへの接続にパスワードを指定します。  
  
   5. 選択**関連アプリケーションから資格情報を Get**オプション、および関連アプリケーションを指定します。  
  
       BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [SAP アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)します。  
  
       をクリックして**OK**に戻る、**受信場所のプロパティ** ダイアログ ボックス。  
  
10. **受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。  
  
11. 作成した場合**一方向の受信ポート**手順 5 で、受信パイプラインを指定します。 **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
12. 作成した場合**要求-応答受信ポート**手順 5 で、指定の送信および受信パイプライン。  
  
    1.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
    2.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
13. クリックして**OK**で、**受信場所のプロパティ** ダイアログ ボックス。  
  
14. クリックして**OK**で、**受信ポートのプロパティ** ダイアログ ボックス。

## <a name="see-also"></a>参照
[SAP アダプターを物理ポートのバインドを手動で構成します。](manually-configure-a-physical-port-binding-to-the-sap-adapter.md)