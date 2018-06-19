---
title: HTTPSSO (BizTalk Server サンプル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- SSO, examples
- SSO, HTTP adapters
- examples, HTTP adapters
- HTTP adapters, SSO
- examples, SSO
ms.assetid: 322360df-81d2-4a73-9512-bda9382351a2
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41956d9e10cba87e0e1a1f44d49dd8ec8b6039bc
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
ms.locfileid: "25974272"
---
# <a name="httpsso-biztalk-server-sample"></a>HTTPSSO (BizTalk Server サンプル)
HTTPSSO サンプルでは、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP アダプタでエンタープライズ シングル サインオン (SSO) を使用する方法を示します。  
  
> [!NOTE]
>  このサンプルは、64 ビット オペレーティング システムに対応していません。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、SSO と BizTalk HTTP 送信アダプターおよび受信アダプターを使用して、SSO により、Windows が資格情報を認証した後に、ユーザーが Microsoft Windows 以外のシステムにログオンするために他の資格情報を指定せずに済む方法をシミュレートするエンドツーエンド シナリオを示します。  
  
 このサンプルでは、SSO の管理モジュールとマッピング モジュールを使用して、SSO の相互運用機能クライアント DLL により、関連アプリケーションと SSO マッピングも作成します。  
  
 エンドツーエンド シナリオの次の側面を実装することで、SSO の使用を示します。  
  
-   Windows 統合認証を使用するように構成された、Microsoft インターネット インフォメーション サービス (IIS) 仮想ディレクトリで表されるユーザー インターフェイス。  
  
-   基本認証を使用するように構成された IIS 仮想ディレクトリで表されるバックエンド システム。  
  
-   SQL サンプル データベース Northwind で表されるバックエンド データベース。  
  
 このサンプルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と SSO がインストールされていることを前提としています。 管理者特権が必要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]IIS、SSO、および COM + は Windows XP Professional にします。 SSO 管理者、BizTalk Server 管理者、および BizTalk 分離ホスト ユーザーの各 Windows グループのメンバであることも必要です。  
  
 このサンプルを効果的に使用するには、SSO と BizTalk HTTP アダプタに関する十分な知識があることを前提としています。 たとえば、SSO のコンテキストで関連アプリケーションとは何かを理解しておく必要があります。 これらのトピックについては、次を参照してください。[を使用して SSO](../core/using-sso.md)です。 参照してください[HTTP アダプター](../core/http-adapter.md)です。  
  
 構成が完了すると、このサンプルは次のように動作します。  
  
1.  クリックすると、 **完了** でこのサンプルのユーザー インターフェイスを構成するウィザード アプリケーション、Internet Explorer のインスタンスが起動し、BizTalk HTTP Receive DLL の URL を渡します。  
  
2.  BizTalk Server は SSO を利用して、基本認証で構成された IIS 仮想ディレクトリのファイル EmployeeData.aspx に HTTP 要求を効率的に転送します。 この ASPX ファイルは、Windows 以外のバックエンド システムへのエントリ ポイントをシミュレートします。 SSO を使用しているために、HTTP 要求には、シミュレートされたバックエンド システムへのログオン アカウントをシミュレートする構成済みの資格情報が含まれます。  
  
3.  ASPX ファイルは、変更された SQL サンプル データベース Northwind にアクセスし、シミュレートされたバックエンド システム資格情報に対応する従業員データを取得します。  
  
4.  ASPX ファイルは、取得された従業員データを HTTP 応答で返します。  
  
5.  BizTalk Server は HTTP 応答を Internet Explorer にルーティングし、Internet Explorer は返された従業員データをユーザーに表示します。  
  
 BizTalk Server と SSO を省略し、ファイル EmployeeData.aspx を直接参照すると、[Windows] ダイアログ ボックスが表示され、資格情報を要求されます。  
  
 コマンド ライン ユーティリティ ssomanage.exe を使用して関連アプリケーションやユーザー マッピングの作成など、SSO を構成する方法を示すサンプルについては、次を参照してください。[管理 (BizTalk Server サンプル)](../core/manage-biztalk-server-sample.md)です。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>\SSO\HTTPSSO\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|AssemblyInfo.cs、SsoSample.csproj|この HTTP SSO サンプルのプロジェクト ファイルと関連ファイルです。|  
