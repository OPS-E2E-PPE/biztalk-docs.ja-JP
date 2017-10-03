---
title: "BizTalk グループのバインドをエクスポートする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bindings, exporting
- groups, bindings
- groups, exporting
ms.assetid: 51955266-f87f-41c9-992c-93036b40f663
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df08f99a9e37bf1a4d4a794c17d483fdc381f463
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-export-bindings-for-a-biztalk-group"></a>BizTalk グループのバインドをエクスポートする方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、.xml ファイルに BizTalk グループのバインドをエクスポートする方法について説明します。 」の説明に従って、BizTalk グループまたはアプリケーションにこれらのバインドにインポートすること、ことができます[を BizTalk グループにバインドのインポート方法](../core/how-to-import-bindings-into-a-biztalk-group.md)と[BizTalk アプリケーションにバインドのインポート方法](../core/how-to-import-bindings-into-a-biztalk-application.md)です。 バインド ファイルの使用の詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)です。  
  
> [!NOTE]
>  グループのバインドをエクスポートすると、オプションが指定されているかどうかに関係なく、常にグローバル パーティ情報がエクスポートされます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者または BizTalk Operators グループのメンバー アカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-export-bindings-for-a-biztalk-group"></a>BizTalk グループのバインドをエクスポートするには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで [[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を BizTalk グループを展開しを右クリックして**アプリケーション**、] をポイント**エクスポート**、順にクリック**バインド**です。  
  
3.  バインドのエクスポート ページで**ファイルへのエクスポート**バインドのエクスポート先 .xml ファイルの絶対パスを入力します。  
  
     例: C:\Bindings\Group1Bindings_Staging1.xml  
  
4.  いることを確認**、現在のグループからすべてのバインドをエクスポート**を選択して、をクリックして**OK**です。  
  
     指定した場所の .xml ファイルに、バインドがエクスポートされます。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask ExportBindings/Destination:** *値* **/grouplevel は**[**/GlobalParties**] [**/Server:** *値*] [**/database:***値*]  
  
     例:  
  
     **BTSTask ExportBindings/Destination:"C:\Binding Files\MyBindings.xml"GroupLevel/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/対象**|作成するバインド ファイルの完全パス (ファイル名を含む)。 同じパスの既存のバインド ファイルは上書きされます。 パスにスペースがある場合は、二重引用符 (") で囲む必要があります。|  
    |**/GroupLevel**|指定した場合、現在の BizTalk グループのすべてのバインドがエクスポートされます。|  
    |**/GlobalParties**|指定した場合、グループのグローバル パーティ情報をエクスポートします。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [バインドをエクスポートします。](../core/exporting-bindings6.md)   
 [ExportBindings コマンド](../core/exportbindings-command.md)   
 [BizTalk アプリケーション、バインド、およびポリシーをインポートします。](../core/importing-biztalk-applications-bindings-and-policies.md)