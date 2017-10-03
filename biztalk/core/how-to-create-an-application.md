---
title: "アプリケーションを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, creating
- creating, applications
ms.assetid: 6a8682a7-3bef-4978-996f-5a9c5154ce62
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6078e292673a1d9dbe3634ea9c0c4e79ab9c2cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-an-application"></a>アプリケーションを作成する方法
新しい BizTalk アプリケーションを作成するには、次の 3 つの方法があります。  
  
-   BizTalk アプリケーションを作成するには、BizTalk Server 管理コンソールの [新しいアプリケーション] コマンドまたは BTSTask コマンド ライン ツールの AddApp コマンドを使用します。 この手順については、このトピックで後述します。  
  
-   他のアプリケーションからエクスポートした .msi ファイルをインポートします。 アプリケーションが現在の BizTalk グループに存在しない場合、アプリケーション (そのアイテムを含む) は現在の BizTalk グループに自動的に作成されます。 詳細については、次を参照してください。[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。  
  
-   Visual Studio から BizTalk アプリケーションへ BizTalk アセンブリを展開します。 Visual Studio で指定されたアプリケーションが現在の BizTalk グループに存在しない場合、そのアプリケーションは自動的に作成されます。 詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。  
  
 新しいアプリケーションを作成する前に、次のオプションの構成方法を決定できます。  
  
-   **新しいアプリケーションの名前に何か。** BizTalk グループの各アプリケーションには、一意の名前を付ける必要があります。  
  
-   **かどうかは、他のアプリケーションへの参照を追加する必要があります。** このアプリケーションから、このアプリケーションで再利用するアイテムを含むアプリケーションへの参照を追加する必要があります。 これにより 2 つのアプリケーションの間の依存関係が作成され、これらのアプリケーションの展開方法に影響します。 背景情報について、次を参照してください。[の依存関係とアプリケーションの配置](../core/dependencies-and-application-deployment.md)と[を別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)です。  
  
-   **かどうかは、1 つ以上のアプリケーションを作成する必要があります。** アイテムによっては、独立したアプリケーションに展開する必要があります。 たとえば、共有アイテムは、独自の独立したアプリケーションに展開する必要があります。 詳細については、次を参照してください。 [BizTalk アプリケーションを配置するためのベスト プラクティス](../core/best-practices-for-deploying-a-biztalk-application.md)です。  
  
 アプリケーションを作成した後は、成果物を追加して、他のトピックでは、このセクションで説明されている他の変更をください ([を変更する BizTalk アプリケーションの作成と](../core/creating-and-modifying-biztalk-applications.md))。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-create-a-biztalk-application"></a>BizTalk アプリケーションを作成するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで [ [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、新しいアプリケーションを作成する] をポイントする BizTalk グループを右クリックして**新規**、順にクリック**アプリケーション**です。  
  
3.  **名前**アプリケーションの名前を入力します。 名前は、BizTalk グループ内で一意にする必要があります。  
  
4.  この BizTalk グループの既定のアプリケーションを作成する場合は、選択、**しやすいように、既定のアプリケーション**チェック ボックスをオンします。  
  
5.  **説明**アプリケーションの説明を入力します。  
  
6.  このアプリケーションには、別のアプリケーションからアイテムを再利用、クリックして**参照**し、残りの手順に従います。 それ以外の場合、をクリックして**OK**以降の手順を行わない。  
  
7.  をクリックして**追加**をクリックしてこのアプリケーションで再利用するアイテムを含むアプリケーションを選択**OK**です。 追加アプリケーションの参照を追加するには、この手順を繰り返します。  
  
8.  一覧からアプリケーションを削除する場合は、アプリケーションを選択し、をクリックして**削除**です。  
  
9. 完了したら、 **[OK]**をクリックします。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask AddApp/applicationname は:** *値*[**/既定**] [**/Description:***値*] [**/サーバー:***値*] [**/database:***値*]  
  
     例:  
  
     **BTSTask AddApp applicationname: myapplication/Description:"お気に入り My application"/Server:MySQLServer/Database:BizTalkMgmtDb**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/ApplicationName**|作成されるアプリケーションの名前。 空白を含む名前は、二重引用符 (") で囲む必要があります。|  
    |**/既定**|指定した場合、BizTalk グループの既定のアプリケーションになります。|  
    |**/説明**|アプリケーションの説明です。 空白を含む説明は、二重引用符 (") で囲む必要があります。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md)   
 [AddApp コマンド](../core/addapp-command.md)