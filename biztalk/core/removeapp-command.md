---
title: RemoveApp コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 323290ae-8498-4ad6-9b06-a1d54640250e
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a670116f01343df2131835dfc225d93bb64a399d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397924"
---
# <a name="removeapp-command"></a>RemoveApp コマンド
BizTalk 管理データベースから、BizTalk アプリケーションを含め、そこに格納されているすべてのアイテムを削除します。 アプリケーションがアンインストールされるわけではありません。 これを行う方法の詳細については、次を参照してください。 [BizTalk アプリケーションをアンインストールする方法](../core/how-to-uninstall-a-biztalk-application.md)します。  
  
 次の場合、削除操作は失敗します。  
  
- **アプリケーションは停止されません。** アプリケーションの停止手順については、次を参照してください。 [BizTalk アプリケーション開始および停止方法](../core/how-to-start-and-stop-a-biztalk-application.md)します。 **ApplicationManager**にインストールされている SDK のサンプル、 <em>\<サンプル パス\>\\</em>admin \explorerom\ ディレクトリを示して 方法プログラム開始または停止を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション。  
  
- **他のアプリケーションには、アプリケーションへの参照が含まれます。** 削除するアプリケーションを他のアプリケーションが参照している場合、先に他のアプリケーションから参照を削除する必要があります。 手順については、次を参照してください。[別のアプリケーションへの参照を削除する方法](../core/how-to-remove-a-reference-to-another-application.md)します。  
  
- **アプリケーションには、別のアプリケーションでの送信ポートのメンバーになっている送信ポート グループが含まれています。** メンバーとなっている送信ポートを参加解除してから、アプリケーションを削除する必要があります。 手順については、次を参照してください。[送信ポートまたは送信ポート グループを参加解除する方法](../core/how-to-unenlist-a-send-port-or-send-port-group.md)します。  
  
- **アプリケーションには、パーティによって参照される送信ポートが含まれています。** パーティから参照を削除するか、送信ポートを別のアプリケーションに移動します。 これらのタスクを実行する方法の詳細については、次を参照してください。[方法を表示または編集するパーティ](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)または[を別のアプリケーション アイテムの移動方法](../core/how-to-move-an-artifact-to-a-different-application.md)します。  
  
- **アプリケーションは、既定のアプリケーションです。** 別のアプリケーションを既定にしてから削除する必要があります。 手順については、次を参照してください。[既定のアプリケーションを変更する方法](../core/how-to-change-the-default-application.md)します。  
  
- **アプリケーションのオーケストレーションが参加している、または、中断されたインスタンス。** オーケストレーションの詳細については、次を参照してください。[オーケストレーション管理](../core/managing-orchestrations.md)します。  
  
> [!NOTE]
>  ポリシーがルール エンジン データベースからは削除されず、ポリシー フォルダーの下に表示するには引き続きアプリケーションに展開された状態にあるポリシーが含まれている場合、\<すべての成果物\>BizTalk のアプリケーション ノード管理コンソール。 ポリシーを他のアプリケーションに追加した場合、ポリシーはその後も展開された状態のままになります。  
  
## <a name="usage"></a>使用方法  
 **BTSTask RemoveApp /ApplicationName:** *value* [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|説明|  
|---------------|--------------|-----------------|  
|**/ApplicationName** (または **/A**、「解説」を参照してください)|はい|削除する BizTalk アプリケーションの名前。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
|**/サーバー** (または **/S**、「解説」を参照してください)|いいえ|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または **/D**、「解説」を参照してください)|いいえ|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask RemoveApp applicationname:**  
  
## <a name="remarks"></a>コメント  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)   
 [BizTalk アプリケーションの展開解除](../core/undeploying-biztalk-applications.md)