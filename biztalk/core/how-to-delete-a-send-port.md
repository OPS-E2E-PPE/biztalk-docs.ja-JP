---
title: "送信ポートを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [send ports], deleting
- send ports, deleting
- deleting, send ports
ms.assetid: aff5980e-57bf-400c-82bd-3d02e143f227
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f55b4e08fa03380c3361a44b7989301b606732d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-delete-a-send-port"></a>送信ポートを削除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートを BizTalk アプリケーションから削除する方法について説明します。 送信ポートを BizTalk アプリケーションから削除すると、そのグループの BizTalk 管理データベースからも送信ポート グループが削除されます。  
  
> [!IMPORTANT]
>  送信ポートを削除すると、そのポートに関連付けられている実行中のサービス インスタンスからは、送信ポートに関する情報 (送信ポート名など) を一切取得できなくなります。 送信ポートに関する情報はキャッシュされますが、サービス インスタンスがメッセージを再送しなければならなくなった場合に、再送処理を最後まで実行できず、メッセージは中断されます。 送信ポートを削除する前に実行がないことを確認する必要があります」の説明に従ってのインスタンスをサービス[送信ポートのインスタンス情報を表示する方法](../core/how-to-view-instance-information-for-a-send-port.md)です。  
  
 送信ポートを削除できるのは、次の条件を満たしている場合だけです。  
  
-   送信ポートにオーケストレーションがバインドされていない:  次の手順で、バインドを解除するには大文字と小文字の場合は、[オーケストレーションをバインド解除する方法](../core/how-to-unbind-an-orchestration.md)です。  
  
-   送信ポートが停止および参加解除されている:  停止し、送信ポートを参加解除の手順については、次を参照してください。[送信ポートまたは送信ポート グループを参加解除する方法](../core/how-to-unenlist-a-send-port-or-send-port-group.md)と[送信ポートまたは送信ポート グループを停止する方法](../core/how-to-stop-a-send-port-or-send-port-group.md)です。  
  
-   送信ポートがパーティで参照されていない:  パーティから送信ポートへの参照を削除する方法の詳細については、次を参照してください。[方法を表示または編集するパーティ](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)です。  
  
-   送信ポートが送信ポート グループに属していない:  送信ポート グループから送信ポートを削除する方法の詳細については、次を参照してください。[送信ポート グループから送信ポートを削除する方法](../core/how-to-remove-a-send-port-from-a-send-port-group.md)です。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中に送信ポートを削除するには、このトピックの手順を実行します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-delete-a-send-port"></a>送信ポートを削除するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 管理]、[BizTalk グループ]、[アプリケーション] の順に展開し、削除する送信ポートを含むアプリケーションを展開します。  
  
3.  をクリックして**送信ポート**送信ポートを右クリックし、クリックして**削除**です。  
  
## <a name="see-also"></a>参照  
 [作成して、送信ポートの構成](../core/creating-and-configuring-send-ports.md)