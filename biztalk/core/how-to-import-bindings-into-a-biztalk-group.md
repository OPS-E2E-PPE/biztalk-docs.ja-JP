---
title: BizTalk グループにバインドをインポートする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, importing
- importing, bindings
- groups, bindings
- bindings, groups
ms.assetid: 38da14fb-3522-4274-a633-2ff24e4bd574
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a64bac6c64a9aadc772bfe8445b23f87b469471d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970136"
---
# <a name="how-to-import-bindings-into-a-biztalk-group"></a>BizTalk グループにバインドをインポートする方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、.xml ファイルからBizTalk グループにバインドをインポートする方法について説明します。 BizTalk グループからバインドをインポートできる .xml ファイルにエクスポートする方法については、次を参照してください。 [BizTalk グループのバインドのエクスポート方法](../core/how-to-export-bindings-for-a-biztalk-group.md)です。  
  
 」の説明に従って、BizTalk アプリケーションにバインドにインポートすることもできます[BizTalk アプリケーションにバインドのインポート方法](../core/how-to-import-bindings-into-a-biztalk-application.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-import-bindings-into-a-biztalk-group"></a>BizTalk グループにバインドをインポートするには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**BizTalk グループを展開し、右クリックし、**アプリケーション**です。  
  
3.  をポイント**インポート**、クリックして**バインド**です。  
  
4.  バインド ファイルをクリックし、をクリックして**開く**です。  
  
     バインド ファイルのアイテムがグループに書き込まれます。 適切なフォルダーに表示される、\<すべての成果物\>ノード。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask ImportBindings/Source:** *値* **/grouplevel は**[**/Server:***値*] [**/データベース:***値*]  
  
     たとえば、次のコマンドは、SQL Server インスタンス (MyServer) 上で実行されている BizTalk 管理データベースで定義されたグループにバインドをインポートします。  
  
     **BTSTask ImportBindings GroupLevel/Server:MyServer/Database:BiztalkMgmtDb/Source:C:\Bindings\Binding1.xml**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/ソース**|インポートするバインド ファイルの完全パス (ファイル名を含む)。 パスにスペースが含まれる場合は、二重引用符 (") で囲む必要があります。|  
    |**/GroupLevel**|バインド ファイルを現在のグループにインポートするためのオプション。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーション、バインド、およびポリシーをインポートします。](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [ImportBindings コマンド](../core/importbindings-command.md)