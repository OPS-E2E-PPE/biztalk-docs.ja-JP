---
title: Oracle データベース アダプターの接続 URI の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI, specifying at design time
- connection URI, specifying at run time
ms.assetid: 9f302b67-0bcc-44d1-9517-10d402873540
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 849adf16faa96726fb3d182930be8f4965eb180d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007211"
---
# <a name="configure-the-connection-uri-for-the-oracle-database-adapter"></a>Oracle データベース アダプターの接続 URI の構成します。
接続 URI は、Oracle データベースへの接続に必要なパラメーターを含む接続文字列です。 使用しているときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]で[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]メタデータを生成する Oracle データベースに接続する URI を指定する必要があります。 使用して、オーケストレーションを構成するときに、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、操作を実行する Oracle データベースに接続する URI を指定する必要があります。  

## <a name="specifying-the-connection-uri-from-visual-studio"></a>接続を Visual Studio から URI を指定します。  
 Visual studio を使用して資格情報を指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。  

#### <a name="to-specify-the-connection-uri-using-consume-adapter-service-add-in"></a>Consume Adapter Service アドインを使用して接続 URI を指定するには  

1. BizTalk プロジェクトを右クリックし、**生成した項目の追加**します。  

2. **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  


   |    プロパティ    |             目的             |
   |----------------|------------------------------------|
   | **カテゴリ** | クリックして**アダプター サービスの使用**します。 |
   | **[テンプレート]**  | クリックして**アダプター サービスの使用**します。 |


3. 開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。  

4. **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleDBBinding**、 をクリック**構成**します。  

5. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と Oracle データベースに接続するためのパスワードを指定します。  

   -   Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。  

   -   Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。  

6. をクリックして、 **URI プロパティ**タブをクリックし、さまざまなパラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。  

7. をクリックして、**バインド プロパティ**タブをクリックし、バインドの値を指定、存在する場合、スキーマを生成する前に必要な。 バインド プロパティの詳細については、次を参照してください。 [for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。  

8. **[OK]** をクリックします。  

#### <a name="to-specify-the-connection-uri-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用して接続 URI を指定するには  

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

8. をクリックして、 **URI プロパティ**タブをクリックし、さまざまなパラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。  

9. をクリックして、**バインド プロパティ**タブをクリックし、バインドの値を指定、存在する場合、スキーマを生成する前に必要な。 バインド プロパティの詳細については、次を参照してください。 [for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。  

10. **[OK]** をクリックします。  

## <a name="specifying-the-connection-uri-from-the-biztalk-server-administration-console"></a>接続を BizTalk Server 管理コンソールから URI を指定します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または Wcf-oracledb ポートの構成の一部として、資格情報を指定する必要があります。  

#### <a name="to-specify-the-connection-uri-for-the-wcf-custom-port"></a>WCF カスタム ポートの接続 URI を指定するには  

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

#### <a name="to-specify-the-connection-uri-for-the-wcf-oracledb-port"></a>Wcf-oracledb ポートの接続 URI を指定するには  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. Wcf-oracledb アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、次を参照してください。[を BizTalk Server 管理コンソールの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)します。  

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