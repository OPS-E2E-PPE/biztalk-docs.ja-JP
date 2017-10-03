---
title: "Biztalk WCF カスタム アダプターと Siebel アダプターを使用してポートを構成する |Microsoft ドキュメント"
description: "作成 wcf-custom 送信ポートと受信ポートを BizTalk Server で Siebel eBusiness Applications アダプターを使用するには"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53c5ee07-36ae-474b-9241-8b53c9066ca1
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 485bfaf7bd958528630e96a64ca0129a56ec330d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-siebel-adapter"></a>Wcf-custom アダプターと Siebel アダプターを使用してポートを構成します。
このトピックでは、Wcf-custom を構成する方法について送信している Siebel システムでの送信操作を実行するポートでは、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators グループまたは BizTalk Operators グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)です。
  
## <a name="deploying-adapters-for-sending-messages-to-a-siebel-system"></a>Siebel システムへのメッセージ送信用のアダプターの展開  
 Siebel システムを使用して、メッセージを送信するための Wcf-custom 送信ポートを構成する次の手順、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
 
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  展開するアプリケーションを展開し、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
4.  右クリック**送信ポート**、 をポイント**新規**、し、ポートの種類によっては、BizTalk Server と Siebel システム間の通信モードを構成する をポイントします。  
  
5.  **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
6.  **型**ドロップダウン リストで、 **Wcf-custom**  をクリック**構成**です。  
  
7.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  をクリックして、**一般的な** タブで、**アドレス (URI)**フィールドは、接続の Siebel システムへの接続に URI を指定します。 接続 URI の詳細については、次を参照してください。 [Siebel システム接続 URI を作成する](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。  
  
    2.  **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 参照してください[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)各操作のアクションの一覧についてはします。 たとえば、アカウントのビジネス コンポーネントに対する挿入操作を呼び出すアクションは。  
  
        ```  
        http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
        ```  
  
    3.  クリックして、**バインド** タブとの間、**バインディングの種類**ドロップダウン リストで、 **siebelBinding**です。 によって公開されるさまざまなバインドのプロパティを指定することも、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインドのプロパティについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。  
  
    4.  クリックして、**資格情報**タブし、次のいずれかの操作します。  
  
        -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。  
  
        -   選択、**を使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。  
  
         BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [Siebel アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)です。  
  
    5.  戻るには、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
8.  **送信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**です。  
  
9. 手順 4 で静的な一方向送信ポートを選択した場合は、送信パイプラインを指定します。 **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
10. 手順 4. で静的な送信請求-応答ポートを選択した場合は、送信を指定し、受信パイプラインです。  
  
    1.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
    2.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
11. **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
[Siebel アダプターを物理ポートのバインドを手動で構成します。](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)