|SsoSample.cs|このサンプルの多くを構成する HTTP SSO グラフィカル アプリケーションの最上位の Microsoft Visual C# ソース ファイルです。 このファイルには、という名前のクラス内の SSO 構成コードが含まれています。 **SsoConfigurator** が最終的にこのサンプルのポイント。|  
|\Scripts フォルダー内のファイル:<br /><br /> EmployeeData.aspx|従業員が直接または SSO を使用して個人データを表示する要求を開始したときに、バックエンド データベース (この場合は SQL Northwind データベース) へのアクセスと照会に使用されます。|  
|\Scripts フォルダー内のファイル:<br /><br /> ValidateUser.aspx|ユーザーを検証し、直接または SSO を使用してそのユーザーが検証されたかどうかを報告する単純なテストです。|  
|\UI フォルダー内のファイル:<br /><br /> AddApplication.cs、AddApplication.resx、AddMapping.cs、AddMapping.resx、App.ico、BtsPage.cs、BtsPage.resx、ExecutePage.cs、ExecutePage.resx、FinishPage.cs、FinishPage.resx、IisPage.cs、IisPage.resx、InfoPage.cs、InfoPage.resx、PageBase.cs、PageBase.resx、SsoPage.cs、SsoPage.resx、SsoSampleWizard.cs、SsoSampleWizard.resx、WelcomePage.cs、WelcomePage.resx、WorkPage.cs、WorkPage.resx|このサンプルの多くを構成する HTTP SSO グラフィカル アプリケーションの補助 Visual C# ソース ファイル、および関連する XML 形式のリソース ファイルです。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
  
#### <a name="to-build-and-initialize-the-httpsso-sample"></a>HTTPSSO サンプルをビルドして初期化するには  
  
1.  Microsoft インターネット インフォメーション サービス (IIS) が基本認証に使用できるローカル Windows アカウントを作成します。 SSO は、Windows ドメイン アカウントをこのローカル Windows アカウントにマップします。 たとえば、自分の姓を使用してローカル Windows アカウントを作成します。  
  
    > [!NOTE]
    >  ドメイン コントローラ上で実行している場合は、ドメイン アカウントを作成し、ログオンしたドメイン アカウントをこのアカウントにマップできます。  
  
2.  Microsoft SQL Server の Enterprise Manager を使用して開きます、 **従業員** 、Northwind サンプル データベースのテーブルが表示され、作成したサンプル データ、さまざまな列を含むローカルの Windows アカウントに対応する行を追加します。 Employees テーブルの LastName 列に追加した値は、手順 1. で追加したローカル Windows アカウントのユーザー名と同じである必要があります。  
  
3.  ASP.NET アカウント (ASPNET) に Northwind データベースの読み取り特権があることを確認します。  
  
4.  Visual Studio を使用して、プロジェクト ファイル SsoSample.csproj を開きます。  
  
