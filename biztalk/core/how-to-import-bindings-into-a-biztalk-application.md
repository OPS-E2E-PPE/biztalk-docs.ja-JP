---
title: BizTalk アプリケーションにバインドをインポートする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, applications
- applications, importing
- applications, bindings
- bindings, importing
ms.assetid: 89841b23-4e1b-46ff-8f00-cdad65d6216d
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b07e2c7cb5e63ee3e03ac69ad591d7939b22d5d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254138"
---
# <a name="how-to-import-bindings-into-a-biztalk-application"></a>BizTalk アプリケーションにバインドをインポートする方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、.xml ファイルから BizTalk アプリケーションにバインドをインポートする方法について説明します。 」の説明に従って、BizTalk グループにバインドにインポートすることもできます[を BizTalk グループにバインドのインポート方法](../core/how-to-import-bindings-into-a-biztalk-group.md)です。  
  
 バインドは、アセンブリ、アプリケーション、グループからエクスポートしたものをインポートできます。 グループのバインドをインポートする場合、同じ名前を持つアプリケーションのバインドだけが、バインドのインポート先のアプリケーションに適用されます。 異なる名前のアプリケーションからバインドをインポートすることもできます。 バインドをエクスポートする方法については、次を参照してください。[バインドのエクスポート](../core/exporting-bindings6.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-import-bindings-into-a-biztalk-application"></a>BizTalk アプリケーションにバインドをインポートするには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、[BizTalk グループ]、[アプリケーション] の順に展開します。  
  
3.  ポイントし、バインドをインポートするアプリケーションを右クリックして**インポート**、クリックして**バインド**です。  
  
4.  バインド ファイルをクリックし、をクリックして**開く**です。  
  
     バインド ファイルのアイテムがアプリケーションに書き込まれます。 これらのアイテムは、アプリケーションの該当するフォルダーに表示されます。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask ImportBindings/Source:** *値*[**/applicationname は:***値*] [**/Server:** *値*] [**/database:***値*]  
  
     たとえば、次のコマンドは、既定の BizTalk グループの MyApplication というアプリケーションにバインドをインポートします。  
  
     **Applicationname: myapplication BTSTask ImportBindings** /**Source:C:\Bindings\Binding1.xml**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/ソース**|インポートするバインド ファイルの完全パス (ファイル名を含む)。 パスにスペースが含まれる場合は、二重引用符 (") で囲む必要があります。|  
    |**/ApplicationName**|バインドをインポートする BizTalk アプリケーションの名前。 アプリケーションが存在している必要があります。アプリケーションが存在しない場合、インポート操作は失敗します。 このパラメーターを指定しなかった場合、既定の BizTalk アプリケーションが使用されます。 アプリケーション名にスペースが含まれる場合は、二重引用符 (") で囲む必要があります。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーション、バインド、およびポリシーをインポートします。](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [ImportBindings コマンド](../core/importbindings-command.md)