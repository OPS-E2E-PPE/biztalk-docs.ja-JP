---
title: Biztalk wcf-custom アダプターおよび Oracle E-business Suite を使用してポートの構成 |Microsoft ドキュメント
description: BizTalk Server で Oracle EBS からメッセージを送信または受信する Wcf-custom アダプターを使用します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83d0bb00-934c-40cf-8833-354e7ce7e927
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03f6071c4df6e60024483e897d577281b1f39487
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218370"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-oracle-e-business-suite"></a>Wcf-custom アダプターおよび Oracle E-business Suite を使用してポートを構成します。
Wcf-custom 送信を構成して受信ポートで Oracle E-business Suite を使用して送信および受信操作を実行する方法、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators グループまたは BizTalk Operators グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)です。
  
## <a name="deploy-adapters-to-send-messages-to-oracle-ebs"></a>Oracle EBS にメッセージを送信アダプターを展開します。  
 Oracle E-business Suite を使用するメッセージを送信するための Wcf-custom 送信ポートを構成する次の手順、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
1.  開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  展開するアプリケーションを展開し、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
4.  右クリック**送信ポート**、 をポイント**新規**との間の通信モードによって構成するポートの種類 をポイントし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と Oracle E-business Suite です。  
  
5.  **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
6.  **型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
7.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  クリックして、**全般**] タブで、し、[、**アドレス (URI)** フィールドで、for Oracle E-business Suite 接続 URI を指定します。 接続 URI の詳細については、次を参照してください。 [Oracle E-business Suite 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)です。  
  
    2.  **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 参照してください[メッセージと Oracle EBS アダプターのメッセージ スキーマを](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)) の各操作のアクションのリスト。 たとえば、資産のアプリケーション インターフェイス テーブル (FA_BOOKS) に対する挿入操作を呼び出すアクションは。  
  
        ```  
        InterfaceTables/Insert/OFA/FA/FA_BOOKS  
        ```  
  
    3.  クリックして、**バインド**] タブとの間、**バインディングの種類**一覧で、[ **oracleEBSBinding**です。 によって公開されている別のバインディング プロパティを指定することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
    4.  クリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。  
  
        -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名と Oracle E-business Suite への接続にパスワードを指定します。  
  
            |プロパティ|目的|  
            |--------------|----------------|  
            |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**にプロパティのバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
            |**Oracle E-business Suite の資格情報を使用して接続するには**|指定して、 **ClientCredentialType**にプロパティのバインド**EBusiness**用 Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 この場合は、Oracle データベースの資格情報を指定する必要がありますも**OracleUserName**と**OraclePassword**プロパティをバインドします。|  
            |**ClientCredentialType が"Database"に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定して、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。|  
            |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。|  
  
        -   選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。  
  
    5.  戻るには、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
8.  **送信ハンドラー**一覧で、 **BizTalkServerApplication**です。  
  
9. 選択した場合**静的な一方向送信ポート**手順 4 で、送信パイプラインを指定します。 **送信パイプライン**一覧で、[xmltransmit] に対応するパイプラインを選択します。  
  
10. 選択した場合**静的な送信請求-応答ポート**手順 4 で、指定の送信および受信パイプラインです。  
  
    1.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
    2.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
11. **[OK]** をクリックします。  
  
## <a name="deploy-adapters-to-receive-messages-from-oracle-ebs"></a>Oracle EBS からメッセージを受信アダプターを展開します。 
 次の実行 Wcf-custom を構成する手順の受信ポートから Oracle E-business Suite を使用してメッセージを受信するため、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
1.  開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  展開するアプリケーションを展開し、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
4.  右クリック**受信ポート**、指す**新規**、 をクリック**一方向の受信ポート**または**要求-応答受信ポート**に応じて、間の通信モード[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle E-business Suite とします。  
  
5.  **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  
  
6.  **受信場所** タブで、をクリックして**新規**です。 **受信場所のプロパティ** ダイアログ ボックスが表示されます。  
  
7.  **受信場所のプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  受信場所の名前を指定します。  
  
    2.  **型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
8.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  クリックして、**全般**] タブで、し、[、**アドレス (URI)** フィールドで、for Oracle E-business Suite 接続 URI を指定します。 接続 URI の詳細については、次を参照してください。 [Oracle E-business Suite 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)です。  
  
    2.  クリックして、**バインド** タブとの間、**バインディングの種類**ドロップダウン リストで、 **oracleEBSBinding**です。 によって公開されている別のバインディング プロパティを指定することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
    3.  クリックして、**動作**タブは、トランザクション分離レベルを設定します。 トランザクション分離レベルの設定の詳細については、次を参照してください。[トランザクション分離レベルの構成と E-business Suite でのトランザクション タイムアウト](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)です。  
  
    4.  クリックして、**他**タブをクリックし、次のいずれかの操作します。  
  
        -   選択**ユーザー アカウント**オプション、およびユーザー名と Oracle E-business Suite への接続にパスワードを指定します。  
  
            |プロパティ|目的|  
            |--------------|----------------|  
            |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**にプロパティのバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
            |**Oracle E-business Suite の資格情報を使用して接続するには**|指定して、 **ClientCredentialType**にプロパティのバインド**EBusiness**用 Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 この場合は、Oracle データベースの資格情報を指定する必要がありますも**OracleUserName**と**OraclePassword**プロパティをバインドします。|  
            |**ClientCredentialType が"Database"に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定して、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。|  
            |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。|  
  
        -   選択**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。  
  
    5.  戻るには、**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
9. **受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**です。  
  
10. 選択した場合**一方向の受信ポート**手順 4 で、受信パイプラインを指定します。 **受信パイプライン**一覧で、[xmlreceive] に対応するパイプラインを選択します。  
  
11. 選択した場合**要求-応答受信ポート**手順 4 で、指定の送信および受信パイプラインです。  
  
    1.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
    2.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
12. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
13. **受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [Oracle E-business アダプターにバインドする物理ポートを手動で構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)   
 [Windows 認証を使用して Oracle E-business Suite に接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)