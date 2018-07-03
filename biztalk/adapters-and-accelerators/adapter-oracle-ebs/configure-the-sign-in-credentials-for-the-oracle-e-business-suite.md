---
title: Oracle E-business suite のサインイン資格情報の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 743ced51-706b-4788-b5a8-e0ed8ffb3b48
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08081cc1e59181f3cd6aad0dfa532b060287d2ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978947"
---
# <a name="configure-the-sign-in-credentials-for-the-oracle-e-business-suite"></a>Oracle E-business suite のサインイン資格情報を構成します。
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントのクライアント資格情報を提供する必要があります。 アダプターは、Oracle E-business Suite でユーザーを認証して、接続を確立するために、これらの資格情報を使用します。  

 アダプター クライアントのクライアント資格情報の両方を使用する場合を提供できます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用する場合と、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 使用する場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]メタデータを生成する資格情報が必要です。 使用する場合、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、資格情報が Oracle E-business Suite で操作を実行するために必要です。  

> [!IMPORTANT]
>  Oracle E-business Suite または Oracle データベースを基になるは、資格情報を指定できます。 接続し、メタデータを生成するには、資格情報を指定できます。 ただし、Oracle E-business Suite の成果物を起動するための操作を実行中に、アプリケーションのコンテキストを呼び出したい Oracle E-business Suite のアプリケーションを設定する必要があるため Oracle E-business Suite の資格情報を指定する必要があります。 アプリケーション コンテキストの設定の詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  

 このセクションで、クライアントの資格情報を指定する方法について説明します[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

## <a name="specifying-credentials-from-visual-studio"></a>Visual Studio からの資格情報の指定  
 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して資格情報を指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。  

#### <a name="to-specify-credentials-using-consume-adapter-service-add-in"></a>Consume Adapter Service アドインを使用して資格情報を指定するには  

1.  BizTalk プロジェクトを右クリックし、**生成した項目の追加**します。  

2.  **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|クリックして**アダプター サービスの使用**します。|  
    |**[テンプレート]**|クリックして**アダプター サービスの使用**します。|  

3.  開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。  

4.  **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleEBSBinding**、順にクリックします**構成**.  

5.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**] タブとの間、**クライアント資格情報の種類**一覧で、[**ユーザー名**とユーザー名と、Oracle E-business Suite に接続するためのパスワードを指定します。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
    |**Oracle E-business Suite の資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**EBusiness** for Oracle E-business Suite の資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。 する必要がありますの Oracle データベースの資格情報を指定するこの例では、 **OracleUserName**と**OraclePassword**プロパティをバインドします。|  
    |**ClientCredentialType が「データベース」に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。|  
    |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。|  

6.  **[OK]** をクリックします。  

#### <a name="to-specify-credentials-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用して資格情報を指定するには  

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

7. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**] タブとの間、**クライアント資格情報の種類**一覧で、[**ユーザー名**とユーザー名と、Oracle E-business Suite に接続するためのパスワードを指定します。  


   |                                         プロパティ                                          |                                                                                                                                               目的                                                                                                                                                |
   |-------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                     **Oracle データベースの資格情報を使用して接続するには**                      |                                                                          指定、 **ClientCredentialType**プロパティをバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。                                                                          |
   |                 **Oracle E-business Suite の資格情報を使用して接続するには**                  | 指定、 **ClientCredentialType**プロパティをバインド**EBusiness** for Oracle E-business Suite の資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。 する必要がありますの Oracle データベースの資格情報を指定するこの例では、 **OracleUserName**と**OraclePassword**プロパティをバインドします。 |
   | **ClientCredentialType が「データベース」に設定されている場合は、Windows 認証を使用して接続するには**  |                                                                                                         「/」を指定、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。                                                                                                         |
   | **ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには** |                                       Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。                                       |


8. **[OK]** をクリックします。  

## <a name="specifying-credentials-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールからの資格情報の指定  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または Wcf-oracleebs ポートの構成の一部として、資格情報を指定する必要があります。  

#### <a name="to-specify-credentials-for-the-wcf-custom-port"></a>WCF カスタム ポートの資格情報を指定するには  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

3. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  

   > [!NOTE]
   >  受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。  

4. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。**バインドの種類**ドロップダウン リストで、 **oracleEBSBinding**します。  

5. 送信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。  

   -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Oracle E-business Suite に接続するためのパスワードを指定します。  

       |プロパティ|目的|  
       |--------------|----------------|  
       |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
       |**Oracle E-business Suite の資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**EBusiness** for Oracle E-business Suite の資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。 する必要がありますの Oracle データベースの資格情報を指定するこの例では、 **OracleUserName**と**OraclePassword**プロパティをバインドします。|  
       |**ClientCredentialType が「データベース」に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。|  
       |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。|  

   -   選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。  

6. 受信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他**タブをクリックし、次のいずれかの操作を行います。  

   -   選択**ユーザー アカウント**オプション、およびユーザー名と Oracle E-business Suite に接続するためのパスワードを指定します。  

       |プロパティ|目的|  
       |--------------|----------------|  
       |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
       |**Oracle E-business Suite の資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**EBusiness** for Oracle E-business Suite の資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。 する必要がありますの Oracle データベースの資格情報を指定するこの例では、 **OracleUserName**と**OraclePassword**プロパティをバインドします。|  
       |**ClientCredentialType が「データベース」に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。|  
       |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。|  

   -   選択**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。  

7. **[OK]** をクリックします。  

#### <a name="to-specify-credentials-for-the-wcf-oracleebs-port"></a>Wcf-oracleebs ポート用の資格情報を指定するには  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. Wcf-oracleebs アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、次を参照してください。 [、Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)します。  

3. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

4. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-oracleebs**、 をクリックし、**構成**します。  

   > [!NOTE]
   >  受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。  

5. ポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブ。**バインドの種類**ドロップダウン リストで、 **oracleEBSBinding**します。  

6. トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合は、クリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。  

   -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Oracle E-business Suite に接続するためのパスワードを指定します。  

       |プロパティ|目的|  
       |--------------|----------------|  
       |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
       |**Oracle E-business Suite の資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**EBusiness** for Oracle E-business Suite の資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。 する必要がありますの Oracle データベースの資格情報を指定するこの例では、 **OracleUserName**と**OraclePassword**プロパティをバインドします。|  
       |**ClientCredentialType が「データベース」に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。|  
       |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。|  

   -   選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。  

7. トランスポートのプロパティ ダイアログ ボックスで、受信ポートを作成する場合にクリックして、**他**タブをクリックし、次のいずれかの操作を行います。  

   -   選択**ユーザー アカウント**オプション、およびユーザー名と Oracle E-business Suite に接続するためのパスワードを指定します。  

       |プロパティ|目的|  
       |--------------|----------------|  
       |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
       |**Oracle E-business Suite の資格情報を使用して接続するには**|指定、 **ClientCredentialType**プロパティをバインド**EBusiness** for Oracle E-business Suite の資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。 する必要がありますの Oracle データベースの資格情報を指定するこの例では、 **OracleUserName**と**OraclePassword**プロパティをバインドします。|  
       |**ClientCredentialType が「データベース」に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。|  
       |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。|  

   -   選択**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。  

8. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
 [Oracle E-business Suite のアプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)   
 [Windows 認証を使用して Oracle E-business Suite に接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)