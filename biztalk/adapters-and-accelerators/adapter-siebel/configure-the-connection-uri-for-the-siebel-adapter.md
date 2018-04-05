---
title: Siebel アダプターの接続 URI の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI, specifying
ms.assetid: b89b60e9-0f3b-4305-865e-9d3b40d04648
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8017e5ccd2c033f26b03fe7443245d2fb88be960
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-connection-uri-for-the-siebel-adapter"></a>Siebel アダプターの接続 URI を構成します。
接続 URI は、Siebel システムに接続する接続文字列です。 接続 URI には、Siebel システムとの接続を確立するために必要なさまざまなパラメーターが含まれています。 この接続の両方で、デザイン時および実行時の URI を指定する必要があります。 デザイン時に、メタデータを生成する Siebel システムへの接続に URI を指定する必要があります。 実行時に、操作を実行する Siebel システムへの接続に URI を指定する必要があります。  
  
## <a name="enter-the-connection-uri-at-design-time"></a>デザイン時に、接続 URI を入力してください。  
 デザイン時の接続を使用して URI を指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。  
  
#### <a name="enter-the-connection-uri-using-consume-adapter-service-add-in"></a>接続 アダプター サービスのアドインを使用して URI を入力してください。  
  
1.  BizTalk プロジェクトを右クリックし、順にポイント**追加**、し、**生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプター サービスの使用**です。|  
    |**[テンプレート]**|をクリックして**アダプター サービスの使用**です。|  
  
3.  開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。  
  
4.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**siebelBinding**、 をクリック**構成**.  
  
5.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **Username**ユーザー名と Siebel システムへの接続にパスワードを指定します。  
  
6.  **アダプターの構成**ダイアログ ボックスで、をクリックして、 **URI プロパティ**タブおよび他のパラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI を作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。  
  
7.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ** タブの値を指定します、バインディング、存在する場合は、スキーマを生成する前に指定する必要です。 バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインド プロパティ読む](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。  
  
8.  **[OK]**をクリックします。  
  
#### <a name="enter-the-connection-uri-using-add-adapter-metadata-wizard"></a>入力アダプター メタデータの追加ウィザードを使用して、URI の接続  
  
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
  
6.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**siebelBinding**、 をクリック**構成**.  
  
7.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **Username**ユーザー名と Siebel システムへの接続にパスワードを指定します。  
  
8.  **アダプターの構成**ダイアログ ボックスで、をクリックして、 **URI プロパティ**タブおよび他のパラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI を作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。  
  
9. **アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ** タブの値を指定します、バインディング、存在する場合は、スキーマを生成する前に指定する必要です。 バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインド プロパティ読む](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。  
  
    > [!NOTE]
    >  既存の WCF Siebel 送信ポートを選択した場合、バインドのプロパティを指定する必要はありません。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。 このような場合、メタデータの生成中にバインドのプロパティの新しい値をデザイン時に使用されます。 ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。  
  
10. **[OK]**をクリックします。  
  
## <a name="enter-the-connection-uri-at-run-time"></a>実行時に、接続 URI を入力してください。  
 実行時に、Wcf-custom または Wcf-siebel のポート設定の一部として URI を指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
#### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a>WCF カスタム ポートの接続 URI を入力してください。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポート、およびクリックを作成するアプリケーションの順に展開し、**送信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
4.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。  
  
5.  **アドレス (URI)**テキスト ボックスで、接続、Siebel システムへの接続に URI を指定します。 詳細については、接続 URI の[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI を作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。  
  
6.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。**バインディングの種類**ドロップダウン リストで、 **siebelBinding**です。  
  
7.  送信ポートを作成する、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、次のいずれかの操作します。  
  
    1.  選択、**シングル サインオンを使用しない**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。  
  
    2.  選択、**を使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。  
  
8.  **[OK]**をクリックします。  
  
#### <a name="enter-the-connection-uri-for-the-wcf-siebel-port"></a>Wcf-siebel ポートの接続 URI を入力してください。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  Wcf-siebel アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 手順については、次を参照してください。 [Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)です。  
  
3.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポート、およびクリックを作成するアプリケーションの順に展開し、**送信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する Wcf-siebel アダプターを選択し、をクリックして**構成**です。  
  
5.  トランスポートのプロパティ ダイアログ ボックスをクリックして、**全般**タブです。  
  
6.  クリックして、**構成**ボタンをクリックし、接続パラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI を作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。  
  
7.  トランスポートのプロパティ ダイアログ ボックスをクリックして、**バインディング**タブし、バインドのプロパティの値を指定します。  
  
8.  送信ポートを作成する、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、次のいずれかの操作します。  
  
    1.  選択、**シングル サインオンを使用しない**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。  
  
    2.  選択、**を使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。  
  
9. **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
[Siebel アダプターと BizTalk アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)