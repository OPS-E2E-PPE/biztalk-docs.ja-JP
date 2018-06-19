---
title: BizTalk アセンブリのバインドをエクスポートする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies, bindings
- assemblies, exporting
- exporting, assemblies
ms.assetid: 7e37348d-5fa5-43cc-b3c0-2d8cb6a8f394
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64086cc8e54d89180d3c95268c78bc53e5ec9f55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254858"
---
# <a name="how-to-export-bindings-for-a-biztalk-assembly"></a>BizTalk アセンブリのバインドをエクスポートする方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、.xml ファイルに BizTalk アセンブリのバインドをエクスポートする方法について説明します。 エクスポートしたバインドは、BizTalk アプリケーションにインポートできます。この際、既存のバインドにインポートするバインドと同じ名前が含まれている場合は、既存のバインドが上書きされます。 アセンブリを更新する前にバインドをエクスポートしておくと、更新後にインポートすることでバインドを再適用できます。 アプリケーションおよびアセンブリの更新に関する詳細については、次を参照してください。 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)です。 バインド ファイルの使用の詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者または BizTalk Server Operators グループのメンバー アカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-export-bindings-for-a-biztalk-assembly"></a>BizTalk アセンブリのバインドをエクスポートするには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、[BizTalk グループ]、[アプリケーション] の順に展開します。  
  
3.  アセンブリを含むアプリケーションを右クリックし、**エクスポート**、クリックして**バインド**です。  
  
4.  バインドのエクスポート ページで**ファイルへのエクスポート**バインドのエクスポート先 .xml ファイルの絶対パスを入力します。  
  
     例: **C:\Bindings\MyAssemblyBindings_Staging1.xml**  
  
5.  バインドのエクスポート] ページで、をクリックして **、選択したアセンブリのバインドをエクスポート**、し、[**アセンブリ**アセンブリをクリックします。  
  
6.  すべてのグループのパーティ情報をエクスポートする場合は、選択**グローバル パーティ情報をエクスポート**です。  
  
     指定した場所の .xml ファイルに、バインドがエクスポートされます。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask ExportBindings/Destination:** *値* **/AssemblyName:** *値*[**/GlobalParties**] [**/Server:***値*] [**/database:***値*]  
  
     例:  
  
     **BTSTask ExportBindings/Destination:"C:\Binding Files\MyBindings.xml"/AssemblyName:"ErrorHandling.ErrorHandler、バージョン 1.0.0.0、Culture = neutral, PublicKeyToken = = 11e921d58826420e"/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/対象**|作成するバインド ファイルの完全パス (ファイル名を含む)。 同じパスの既存のバインド ファイルは上書きされます。 パスにスペースがある場合は、二重引用符 (") で囲む必要があります。|  
    |**/AssemblyName**|バインドのエクスポート元となるアセンブリのローカル一意識別子 (LUID)。 使用して、アプリケーション内のアイテムの Luid の一覧を取得することができます、 [ListApp コマンド](../core/listapp-command.md)です。|  
    |**/GlobalParties**|指定した場合は、グループのグローバル パーティ情報をエクスポートします。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [バインドをエクスポートします。](../core/exporting-bindings6.md)   
 [ExportBindings コマンド](../core/exportbindings-command.md)   
 [BizTalk アプリケーション、バインド、およびポリシーをインポートします。](../core/importing-biztalk-applications-bindings-and-policies.md)