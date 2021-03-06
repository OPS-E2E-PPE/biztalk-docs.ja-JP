---
title: オーケストレーションをアプリケーションから削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, orchestrations
- deleting, orchestrations
- managing [orchestrations], deleting
- orchestrations, applications
- orchestrations, deleting
ms.assetid: e6d635ea-3513-42de-a667-b56c536e5328
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a3dbca1d838ca2691dcbfd1174debe49cbf0362
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335033"
---
# <a name="how-to-remove-an-orchestration-from-an-application"></a>オーケストレーションをアプリケーションから削除する方法
ここでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、オーケストレーションを BizTalk アプリケーションから削除する方法について説明します。 オーケストレーションをアプリケーションから削除すると、BizTalk グループの BizTalk 管理データベースからも削除されます。  
  
 オーケストレーションを削除すると、次の処理が行われます。  
  
- オーケストレーションが BizTalk 管理データベースから削除されます。  
  
- オーケストレーションを含む BizTalk アセンブリも BizTalk 管理データベースから削除されますが、ローカル ファイル システムまたはグローバル アセンブリ キャッシュ (GAC) 内に存在する場合、そのアセンブリは削除されません。  
  
- BizTalk アセンブリが削除されるため、アセンブリに含まれるすべての成果物は、BizTalk 管理データベースから削除されます。  
  
  オーケストレーションをアプリケーションから削除する前に、次の重要事項を考慮します。  
  
- 他のアイテムがこのオーケストレーションに依存関係を持っている場合、または削除されるアセンブリに含まれるアイテムに依存関係を持っている場合は、オーケストレーションを削除するとアイテムが適切に動作しなくなります。 依存関係に関する背景情報は、次を参照してください。[依存関係とアプリケーションの展開](../core/dependencies-and-application-deployment.md)します。  
  
- 実行中のインスタンスを含むオーケストレーションは削除できません。 実行中のインスタンスはすべて終了する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="to-remove-an-orchestration-from-an-application"></a>オーケストレーションをアプリケーションから削除するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、し、削除するオーケストレーションを含むアプリケーションを展開します。  
  
3. クリックして**オーケストレーション**、オーケストレーションを右クリックし、クリックして**参加解除**します。  
  
4. オーケストレーションを選択し、[**ビュー**、] をクリックし、**インスタンス情報**します。  
  
5. クエリの結果ウィンドウで、オーケストレーション インスタンスを右クリックし、 **Terminate**します。  
  
   > [!NOTE]
   >  参加解除、インスタンス、実行中の終了および停止できますすべてのアプリケーションのオーケストレーションは、一度に、アプリケーションの完全停止オプションを使用して」の説明に従って[BizTalk アプリケーション開始および停止方法](../core/how-to-start-and-stop-a-biztalk-application.md)します。  
  
6. クリックして**オーケストレーション**、オーケストレーションを右クリックし、クリックして**削除**します。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
    例:  
  
    **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**  
  
   |パラメーター|説明|  
   |---------------|-----------------|  
   |**/ApplicationName**|削除するオーケストレーションが存在する BizTalk アプリケーションの名前。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。 このパラメーターを指定しなかった場合、既定のアプリケーションが使用されます。|  
   |**/Luid**|オーケストレーションのローカル一意識別子 (LUID)。 LUID を取得するにを使用して、 [ListApp コマンド](../core/listapp-command.md)します。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前です。 Database パラメーターを指定する場合は必須です。 Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。|  
   |**/Database**|BizTalk 管理データベースの名前。 Server パラメーターを指定する場合は必須です。 Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [RemoveResource コマンド](../core/removeresource-command.md)