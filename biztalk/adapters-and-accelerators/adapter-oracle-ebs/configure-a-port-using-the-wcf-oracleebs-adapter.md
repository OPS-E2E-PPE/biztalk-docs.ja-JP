---
title: Wcf-oracleebs アダプターを使用して biztalk ポートの構成 |Microsoft Docs
description: Wcf-oracleebs アダプターを使用して、BizTalk Server で Oracle EBS からメッセージを送受信する
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b4c5c10-79a6-48d3-b4ee-dddf837f020b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26a656f303b10c6c2b62f5c12ecefe0b25be49f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375712"
---
# <a name="configure-a-port-using-the-wcf-oracleebs-adapter"></a>Wcf-oracleebs アダプターを使用してポートを構成します。
Wcf-oracleebs を構成する方法は、送信し、受信ポートで Oracle E-business Suite を使用して、送信および受信操作を実行する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  
  
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)します。
  
## <a name="deploy-adapters-to-send-messages-to-oracle-ebs"></a>Oracle EBS にメッセージを送信アダプターを展開します。 
 Oracle E-business Suite を使用するメッセージを送信するための Wcf-oracleebs 送信ポートを構成するのには、次の手順を実行、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。    
 
1. 開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. Wcf-oracleebs アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 [Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)の手順を示します。
  
3. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
4. 展開するアプリケーションを展開し、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  
  
5. 右クリック**送信ポート**、 をポイント**新規**との間の通信モードによって構成するポートの種類 をポイントし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と Oracle E-business Suite。  
  
6. **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
7. **型**ボックスの一覧が Wcf-oracleebs を選択し、クリックして**構成**します。  
  
8. トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。  
  
   1. をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細については、次を参照してください。 [for Oracle E-business Suite 接続 URI を構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)します。  
  
   2. **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 参照してください[メッセージと Oracle EBS アダプターのメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)の各操作のアクションの一覧。 たとえば、資産のアプリケーションの下で、インターフェイス テーブル (FA_BOOKS) に対する挿入操作を呼び出すアクションは。  
  
      ```  
      InterfaceTables/Insert/OFA/FA/FA_BOOKS  
      ```  
  
   3. をクリックして、**バインド**タブによって公開されるバインドのプロパティを指定して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 バインド プロパティの詳細については、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  
  
      > [!NOTE]
      >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。 たとえば、通知に関連するバインドのプロパティは通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときに使用できませんなりました。  
  
   4. をクリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。  
  
      -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Oracle E-business Suite に接続するためのパスワードを指定します。  
  
          |プロパティ|目的|  
          |--------------|----------------|  
          |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
          |**Oracle E-business Suite の資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**EBusiness** for Oracle E-business Suite の資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。 する必要がありますの Oracle データベースの資格情報を指定するこの例では、 **OracleUserName**と**OraclePassword**プロパティをバインドします。|  
          |**ClientCredentialType が「データベース」に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。|  
          |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。|  
  
      -   選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。  
  
   5. 戻る、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして **[ok]** します。  
  
9. **送信ハンドラー**一覧で、 **BizTalkServerApplication**します。  
  
10. 選択した場合**静的な一方向送信ポート**手順 5 で、送信パイプラインを指定します。 **送信パイプライン**一覧で [xmltransmit] に対応するパイプラインを選択します。  
  
11. 選択した場合**静的な送信請求-応答ポート**手順 4 で、指定の送信および受信パイプライン。  
  
    1.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
    2.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
12. **[OK]** をクリックします。  
  
## <a name="deploy-adapters-to-receive-messages-from-oracle-ebs"></a>Oracle EBS からメッセージを受信アダプターを展開します。  
 以下を実行する、Wcf-oracleebs を構成する手順から Oracle E-business Suite を使用してメッセージを受信するためのポートの受信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
1. 開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. Wcf-oracleebs アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、次を参照してください。 [、Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)します。  
  
3. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
4. 展開するアプリケーションを展開し、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  
  
5. 右クリックして**受信ポート**、 をポイント**新規**、 をクリック**一方向の受信ポート**または**要求-応答受信ポート**に応じて、間の通信モード[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と Oracle E-business Suite。  
  
6. **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  
  
7. **受信場所**] タブで [**新規**します。 **受信場所のプロパティ** ダイアログ ボックスが表示されます。  
  
8. **受信場所のプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1.  受信場所の名前を指定します。  
  
   2.  **型**ボックスの一覧が Wcf-oracleebs を選択し、クリックして**構成**します。  
  
9. トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。  
  
   1. をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細については、次を参照してください。 [for Oracle E-business Suite 接続 URI を構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)します。  
  
   2. をクリックして、**バインド** タブでバインドによって公開されるプロパティの値を指定し、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 バインド プロパティの詳細については、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  
  
      > [!NOTE]
      >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。 たとえば、通知に関連するバインドのプロパティは通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときに使用できませんなりました。  
  
   3. をクリックして、**動作** タブ、トランザクション分離レベルを設定します。 トランザクション分離レベルを設定する方法についての詳細については、次を参照してください。[トランザクション分離レベルの構成と Oracle E-business Suite でのトランザクション タイムアウト](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)します。  
  
   4. をクリックして、**他**タブをクリックし、次のいずれかの操作を行います。  
  
      -   選択**ユーザー アカウント**オプション、およびユーザー名と Oracle E-business Suite に接続するためのパスワードを指定します。  
  
          |プロパティ|目的|  
          |--------------|----------------|  
          |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
          |**Oracle E-business Suite の資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**EBusiness** for Oracle E-business Suite の資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。 する必要がありますの Oracle データベースの資格情報を指定するこの例では、 **OracleUserName**と**OraclePassword**プロパティをバインドします。|  
          |**ClientCredentialType が「データベース」に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。|  
          |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。|  
  
      -   選択**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。  
  
   5. 戻ります、**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**。  
  
10. **受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。  
  
11. 選択した場合**一方向の受信ポート**手順 5 で、受信パイプラインを指定します。 **受信パイプライン**一覧で [xmlreceive] に対応するパイプラインを選択します。  
  
12. 選択した場合**要求-応答受信ポート**手順 5 で、指定の送信および受信パイプライン。  
  
    1.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
    2.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
13. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**します。  
  
14. **受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**します。  
  
## <a name="see-also"></a>参照  
 [Oracle E-business アダプターにバインドする物理ポートを手動で構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)   
 [Windows 認証を使用して Oracle E-business Suite に接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)