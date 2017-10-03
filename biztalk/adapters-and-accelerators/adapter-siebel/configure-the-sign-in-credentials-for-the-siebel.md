---
title: "Siebel の資格情報 で、サインオンの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, specify credentials for the Siebel system at run time
- credentials, specifying
- how to, specify credentials for the Siebel system at design time
ms.assetid: a9fef2ba-c38e-44f7-84a3-b6a95d4dc210
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e29f79830a3b76c094ebf8b70d533bfd36218f95
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-sign-in-credentials-for-the-siebel"></a>Siebel の資格情報 で、サインオンを構成します。
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプター クライアント クライアントの資格情報を提供する必要があります。 アダプターは、Siebel システムでユーザーを認証し、接続を確立するために、これらの資格情報を使用します。  
  
 アダプターのクライアントは、デザイン時に資格情報または実行時に、クライアントに提供できます。 デザイン時に、メタデータを生成する資格情報が必要です。 実行時に、Siebel システムに対して操作を実行する資格情報が必要です。 このセクションでは、デザイン時および実行時にクライアントの資格情報を指定することに関する情報を提供します。  
  
## <a name="enter-the-client-credentials-at-design-time"></a>デザイン時にクライアントの資格情報を入力してください。  
 デザイン時にを使用して資格情報を指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。  
  
#### <a name="enter-client-credentials-using-consume-adapter-service-add-in"></a>アダプター サービスのアドインを使用してクライアントの資格情報を入力してください。  
  
1.  BizTalk プロジェクトを右クリックし、順にポイント**追加**、し、**生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプター サービスの使用**です。|  
    |**[テンプレート]**|をクリックして**アダプター サービスの使用**です。|  
  
3.  開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。  
  
4.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**siebelBinding**、順にクリック**構成**です。  
  
5.  **アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と Siebel システムへの接続にパスワードを指定します。  
  
6.  **[OK]**をクリックします。  
  
#### <a name="enter-client-credentials-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用してクライアントの資格情報を入力してください。  
  
1.  BizTalk プロジェクトを右クリックし、順にポイント**追加**、し、**生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプターを追加**です。|  
    |**[テンプレート]**|をクリックして**アダプター メタデータの追加**です。|  
  
3.  **[追加]**をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  
  
4.  アダプターの追加ウィザードで選択**Wcf-siebel**です。 コンピューターを選択して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。  
  
    > [!IMPORTANT]
    >  BizTalk で構成された Wcf-siebel ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。  
  
5.  **[次へ]**をクリックします。  
  
6.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**siebelBinding**、順にクリック**構成**です。  
  
7.  **アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と Siebel システムへの接続にパスワードを指定します。  
  
8.  **[OK]**をクリックします。  
  
## <a name="enter-client-credentials-at-run-time"></a>実行時にクライアントの資格情報を入力してください。  
 、実行時の構成の一部として、Wcf-custom または Wcf-siebel ポートでクライアントの資格情報を指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
#### <a name="enter-credentials-for-the-wcf-custom-port"></a>WCF カスタム ポートの資格情報を入力します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**. 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
4.  送信ポートの場合に、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、次のいずれかの操作します。  
  
    -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。  
  
    -   選択、**を使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。  
  
5.  **[OK]**をクリックします。  
  
> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]また、エンタープライズ シングル サインオン (ESSO) システムをサポートします。 ESSO は、のみシナリオでは、BizTalk、WCF アダプターは、ESSO 関連アプリケーションの認識を適用します。 BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [Siebel アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)です。
  
#### <a name="enter-credentials-for-the-wcf-siebel-port"></a>Wcf-siebel ポートの資格情報を入力します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  Wcf-siebel アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 手順については、次を参照してください。 [Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)です。  
  
3.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**. 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する Wcf-siebel ポートを選択し、をクリックして**構成**です。  
  
5.  トランスポートのプロパティ ダイアログ ボックスで、送信ポートをクリックして、**資格情報**タブし、次のいずれかの操作します。  
  
    -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。  
  
    -   選択、**を使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。  
  
6.  **[OK]**をクリックします。  
  
> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]また、エンタープライズ シングル サインオン (ESSO) システムをサポートします。 ESSO は、のみシナリオでは、BizTalk、WCF アダプターは、ESSO 関連アプリケーションの認識を適用します。 BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [Siebel アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)です。
  
## <a name="see-also"></a>参照  
[Siebel アダプターと BizTalk アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)