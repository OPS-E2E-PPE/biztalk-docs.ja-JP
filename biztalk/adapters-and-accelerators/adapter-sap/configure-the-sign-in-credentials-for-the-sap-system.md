---
title: SAP システムの資格情報で、サインオンの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb41106b-b673-4fcf-a56e-6208e3113469
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a6ace75f66bb7fdd4cfb3362f7d019ab99d73bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217810"
---
# <a name="configure-the-sign-in-credentials-for-the-sap-system"></a>SAP システムの資格情報で、サインオンを構成します。
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアント クライアントの資格情報を提供する必要があります。 アダプターは、SAP システムでユーザーを認証し、接続を確立するために、これらの資格情報を使用します。  
  
 アダプターのクライアントでは、デザイン時に、クライアント両方資格情報を提供したり、時間を実行することができます。 デザイン時に、メタデータを生成する資格情報が必要です。 実行時に、SAP システムでの操作を実行する資格情報が必要です。 このセクションでは、デザイン時および実行時にクライアントの資格情報を指定することに関する情報を提供します。  
  
## <a name="enter-the-client-credentials-at-design-time"></a>デザイン時にクライアントの資格情報を入力してください。  
 デザイン時にを使用して資格情報を指定することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。  
  
### <a name="enter-credentials-using-consume-adapter-service-add-in"></a>アダプター サービスのアドインを使用して資格情報を入力してください。  
  
1.  BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプター サービスの使用**です。|  
    |**[テンプレート]**|をクリックして**アダプター サービスの使用**です。|  
  
3.  開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。  
  
4.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**sapBinding**、順にクリック**構成**です。  
  
5.  **アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と、SAP システムへの接続にパスワードを指定します。  
  
6.  **[OK]** をクリックします。  
  
### <a name="enter-credentials-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用して資格情報を入力してください。  
  
1.  BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプターを追加**です。|  
    |**[テンプレート]**|をクリックして**アダプター メタデータの追加**です。|  
  
3.  **[追加]** をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  
  
4.  アダプターの追加ウィザードで選択**WCF SAP**です。 BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。  
  
    > [!IMPORTANT]
    >  BizTalk で構成されている WCF SAP ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。  
  
5.  **[次へ]** をクリックします。  
  
6.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**sapBinding**、順にクリック**構成**です。  
  
7.  **アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と、SAP システムへの接続にパスワードを指定します。  
  
8.  **[OK]** をクリックします。  
  
## <a name="enter-client-credentials-at-run-time"></a>実行時にクライアントの資格情報を入力してください。  
 実行時に、クライアントの資格情報を指定で Wcf-custom または WCF SAP ポートの構成の一部として、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
### <a name="enter-credentials-for-the-wcf-custom-port"></a>WCF カスタム ポートの資格情報を入力します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
4.  送信ポートの場合に、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、次のいずれかの操作します。  
  
    -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名と、SAP システムへの接続にパスワードを指定します。  
  
    -   選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。  
  
5.  受信ポートの場合で、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他の**タブし、次のいずれかの操作します。  
  
    -   選択**ユーザー アカウント**オプション、およびユーザー名と、SAP システムへの接続にパスワードを指定します。  
  
    -   選択**から資格情報を取得関連アプリケーション**オプション、および関連アプリケーションを指定します。  
  
6.  **[OK]** をクリックします。  
  
### <a name="enter-credentials-for-the-wcf-sap-port"></a>WCF SAP ポートの資格情報を入力します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  WCF SAP アダプターを追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 手順については、次を参照してください。 [SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)です。  
  
3.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する WCF SAP アダプターを選択し、をクリックして**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
5.  トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合にクリックして、**資格情報**タブし、次のいずれかの操作します。  
  
    1.  選択、**シングル サインオンを使用しない**オプション、およびユーザー名と、SAP システムへの接続にパスワードを指定します。  
  
    2.  選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。  
  
6.  受信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他の**タブし、次のいずれかの操作します。  
  
    1.  選択**ユーザー アカウント**オプション、およびユーザー名と、SAP システムへの接続にパスワードを指定します。  
  
    2.  選択**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。  
  
7.  **[OK]** をクリックします。  
  
> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]また、エンタープライズ シングル サインオン (SSO) システムをサポートします。 SSO は、BizTalk のシナリオで使用できるのみ、[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]は SSO 関連アプリケーションを認識します。 BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [SAP アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)です。
  
## <a name="see-also"></a>参照  
[SAP アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)