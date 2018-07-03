---
title: Siebel アダプターの接続 URI の構成 |Microsoft Docs
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
ms.openlocfilehash: 070925b09cf4e4896097be1aa88bc57fcd625626
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992395"
---
# <a name="configure-the-connection-uri-for-the-siebel-adapter"></a>Siebel アダプターの接続 URI を構成します。
接続 URI は、Siebel システムに接続する接続文字列です。 接続 URI には、Siebel システムとの接続を確立するために必要なさまざまなパラメーターが含まれています。 この接続のデザイン時と実行時の両方に URI を指定する必要があります。 デザイン時に、メタデータを生成する Siebel システムへの接続の URI を指定する必要があります。 実行時に、操作を実行する Siebel システムへの接続に URI を指定する必要があります。  

## <a name="enter-the-connection-uri-at-design-time"></a>デザイン時の接続 URI を入力します。  
 デザイン時に、使用して接続 URI を指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。  

#### <a name="enter-the-connection-uri-using-consume-adapter-service-add-in"></a>接続 Consume Adapter Service アドインを使用して URI を入力します。  

1. BizTalk プロジェクトを右クリックし、**追加**、し、**生成した項目の追加**します。  

2. **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  


   |    プロパティ    |             目的             |
   |----------------|------------------------------------|
   | **カテゴリ** | クリックして**アダプター サービスの使用**します。 |
   | **[テンプレート]**  | クリックして**アダプター サービスの使用**します。 |


3. 開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。  

4. **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**siebelBinding**、 をクリック**構成**.  

5. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **Username**ユーザー名と Siebel システムへの接続にパスワードを指定します。  

6. **アダプターの構成**ダイアログ ボックスで、をクリックして、 **URI プロパティ**タブし、さまざまなパラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI の作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。  

7. **アダプターの構成**ダイアログ ボックスで、 をクリックして、**バインドのプロパティ**タブし、バインドの値を指定、存在する場合は、スキーマを生成する前に指定するために必要です。 バインド プロパティの詳細については、次を参照してください。 [for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。  

8. **[OK]** をクリックします。  

#### <a name="enter-the-connection-uri-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用して、URI の接続を入力します。  

1. BizTalk プロジェクトを右クリックし、**追加**、し、**生成した項目の追加**します。  

2. **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  


   |    プロパティ    |           目的            |
   |----------------|---------------------------------|
   | **カテゴリ** |     クリックして**アダプターを追加**します。      |
   | **[テンプレート]**  | クリックして**アダプター メタデータの追加**します。 |


3. **[追加]** をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  

4. アダプターの追加ウィザードで選択**Wcf-siebel**します。 コンピューターを選択します。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。  

   > [!IMPORTANT]
   >  BizTalk で構成された Wcf-siebel ポート既にある場合からポートを選択して、**ポート**一覧。  

5. **[次へ]** をクリックします。  

6. **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**siebelBinding**、 をクリック**構成**.  

7. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **Username**ユーザー名と Siebel システムへの接続にパスワードを指定します。  

8. **アダプターの構成**ダイアログ ボックスで、をクリックして、 **URI プロパティ**タブし、さまざまなパラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI の作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。  

9. **アダプターの構成**ダイアログ ボックスで、 をクリックして、**バインドのプロパティ**タブし、バインドの値を指定、存在する場合は、スキーマを生成する前に指定するために必要です。 バインド プロパティの詳細については、次を参照してください。 [for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。  

    > [!NOTE]
    >  既存の WCF Siebel 送信ポートを選択した場合は、バインドのプロパティを指定する必要がありますできません。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。 このような場合、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。 ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。  

10. **[OK]** をクリックします。  

## <a name="enter-the-connection-uri-at-run-time"></a>実行時に、接続 URI を入力します。  
 実行時にで Wcf-custom または Wcf-siebel ポート構成の一部として URI を指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

#### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a>WCF カスタム ポートの接続 URI を入力します。  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、ポート、およびクリックを作成するアプリケーションを展開し**送信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

3. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  

4. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。  

5. **アドレス (URI)** テキスト ボックスで、接続、Siebel システムへの接続に URI を指定します。 接続 URI の詳細についてはの[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI の作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。  

6. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。**バインドの種類**ドロップダウン リストで、 **siebelBinding**します。  

7. 送信ポートを作成する、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、次のいずれかの操作を行います。  

   1.  選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。  

   2.  選択、**使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。  

8. **[OK]** をクリックします。  

#### <a name="enter-the-connection-uri-for-the-wcf-siebel-port"></a>Wcf-siebel ポートの接続 URI を入力します。  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. Wcf-siebel アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、次を参照してください。 [Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)します。  

3. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、ポート、およびクリックを作成するアプリケーションを展開し**送信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

4. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した Wcf-siebel アダプターを選択してをクリックして**構成**します。  

5. トランスポートのプロパティ ダイアログ ボックスでをクリックして、**全般**タブ。  

6. をクリックして、**構成**ボタンをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI の作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。  

7. トランスポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブし、バインドのプロパティの値を指定します。  

8. 送信ポートを作成する、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、次のいずれかの操作を行います。  

   1.  選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。  

   2.  選択、**使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。  

9. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
[Siebel アダプターを使用した BizTalk アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)