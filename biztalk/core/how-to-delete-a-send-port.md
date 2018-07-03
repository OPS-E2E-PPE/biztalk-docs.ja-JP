---
title: 送信ポートを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send ports], deleting
- send ports, deleting
- deleting, send ports
ms.assetid: aff5980e-57bf-400c-82bd-3d02e143f227
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fd1bdab77761787cef404f318d2965f68e3a8c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973210"
---
# <a name="how-to-delete-a-send-port"></a>送信ポートを削除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートを BizTalk アプリケーションから削除する方法について説明します。 送信ポートを BizTalk アプリケーションから削除すると、そのグループの BizTalk 管理データベースからも送信ポート グループが削除されます。  
  
> [!IMPORTANT]
>  送信ポートを削除すると、そのポートに関連付けられている実行中のサービス インスタンスからは、送信ポートに関する情報 (送信ポート名など) を一切取得できなくなります。 送信ポートに関する情報はキャッシュされますが、サービス インスタンスがメッセージを再送しなければならなくなった場合に、再送処理を最後まで実行できず、メッセージは中断されます。 送信ポートを削除する前に実行がないことを確認する必要があります」の説明に従って、インスタンスをサービス[送信ポートのインスタンス情報を表示する方法](../core/how-to-view-instance-information-for-a-send-port.md)します。  
  
 送信ポートを削除できるのは、次の条件を満たしている場合だけです。  
  
-   送信ポートにオーケストレーションがバインドされていない:  次の手順で、バインドを削除するには、ケースの場合は、[オーケストレーションをバインド解除する方法](../core/how-to-unbind-an-orchestration.md)します。  
  
-   送信ポートが停止および参加解除されている:  停止、および送信ポートを参加解除については、次を参照してください。[送信ポートまたは送信ポート グループを参加解除する方法](../core/how-to-unenlist-a-send-port-or-send-port-group.md)と[送信ポートまたは送信ポート グループを停止する方法](../core/how-to-stop-a-send-port-or-send-port-group.md)します。  
  
-   送信ポートがパーティで参照されていない:  パーティから送信ポートへの参照を削除する方法の詳細については、次を参照してください。[方法を表示または編集するパーティ](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)します。  
  
-   送信ポートが送信ポート グループに属していない:  送信ポート グループから送信ポートを削除する方法の詳細については、次を参照してください。[送信ポート グループから送信ポートを削除する方法](../core/how-to-remove-a-send-port-from-a-send-port-group.md)します。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中に送信ポートを削除するには、このトピックの手順を実行します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-delete-a-send-port"></a>送信ポートを削除するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで BizTalk Server 管理コンソールを展開し、BizTalk グループ、アプリケーションを展開し削除する送信ポートを含むアプリケーションを展開  
  
3. クリックして**送信ポート**送信ポートを右クリックし、クリックして**削除**します。  
  
## <a name="see-also"></a>参照  
 [送信ポートの作成および構成](../core/creating-and-configuring-send-ports.md)