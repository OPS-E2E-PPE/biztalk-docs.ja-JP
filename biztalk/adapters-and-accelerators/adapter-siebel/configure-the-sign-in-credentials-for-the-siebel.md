---
title: Siebel の資格情報で、サインオンの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, specify credentials for the Siebel system at run time
- credentials, specifying
- how to, specify credentials for the Siebel system at design time
ms.assetid: a9fef2ba-c38e-44f7-84a3-b6a95d4dc210
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 865f7fe900d009db7ac79ba933f484cae3fd3e00
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371833"
---
# <a name="configure-the-sign-in-credentials-for-the-siebel"></a>Siebel の資格情報で、サインオンを構成します。
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプター クライアントのクライアント資格情報を提供する必要があります。 アダプターは、Siebel システムでユーザーを認証し、接続を確立するために、これらの資格情報を使用します。  

 アダプター クライアントは、資格情報をデザイン時または実行時に、クライアントに提供できます。 デザイン時に、メタデータを生成する資格情報が必要です。 実行時に、Siebel システムに対して操作を実行する資格情報が必要です。 このセクションでは、デザイン時および実行時にクライアントの資格情報を指定する方法の情報を提供します。  

## <a name="enter-the-client-credentials-at-design-time"></a>デザイン時にクライアントの資格情報を入力します。  
 デザイン時を使用して資格情報を指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。  

#### <a name="enter-client-credentials-using-consume-adapter-service-add-in"></a>Consume Adapter Service アドインを使用してクライアント資格情報を入力します。  

1.  BizTalk プロジェクトを右クリックし、**追加**、し、**生成した項目の追加**します。  

2.  **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|クリックして**アダプター サービスの使用**します。|  
    |**[テンプレート]**|クリックして**アダプター サービスの使用**します。|  

3.  開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。  

4.  **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**siebelBinding**、順にクリックします**構成**します。  

5.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と Siebel システムへの接続にパスワードを指定します。  

6.  **[OK]** をクリックします。  

#### <a name="enter-client-credentials-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用してクライアント資格情報を入力します。  

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

6. **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**siebelBinding**、順にクリックします**構成**します。  

7. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と Siebel システムへの接続にパスワードを指定します。  

8. **[OK]** をクリックします。  

## <a name="enter-client-credentials-at-run-time"></a>実行時にクライアントの資格情報を入力します。  
 実行時で Wcf-custom または Wcf-siebel ポート構成の一部としてクライアントの資格情報を指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

#### <a name="enter-credentials-for-the-wcf-custom-port"></a>WCF カスタム ポートの資格情報を入力します。  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**をクリックして、ポートを作成するアプリケーションを展開し**送信ポート**. 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

3. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  

4. 送信ポートので、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、 をクリックして、**資格情報**タブし、次のいずれかの操作を行います。  

   -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。  

   -   選択、**使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。  

5. **[OK]** をクリックします。  

> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] また、エンタープライズ シングル サインオン (ESSO) システムをサポートします。 ESSO は、WCF アダプターは ESSO 関連アプリケーションを認識する、BizTalk のシナリオでは適用のみです。 BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [Siebel アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)します。

#### <a name="enter-credentials-for-the-wcf-siebel-port"></a>Wcf-siebel ポートの資格情報を入力します。  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. Wcf-siebel アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、次を参照してください。 [Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)します。  

3. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**をクリックして、ポートを作成するアプリケーションを展開し**送信ポート**. 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

4. ポートのプロパティ ダイアログ ボックスから、**型**ボックスの一覧は、先ほど追加した Wcf-siebel ポートを選択し、順にクリックします**構成**します。  

5. トランスポートのプロパティ ダイアログ ボックスの送信ポートをクリックして、**資格情報**タブし、次のいずれかの操作を行います。  

   -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。  

   -   選択、**使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。  

6. **[OK]** をクリックします。  

> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] また、エンタープライズ シングル サインオン (ESSO) システムをサポートします。 ESSO は、WCF アダプターは ESSO 関連アプリケーションを認識する、BizTalk のシナリオでは適用のみです。 BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [Siebel アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)します。

## <a name="see-also"></a>参照  
[Siebel アダプターを使用した BizTalk アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)