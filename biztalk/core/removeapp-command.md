---
title: "RemoveApp コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 323290ae-8498-4ad6-9b06-a1d54640250e
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9808b43ba07434793403d175885694f67530dae0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="removeapp-command"></a>RemoveApp コマンド
BizTalk 管理データベースから、BizTalk アプリケーションを含め、そこに格納されているすべてのアイテムを削除します。 アプリケーションがアンインストールされるわけではありません。 これを行う方法の詳細については、次を参照してください。[を BizTalk アプリケーションをアンインストールする方法](../core/how-to-uninstall-a-biztalk-application.md)です。  
  
 次の場合、削除操作は失敗します。  
  
-   **アプリケーションは停止されません。** アプリケーションを停止する方法の手順については、次を参照してください。[起動し、BizTalk アプリケーションを停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)です。 **ApplicationManager**にインストールされている SDK サンプルの*\<サンプル パス >\\*\explorerom\ ディレクトリは、プログラムで開始または停止する方法を示しています、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションです。  
  
-   **その他のアプリケーションでは、アプリケーションへの参照を含んでいます。** 削除するアプリケーションを他のアプリケーションが参照している場合、先に他のアプリケーションから参照を削除する必要があります。 手順については、次を参照してください。[を別のアプリケーションへの参照を削除する方法](../core/how-to-remove-a-reference-to-another-application.md)です。  
  
-   **アプリケーションには、別のアプリケーションでの送信ポートがメンバーになっている送信ポート グループが含まれています。** メンバーとなっている送信ポートを参加解除してから、アプリケーションを削除する必要があります。 手順については、次を参照してください。[送信ポートまたは送信ポート グループを参加解除する方法](../core/how-to-unenlist-a-send-port-or-send-port-group.md)です。  
  
-   **アプリケーションには、パーティによって参照される送信ポートが含まれています。** パーティから参照を削除するか、送信ポートを別のアプリケーションに移動します。 これらのタスクの実行方法の詳細については、次を参照してください。[方法を表示または編集するパーティ](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)または[別のアプリケーションにアイテムを移動する方法](../core/how-to-move-an-artifact-to-a-different-application.md)です。  
  
-   **アプリケーションは、既定のアプリケーションです。** 別のアプリケーションを既定にしてから削除する必要があります。 手順については、次を参照してください。[を既定のアプリケーションを変更する方法](../core/how-to-change-the-default-application.md)です。  
  
-   **アプリケーションのオーケストレーションが参加している開始されると、か、中断されたインスタンス。** オーケストレーションの詳細については、次を参照してください。[オーケストレーション管理](../core/managing-orchestrations.md)です。  
  
> [!NOTE]
>  アプリケーションに展開された状態になっているポリシーが含まれている場合、ポリシーはルール エンジン データベースから削除されませんし、下にある ポリシー フォルダーに表示する、\<すべてのアイテム > アプリケーション ノードの BizTalk 管理コンソールコンソールです。 ポリシーを他のアプリケーションに追加した場合、ポリシーはその後も展開された状態のままになります。  
  
## <a name="usage"></a>使用方法  
 **BTSTask RemoveApp/applicationname は:** *値*[**/Server:***値*] [**/database:** *値*]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|Description|  
|---------------|--------------|-----------------|  
|**/ApplicationName** (または**/A**、「解説」を参照してください)|はい|削除する BizTalk アプリケーションの名前。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
|**/サーバー** (または**/S**、「解説」を参照してください)|不可|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または**/D**、「解説」を参照してください)|不可|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask RemoveApp applicationname:**  
  
## <a name="remarks"></a>解説  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)   
 [BizTalk アプリケーションを展開解除](../core/undeploying-biztalk-applications.md)