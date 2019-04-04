---
title: Oracle データベースの資格情報で、サインオンの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Enter the credentials
helpviewer_keywords:
- credentials, specifying at run time
- credentials, specifying at design time
ms.assetid: d8f62829-ce77-4d82-a411-2eeefb6fe75a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6b19b79d05a925f02938669693c5eb92e9185b0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995659"
---
# <a name="configure-the-sign-in-credentials-for-the-oracle-database"></a>Oracle データベースの資格情報で、サインオンを構成します。
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントのクライアント資格情報を提供する必要があります。 アダプターは、Oracle データベースがあるユーザーを認証して、接続を確立するために、これらの資格情報を使用します。  

 アダプター クライアントのクライアント資格情報の両方を使用する場合を提供できます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用する場合と、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 使用する場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]メタデータを生成する資格情報が必要です。 使用する場合、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、資格情報が Oracle データベースで操作を実行するために必要です。 このトピックではクライアント資格情報を指定する方法について[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

## <a name="specifying-client-credentials-from-visual-studio"></a>Visual Studio からのクライアント資格情報の指定  
 Visual studio を使用して資格情報を指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。  

#### <a name="to-specify-credentials-using-consume-adapter-service-add-in"></a>Consume Adapter Service アドインを使用して資格情報を指定するには  

1.  BizTalk プロジェクトを右クリックし、**生成した項目の追加**します。  

2.  **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|クリックして**アダプター サービスの使用**します。|  
    |**[テンプレート]**|クリックして**アダプター サービスの使用**します。|  

3.  開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。  

4.  **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleDBBinding**、 をクリック**構成**します。  

5.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と Oracle データベースに接続するためのパスワードを指定します。  

    -   Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。  

    -   Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。  

6.  **[OK]** をクリックします。  

#### <a name="to-specify-credentials-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用して資格情報を指定するには  

1. BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。  

2. **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  


   |    プロパティ    |           目的            |
   |----------------|---------------------------------|
   | **カテゴリ** |     クリックして**アダプターを追加**します。      |
   | **[テンプレート]**  | クリックして**アダプター メタデータの追加**します。 |


3. **[追加]** をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  

4. [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、 **Wcf-oracledb**します。 コンピューターを選択します。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。  

   > [!IMPORTANT]
   >  BizTalk で構成された Wcf-oracledb ポート既にある場合からポートを選択して、**ポート**一覧。  

5. **[次へ]** をクリックします。  

6. **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleDBBinding**、順にクリックします**構成**.  

7. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**] タブとの間、**クライアント資格情報の種類**一覧で、[**ユーザー名**とユーザー名と Oracle データベースに接続するためのパスワードを指定します。  

   -   Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。  

   -   Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。  

8. **[OK]** をクリックします。  

## <a name="specifying-client-credentials-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールからクライアント資格情報の指定  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または Wcf-oracledb ポートの構成の一部として、資格情報を指定する必要があります。  

#### <a name="to-specify-client-credentials-for-the-wcf-custom-port"></a>クライアントの資格情報、WCF カスタム ポートを指定するには  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

3. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  

4. 送信ポートので、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、 をクリックして、**資格情報**タブし、次のいずれかの操作を行います。  

   -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Oracle データベースに接続するためのパスワードを指定します。  

       -   Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。  

       -   Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。  

   -   選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。  

5. 受信ポートので、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他** タブで、次のいずれかを実行し、。  

   -   選択**ユーザー アカウント**オプション、およびユーザー名と Oracle データベースに接続するためのパスワードを指定します。  

       -   Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。  

       -   Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。  

   -   選択**関連アプリケーションから資格情報を Get**オプション、および関連アプリケーションを指定します。  

6. **[OK]** をクリックします。  

#### <a name="to-specify-credentials-for-the-wcf-oracledb-port"></a>Wcf-oracledb ポート用の資格情報を指定するには  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. Wcf-oracledb アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、[を BizTalk Server 管理コンソールの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)を参照してください。  

3. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

4. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-oracledb**、 をクリックし、**構成**します。  

   > [!NOTE]
   >  受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。  

5. ポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブ。**バインドの種類**ドロップダウン リストで、 **oracleDBBinding**します。  

6. トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合は、クリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。  

   -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Oracle データベースに接続するためのパスワードを指定します。  

       -   Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。  

       -   Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。  

   -   選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。  

7. トランスポートのプロパティ ダイアログ ボックスで、受信ポートを作成する場合にクリックして、**他**タブをクリックし、次のいずれかの操作を行います。  

   -   選択**ユーザー アカウント**オプション、およびユーザー名と Oracle データベースに接続するためのパスワードを指定します。  

       -   Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。  

       -   Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。  

   -   選択**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。  

8. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)   
 [Windows 認証を使用して Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)