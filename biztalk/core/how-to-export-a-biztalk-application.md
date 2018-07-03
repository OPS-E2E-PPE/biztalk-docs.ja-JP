---
title: BizTalk アプリケーションをエクスポートする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, exporting
- exporting, warnings
- exporting, applications
- applications, exporting
- applications, security
- applications, warnings
- exporting, security
ms.assetid: a1d6ffca-3d29-44c7-a811-6cf8b42e23f6
caps.latest.revision: 50
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6bdab45366e4f1a540e436ee44f6736b04cee08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977515"
---
# <a name="how-to-export-a-biztalk-application"></a>BizTalk アプリケーションをエクスポートする方法
ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールまたはコマンド ラインを使用して、アプリケーションをエクスポートする方法について説明します。 BizTalk アプリケーションをエクスポートすると、Windows Installer (.msi) ファイルが生成されます。このファイルには、アプリケーションと、エクスポートするよう選択したアプリケーションのアイテムが含まれます。 既定のオプションではアプリケーションのすべてのアイテムが選択されていますが、アイテムのサブセットを選択することもできます。 生成された .msi ファイルは別の BizTalk グループにインポートできます。これによって、新しいグループの既存のアプリケーションにアイテムを追加したり、既存のアプリケーションのアイテムを更新したり、グループ内にインポート対象のアイテムを含んだ新しいアプリケーションを作成することができます。 詳細については、次を参照してください。 [BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。 」の説明に従って、それを実行するコンピューターでアプリケーションをインストールする .msi ファイルを使用するも[BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)します。 アプリケーションにファイルベースのアイテムが含まれる場合、アプリケーションを使用するにはそのアイテムもインストールする必要があります。  
  
 アプリケーションをエクスポートする際には、次の重要事項を念頭に置いてください。  
  
- **既存のバインドは、インポートされるバインドによって自動的に上書きされます。** エクスポートするアプリケーションのバインドで、.msi ファイルのインポート先アプリケーションのバインドを上書きしないようにするには、エクスポートするリソースにバインド ファイルを選択しないでください。 バインド ファイルを含む .msi ファイルを既存のアプリケーションにインポートすると、既存のアイテムを上書きするオプションを選択していなくても、既存のバインドはインポートしたバインドで上書きされます。  
  
- **ユーザーを変更している成果物、アプリケーションのエクスポート時。** エクスポート処理の実行中に、ユーザーが仮想ディレクトリ、証明書、ポリシーなどのデータベース関連アイテムを変更している場合、これらの変更はエクスポート後の .msi ファイルには反映されません。 このため、エクスポート操作は、ユーザーがアイテムの変更を行う可能性が低い時間帯にスケジュールすることをお勧めします。  
  
- **Windows Vista で .msi をインストールするときに、誤ったエラーを表示できる**します。 使用してエクスポートされた .msi パッケージをインストールするときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、次の誤ったエラーが表示される、"インストーラーはこのパッケージをインストールして予期しないエラーにしました。 このパッケージに問題がある可能性があります。 エラー コード: 2869。" このエラーを修正するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して .msi パッケージをインポートした後に、パッケージを再度エクスポートしてインストールします。  
  
- **アプリケーションによっては、別のアプリケーションに依存関係があります。** 別のアプリケーションとの依存関係は、アプリケーションの展開方法に影響します。 詳細については、次を参照してください。[依存関係とアプリケーションの展開](../core/dependencies-and-application-deployment.md)します。  
  
- **前に、エクスポート、アプリケーションでは、リソースのインストール先ディレクトリを変更できます。** 変換先の場所を変更する場合は、アプリケーションのリソース ノードを展開、変更、および選択するリソースを右クリックして**変更**します。 リソースの変更 ダイアログ ボックスでの新しい場所を入力します。**先**します。  
  
- **アプリケーションには、ルール エンジン データベースから削除されたポリシーが含まれている場合、エクスポートは失敗します。** ルール エンジン展開ウィザードを使用してルール エンジン データベースからポリシーを削除した場合、ポリシーは管理コンソールに "未公開" の状態として表示されます。この場合、アプリケーションをエクスポートすることはできません。 ルール エンジン展開ウィザードの詳細については、次を参照してください。[とボキャブラリを展開およびポリシーの展開を解除する方法](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)します。  
  
> [!IMPORTANT]
>  .msi ファイルには機密データが含まれている場合があります。 ファイルが安全であることを確認する手順を実行してください。 詳細については、次を参照してください。[セキュリティと Windows インストーラー](../core/security-and-windows-installer.md)します。  
> 
>  パスワードは、アプリケーションのエクスポート中にアプリケーションのバインドから削除されます。 .Msi ファイルからアプリケーションをインストールした後は、アプリケーションが機能するためにパスワードを再構成する必要があります。 ただし、パスワードはアプリケーションに追加したバインド ファイルからは削除されません。  
> 
>  アプリケーションに Web サイトが含まれている場合、または Web サービスを使用するオーケストレーションが含まれている場合、仮想ディレクトリのセキュリティ設定は、アプリケーションのエクスポートで .msi ファイルが生成されたときに使用されていた設定になります。 運用環境にアプリケーションを展開する場合、アプリケーションをエクスポートする前に確認してください、設定がセキュリティ要件を満たしています。 仮想ディレクトリが既にホスト コンピューターに存在する場合、セキュリティ設定は上書きされず、アプリケーションのファイルが設定に追加されます。 アプリケーションをインポートした後、セキュリティ設定を確認してください。  
> 
>  アプリケーションのエクスポート時には、ファイルとフォルダーからすべての随意アクセス制御リスト (DACL) が削除されます。 したがって、アプリケーションのインストール後、ファイルとフォルダーのすべてのセキュリティ設定 (仮想ディレクトリを含む) を再構築する必要があります。  
> 
> [!NOTE]
>  エクスポート操作が失敗した場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では作成された .msi ファイルとすべての一時ファイルが削除されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行する必要がありますがログオンしてのメンバーであるアカウントを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。 また、ビジネス ルール エンジンがインストールされている必要があります。 詳細については、次を参照してください。 [BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)します。  
  
## <a name="to-export-an-application"></a>アプリケーションのエクスポート  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**、BizTalk グループを展開し、展開、**アプリケーション**します。  
  
3. アプリケーションのエクスポート をポイントするを右クリックして**エクスポート**、 をクリックし、 **MSI ファイル**します。  
  
4. MSI ファイルのエクスポート ウィザードのページへようこそ、をクリックして**次**します。  
  
5. リソースの選択 ページで、.msi ファイルにエクスポートするアイテムを選択し、クリックして**次**します。  
  
6. メッセージが表示されたら、IIS ホストの指定 ページで、含めるをクリックする仮想ディレクトリをホストするコンピューターのサーバー名を入力**次**します。 サーバーの指定が要求されるのは、仮想ディレクトリがアプリケーションに追加されたりインポートされたときに、仮想ディレクトリが BizTalk 管理データベースに追加されていなかった場合のみです。  
  
7. 依存関係 ページで、アプリケーションの依存関係を確認し、**次**します。  
  
8. 変換先 ページで**送信先アプリケーション名**アプリケーション名を入力します。  
  
9. **を生成する MSI ファイル**、.msi ファイルの完全なパスを入力し、クリックして**エクスポート**します。 例: C:\MSI\Errorhandling.msi  
  
    > [!NOTE]
    >  .msi ファイルはセキュリティで保護されたフォルダーに保存することをお勧めします。  
  
10. [概要] ページで、この操作の場合は、ログ ファイルの場所をメモしておき、クリックして**完了**します。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1. 次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask の ExportApp** [**/applicationname は:**<em>値</em>] **/package:**<em>値</em>[**ResourceSpec:**<em>値</em>[**/Server:**<em>値</em>] [**/database:**<em>値</em>]  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
    例:  
  
    **BTSTask の ExportApp applicationname: myapplication/Package:C:/MSI/MyApplication.msi/ResourceSpec:"C:\My Files\ResourceSpec.xml"/Server:MySQLServer/Database:BizTalkMgmtDb**  
  
    指定したアイテムは、指定した場所に .msi ファイルとしてエクスポートされます。  
  
   |パラメーター|値|  
   |---------------|-----------|  
   |**/ApplicationName**|エクスポートする BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、既定の BizTalk アプリケーションが使用されます。 名前にスペースが含まれる場合は、二重引用符 (") で囲む必要があります。|  
   |**/パッケージ**|作成する .msi ファイルのパス (ファイル名を含む) です。|  
   |**/ResourceSpec**|XML 形式の ResourceSpec ファイルのパス (ファイル名を含む) です。 ResourceSpec パラメーターと共に、ListApp を実行するときに作成されたリソース仕様 XML ファイルを編集してエクスポートするアイテムのコマンドを指定できます」の説明に従って[ListApp コマンド](../core/listapp-command.md)します。 Web サーバーがリモート コンピューター上にある場合をエクスポートする仮想ディレクトリのインターネット インフォメーション サービス (IIS) のホスト サーバー名を追加するには、このファイルを手動で編集する必要があります。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
   |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーション、バインド、およびポリシーのエクスポート](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [ExportApp コマンド](../core/exportapp-command.md)