5.  **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。  
  
    > [!NOTE]
    >  ビルドを続行する前に、ソリューションを保存するように要求されます。  
  
     プロジェクトの次の BizTalk アセンブリ参照が見つからない場合は、アセンブリ参照を削除し、表示された場所から再追加してから、もう一度ビルドします。  
  
    -   **Microsoft.BizTalk.ExplorerOM**します。 既定では、Microsoft.BizTalk.ExplorerOM.dll ファイルは、フォルダーにあります[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Developer Tools\\です。  
  
    -   **Microsoft.BizTalk.SSOClient.Interop**します。 既定では、Microsoft.BizTalk.Interop.SSOClient.dll ファイル フォルダーにある、 \< *ProgramFiles*\>でのシングル サインオン \Common Files\Enterprise\\です。  
  
     これにより、次のフォルダに実行可能ファイル SsoSample.exe が作成されます。  
  
     \<*パスのサンプル*\>\SSO\HTTPSSO\bin\Debug\  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
> [!NOTE]
>  ワーカー プロセス分離モードを使用して IIS 6.0 でこのサンプルを実行すると、両方の仮想ディレクトリに対してアプリケーション プールが作成されます。 Windows アカウントでこれらの 2 つのアプリケーション プールの ID を手動で構成する必要があります (ID はインターネット インフォメーション サービス マネージャで構成できます)。  
  
#### <a name="to-run-the-httpsso-sample"></a>HTTPSSO サンプルを実行するには  
  
1.  次のフォルダにある実行可能ファイル SsoSample.exe を実行します。  
  
     \<*パスのサンプル*\>\SSO\HTTPSSO\bin\Debug\  
  
     このサンプルのウィザードが開きます。  
  
2.  クリックして [ようこそ] ページには、IIS、SSO、および BizTalk を構成するため、既定の設定を受け入れる **次**します。  
  
3.  [IIS の構成] ページで、作成、およびをクリックする 2 つの IIS 仮想ディレクトリの既定の設定を受け入れる **次**します。  
  
4.  SSO 構成 ページを使用してアクセスされる関連アプリケーション用の既定の設定を受け入れる、 **アプリケーションの追加**  ボタンをクリックします。  
  
5.  SSO 構成 ページで、ほとんどのユーザー マッピングの既定の設定を受け入れるを使用してアクセス、 **追加マッピング**  ボタンをクリックします。 このサンプルをビルドおよび初期化したときに追加したローカル Windows アカウントに基づいて、次の 2 つの設定に値を指定します。  
  
    |設定|値|  
    |-------------|-----------|  
    |外部ユーザー名|追加したローカルの Windows ユーザー アカウント名に設定されます。|  
    |外部ユーザーのパスワード|追加したローカルの Windows ユーザー アカウントのパスワードに設定されます。|  
  
6.  SSO の構成 ページで、クリックして **次**します。  
  
7.  [BizTalk 構成] ページで、送信の既定の設定をそのまま使用し、受信ポート、および、クリックして **次**します。  
  
    > [!NOTE]
    >  既定の送信ポート設定を変更する **EmployeeData.aspx** に **ValidateUser.aspx** Northwinds SQL データベースの Employee テーブルから取得されたサンプル データではなく、単純なユーザー検証を表示するかどうか。 クリックすると、ブラウザーに表示される出力の種類の変更をこの変更を加えたり **完了** 手順 9. でします。  
  
8.  実行される IIS、SSO、および BizTalk の各構成に対応する状態メッセージを確認します。 このフェーズで実行されるコードを見つけることができます、 **IisConfigurator**, 、**SsoConfigurator**, 、および **BtsConfigurator** ファイル SsoSample.cs で定義されているクラス。 構成が完了したら **次**します。  
  
9. ウィザード アプリケーションの最後のページ上の既定の設定を受け入れる**でブラウザーを開始**(チェック ボックスがオンと URL を使用してテキスト ボックスhttp://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll? <message/>)、をクリックし、**完了**です。  
  
     Internet Explorer のインスタンスが開き、Northwinds SQL データベースの Employee テーブルに追加した従業員データのサンプルが表示されます。  
  
 比較のために、BizTalk と SSO を省略し、次の ASPX ファイルのいずれかを直接参照します。  
  
-   http://localhost/SsoSampleServerApplication/ValidateUser.aspx  
  
-   http://localhost/SsoSampleServerApplication/EmployeeData.aspx  
  
 どちらの場合も、BizTalk と SSO を省略しているため、IIS から認証情報を要求されます (前に作成したローカル Windows アカウントの情報を使用します)。  
  
## <a name="comments"></a>コメント  
 SsoSample.exe ウィザード アプリケーションは、2 つの IIS 仮想ディレクトリを構成します。  
  
-   最初の仮想ディレクトリは Windows 統合認証で構成され、BizTalk HTTP 受信 ISAPI 拡張に対応します。 次のフォルダにある .dll ファイル BTSHTTPReceive.dll に関連付ける必要があります。  
  
     \<*インストール パス*\>\HttpReceive  
  
-   2 番目の仮想ディレクトリは基本認証で構成され、ユーザーを認証するためにユーザー ID とパスワードを受け取るバックエンド システムをシミュレートします。 次のフォルダにある ASPX ファイル ValidateUser.aspx と EmployeeData.aspx のいずれかに関連付ける必要があります。  
  
     \<*パスのサンプル*\>\SSO\HTTPSSO\Scripts  
  
 SsoSample.exe ウィザード アプリケーションを使用して、1 つ以上の関連アプリケーションを構成できます。 これらの関連アプリケーションごとに、1 つまたは複数のユーザー マッピングを作成できます。 これらの各ユーザー マッピングは、Windows ユーザー アカウントを、特定のバックエンド システムへのアクセスに使用するアカウントにマップします。 このサンプルでは、そのアカウントは、実際のバックエンド システムをシミュレートする 2 番目の IIS 仮想ディレクトリでの認証に使用する、ローカル Windows アカウントです。  
  
 このサンプルを再実行するには、複数の選択肢があります。  
  
-   Internet Explorer で、次の URL を直接参照します。  
  
     http://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll?<message/>  
  
-   ウィザード アプリケーションを再実行します。ただし、最初のページの構成チェック ボックスをすべてオフにします。  
  
-   ウィザード アプリケーションを再実行します。最初のページの構成チェック ボックスはすべてオンのままにしますが、構成エラーが発生しないように、その他の BizTalk アイテム、関連アプリケーションなどを慎重かつ適切に構成します。  
  
 このサンプルからクリーンアップするには、次の手順を使用します。  
  
#### <a name="to-clean-up-from-this-sample"></a>このサンプルからクリーンアップするには  
  
1.  ローカル Windows アカウントを削除するなど、適宜、実行した手動構成を元に戻します。  
  
2.  仮想ディレクトリに対応する IIS アプリケーションを削除した後、このサンプルで作成された IIS 仮想ディレクトリを削除します。  
  
3.  BizTalk 管理コンソールを使用して、参加解除した後、このサンプルに関連付けられている送信ポートを削除します。 このサンプルに関連付けられている受信ポート (およびその受信場所) を削除します。  
  
4.  Ssomanage アプリケーションを使用して (\program files \common files \enterprise シングル サインオン\\) このサンプルの SSO アプリケーションを削除します。  
  
    ```  
    Ssomanage –deleteapp SsoSampleApplication  
    ```  
  
## <a name="see-also"></a>参照  
 [SSO (BizTalk Server Samples フォルダー)](../core/sso-biztalk-server-samples-folder.md)