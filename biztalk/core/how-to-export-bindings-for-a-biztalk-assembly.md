---
title: BizTalk アセンブリのバインドをエクスポートする方法 |Microsoft Docs
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
ms.openlocfilehash: 2807e0832dae1722e2b0b15e7b098246784bca88
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337782"
---
# <a name="how-to-export-bindings-for-a-biztalk-assembly"></a>BizTalk アセンブリのバインドをエクスポートする方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、.xml ファイルに BizTalk アセンブリのバインドをエクスポートする方法について説明します。 エクスポートしたバインドは、BizTalk アプリケーションにインポートできます。この際、既存のバインドにインポートするバインドと同じ名前が含まれている場合は、既存のバインドが上書きされます。 アセンブリを更新する前にバインドをエクスポートしておくと、更新後にインポートすることでバインドを再適用できます。 アプリケーションとアセンブリの更新の詳細については、次を参照してください。 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)します。 バインド ファイルの使用についての詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者または BizTalk Server Operators グループのメンバー アカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="to-export-bindings-for-a-biztalk-assembly"></a>BizTalk アセンブリのバインドをエクスポートするには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、[BizTalk グループ]、[アプリケーション] の順に展開します。  
  
3. アセンブリを含むアプリケーションを右クリックし、[**エクスポート**、] をクリックし、**バインド**します。  
  
4. バインドのエクスポート ページで**ファイルにエクスポート**バインドのエクスポート先 .xml ファイルの絶対パスを入力します。  
  
    例:**C:\Bindings\MyAssemblyBindings_Staging1.xml**  
  
5. バインドのエクスポート] ページで、次のようにクリックします。**選択したアセンブリのバインドをエクスポート**、し、[**アセンブリ**、アセンブリをクリックします。  
  
6. すべてのグループのパーティ情報をエクスポートする場合は、選択**グローバル パーティ情報をエクスポート**します。  
  
    指定した場所の .xml ファイルに、バインドがエクスポートされます。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask ExportBindings /Destination:** *value* **/AssemblyName:** *value* **[/GlobalParties]** [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
    例:  
  
    **BTSTask ExportBindings/Destination:"C:\Binding Files\MyBindings.xml"/AssemblyName:"ErrorHandling.ErrorHandler、バージョン 1.0.0.0、Culture = neutral, PublicKeyToken = = 11e921d58826420e"/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
   |パラメーター|値|  
   |---------------|-----------|  
   |**/変換先**|作成するバインド ファイルの完全パス (ファイル名を含む)。 同じパスの既存のバインド ファイルは上書きされます。 パスにスペースがある場合は、二重引用符 (") で囲む必要があります。|  
   |**/AssemblyName**|バインドのエクスポート元となるアセンブリのローカル一意識別子 (LUID)。 使用して、アプリケーションでのアイテムの Luid の一覧を取得することができます、 [ListApp コマンド](../core/listapp-command.md)します。|  
   |**/GlobalParties**|指定した場合、グループのグローバル パーティ情報をエクスポートします。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
   |**/Database**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [バインドのエクスポート](../core/exporting-bindings6.md)   
 [ExportBindings コマンド](../core/exportbindings-command.md)   
 [BizTalk アプリケーション、バインド、およびポリシーのインポート](../core/importing-biztalk-applications-bindings-and-policies.md)