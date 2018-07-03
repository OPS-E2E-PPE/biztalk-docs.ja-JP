---
title: BizTalk アプリケーションにバインドをインポートする方法 |Microsoft Docs
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
ms.openlocfilehash: 174a54b5f1ad98b4ba57c70a24ec2f621577271d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011947"
---
# <a name="how-to-import-bindings-into-a-biztalk-application"></a>BizTalk アプリケーションにバインドをインポートする方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、.xml ファイルから BizTalk アプリケーションにバインドをインポートする方法について説明します。 」の説明に従って、BizTalk グループにバインドにインポートすることもできます[を BizTalk グループにバインドのインポート方法](../core/how-to-import-bindings-into-a-biztalk-group.md)します。  
  
 バインドは、アセンブリ、アプリケーション、グループからエクスポートしたものをインポートできます。 グループのバインドをインポートする場合、同じ名前を持つアプリケーションのバインドだけが、バインドのインポート先のアプリケーションに適用されます。 異なる名前のアプリケーションからバインドをインポートすることもできます。 バインドのエクスポート手順については、次を参照してください。[バインドのエクスポート](../core/exporting-bindings6.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="to-import-bindings-into-a-biztalk-application"></a>BizTalk アプリケーションにバインドをインポートするには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、[BizTalk グループ]、[アプリケーション] の順に展開します。  
  
3. ポイントして、バインドをインポートするアプリケーションを右クリックして**インポート**、 をクリックし、**バインド**します。  
  
4. バインド ファイルをクリックし、をクリックして**オープン**します。  
  
    バインド ファイルのアイテムがアプリケーションに書き込まれます。 これらのアイテムは、アプリケーションの該当するフォルダーに表示されます。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1. 次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask ImportBindings/Source:** *値*[**/applicationname は:**<em>値</em>] [**/Server:** <em>値</em>] [**/database:**<em>値</em>]  
  
    たとえば、次のコマンドは、既定の BizTalk グループの MyApplication というアプリケーションにバインドをインポートします。  
  
    **BTSTask ImportBindings applicationname: myapplication** /**Source:C:\Bindings\Binding1.xml**  
  
   |パラメーター|値|  
   |---------------|-----------|  
   |**/ソース**|インポートするバインド ファイルの完全パス (ファイル名を含む)。 パスにスペースが含まれる場合は、二重引用符 (") で囲む必要があります。|  
   |**/ApplicationName**|バインドをインポートする BizTalk アプリケーションの名前。 アプリケーションが存在している必要があります。アプリケーションが存在しない場合、インポート操作は失敗します。 このパラメーターを指定しなかった場合、既定の BizTalk アプリケーションが使用されます。 アプリケーション名にスペースが含まれる場合は、二重引用符 (") で囲む必要があります。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
   |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーション、バインド、およびポリシーのインポート](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [ImportBindings コマンド](../core/importbindings-command.md)