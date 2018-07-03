---
title: For Oracle E-business Suite 接続 URI の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2bb02b4-4ad6-4b07-b48a-8f9a47967ffc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6638e91616cb0e5134108aac0ed18ee844196ba7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991715"
---
# <a name="configure-the-connection-uri-for-oracle-e-business-suite"></a>For Oracle E-business Suite 接続 URI の構成します。
接続 URI は、Oracle E-business Suite への接続に必要なパラメーターを含む接続文字列です。 使用しているときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]で[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]メタデータを生成する、Oracle E-business Suite に接続するための URI を指定する必要があります。 使用して、オーケストレーションを構成するときに、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、操作を実行する Oracle E-business Suite に接続するための URI を指定する必要があります。  

## <a name="specifying-the-connection-uri-from-visual-studio"></a>接続を Visual Studio から URI を指定します。  
 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して接続 URI を指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。  

#### <a name="to-specify-the-connection-uri-using-consume-adapter-service-add-in"></a>Consume Adapter Service アドインを使用して、URI の接続を指定するには  

1. BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。  

2. **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  


   |    プロパティ    |             目的             |
   |----------------|------------------------------------|
   | **カテゴリ** | クリックして**アダプター サービスの使用**します。 |
   | **[テンプレート]**  | クリックして**アダプター サービスの使用**します。 |


3. 開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。  

4. **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleEBSBinding**、順にクリックします**構成**.  

5. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。**クライアント資格情報の種類**一覧で、 **Username**ユーザー名と、Oracle E-business Suite に接続するためのパスワードを指定します。  


   |                                         プロパティ                                          |                                                                                                                                               目的                                                                                                                                                |
   |-------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                     **Oracle データベースの資格情報を使用して接続するには**                      |                                                                          指定、 **ClientCredentialType**プロパティをバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。                                                                          |
   |                 **Oracle E-business Suite の資格情報を使用して接続するには**                  | 指定、 **ClientCredentialType**プロパティをバインド**EBusiness** for Oracle E-business Suite の資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。 する必要がありますの Oracle データベースの資格情報を指定するこの例では、 **OracleUserName**と**OraclePassword**プロパティをバインドします。 |
   | **ClientCredentialType が「データベース」に設定されている場合は、Windows 認証を使用して接続するには**  |                                                                                                         「/」を指定、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。                                                                                                         |
   | **ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには** |                                       Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。                                       |


6. をクリックして、 **URI プロパティ**タブをクリックし、さまざまなパラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[for Oracle E-business Suite 接続 URI を構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)します。  

7. をクリックして、**バインド プロパティ**タブをクリックし、バインドの値を指定、存在する場合、スキーマを生成する前に必要な。 バインド プロパティの詳細については、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  

8. **[OK]** をクリックします。  

#### <a name="to-specify-the-connection-uri-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用して、URI の接続を指定するには  

1. BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。  

2. **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  


   |    プロパティ    |           目的            |
   |----------------|---------------------------------|
   | **カテゴリ** |     クリックして**アダプターを追加**します。      |
   | **[テンプレート]**  | クリックして**アダプター メタデータの追加**します。 |


3. **[追加]** をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  

4. [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、 **Wcf-oracleebs**します。 BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。  

   > [!IMPORTANT]
   >  BizTalk で構成された Wcf-oracleebs ポート既にある場合は、ポートの一覧から、ポートを選択します。  

5. **[次へ]** をクリックします。  

6. **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleEBSBinding**、順にクリックします**構成**.  

7. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。**クライアント資格情報の種類**一覧で、 **Username**ユーザー名と、Oracle E-business Suite に接続するためのパスワードを指定します。  


   |                                         プロパティ                                          |                                                                                                                                               目的                                                                                                                                                |
   |-------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                     **Oracle データベースの資格情報を使用して接続するには**                      |                                                                          指定、 **ClientCredentialType**プロパティをバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。                                                                          |
   |                 **Oracle E-business Suite の資格情報を使用して接続するには**                  | 指定、 **ClientCredentialType**プロパティをバインド**EBusiness** for Oracle E-business Suite の資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。 する必要がありますの Oracle データベースの資格情報を指定するこの例では、 **OracleUserName**と**OraclePassword**プロパティをバインドします。 |
   | **ClientCredentialType が「データベース」に設定されている場合は、Windows 認証を使用して接続するには**  |                                                                                                         「/」を指定、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。                                                                                                         |
   | **ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには** |                                       Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。                                       |


8. をクリックして、 **URI プロパティ**タブをクリックし、さまざまなパラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[for Oracle E-business Suite 接続 URI を構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)します。  

9. をクリックして、**バインド プロパティ**タブをクリックし、バインドの値を指定、存在する場合、スキーマを生成する前に必要な。 バインド プロパティの詳細については、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  

    > [!NOTE]
    >  既存を選択した場合は、Wcf-oracleebs 送信ポート、バインディングのプロパティを指定する必要があります。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。 このような場合、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。 ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。  

10. **[OK]** をクリックします。  

## <a name="specifying-the-connection-uri-from-the-biztalk-server-administration-console"></a>接続を BizTalk Server 管理コンソールから URI を指定します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または Wcf-oracleebs ポートの構成の一部として、接続 URI を指定する必要があります。  

#### <a name="to-specify-the-connection-uri-for-the-wcf-custom-port"></a>WCF カスタム ポートの接続 URI を指定するには  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

3. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  

   > [!NOTE]
   >  受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。  

4. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。  

5. **アドレス (URI)** テキスト ボックスで、Oracle E-business Suite に接続する接続 URI を指定します。 接続 URI の詳細についてはの[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[for Oracle E-business Suite 接続 URI を構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)します。  

6. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。**バインドの種類**ドロップダウン リストで、 **oracleEBSBinding**します。  

7. 送信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。  

   -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Oracle E-business Suite に接続するためのパスワードを指定します。  

       |プロパティ|目的|  
       |--------------|----------------|  
       |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
       |**Oracle E-business Suite の資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**EBusiness** for Oracle E-business Suite の資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。 する必要がありますの Oracle データベースの資格情報を指定するこの例では、 **OracleUserName**と**OraclePassword**プロパティをバインドします。|  
       |**ClientCredentialType が「データベース」に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。|  
       |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。|  

   -   選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。  

8. 受信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他**タブをクリックし、次のいずれかの操作を行います。  

   -   選択**ユーザー アカウント**オプション、およびユーザー名と Oracle E-business Suite に接続するためのパスワードを指定します。  

       |プロパティ|目的|  
       |--------------|----------------|  
       |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
       |**Oracle E-business Suite の資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**EBusiness** for Oracle E-business Suite の資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。 する必要がありますの Oracle データベースの資格情報を指定するこの例では、 **OracleUserName**と**OraclePassword**プロパティをバインドします。|  
       |**ClientCredentialType が「データベース」に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。|  
       |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。|  

   -   選択**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。  

9. **[OK]** をクリックします。  

#### <a name="to-specify-the-connection-uri-for-the-wcf-oracleebs-port"></a>Wcf-oracleebs ポートの接続 URI を指定するには  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. Wcf-oracleebs アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、次を参照してください。 [、Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)します。  

3. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

4. ポートのプロパティ ダイアログ ボックスから、**型**一覧から、以前では、追加し、をクリックし、選択、Wcf-oracleebs アダプター**構成**します。  

   > [!NOTE]
   >  受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。  

5. トランスポートのプロパティ ダイアログ ボックスでをクリックして、**全般**タブ。  

6. をクリックして、**構成**ボタンをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[for Oracle E-business Suite 接続 URI を構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)します。  

7. トランスポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブし、バインドのプロパティの値を指定します。  

   > [!NOTE]
   >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。 たとえば、通知に関連するバインドのプロパティは通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときに使用できませんなりました。  

8. トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合は、クリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。  

   -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Oracle E-business Suite に接続するためのパスワードを指定します。  

       |プロパティ|目的|  
       |--------------|----------------|  
       |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
       |**Oracle E-business Suite の資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**EBusiness** for Oracle E-business Suite の資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。 する必要がありますの Oracle データベースの資格情報を指定するこの例では、 **OracleUserName**と**OraclePassword**プロパティをバインドします。|  
       |**ClientCredentialType が「データベース」に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。|  
       |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。|  

   -   選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。  

9. トランスポートのプロパティ ダイアログ ボックスで、受信ポートを作成する場合にクリックして、**他**タブをクリックし、次のいずれかの操作を行います。  

    -   選択**ユーザー アカウント**オプション、およびユーザー名と Oracle E-business Suite に接続するためのパスワードを指定します。  

        |プロパティ|目的|  
        |--------------|----------------|  
        |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
        |**Oracle E-business Suite の資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**EBusiness** for Oracle E-business Suite の資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。 する必要がありますの Oracle データベースの資格情報を指定するこの例では、 **OracleUserName**と**OraclePassword**プロパティをバインドします。|  
        |**ClientCredentialType が「データベース」に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。|  
        |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。|  

    -   選択**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。  

10. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
 [Oracle E-business Suite のアプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)   
 [Windows 認証を使用して Oracle E-business Suite に接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)