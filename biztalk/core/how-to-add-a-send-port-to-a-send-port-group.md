---
title: "送信ポート、送信ポート グループを追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [send port groups], adding send ports
- managing [send ports], adding to send port groups
- send port groups, send ports
- send ports, send port groups
- adding, send ports
ms.assetid: a61b3b32-c05e-40b9-abf1-09b7065fb6a2
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3e10a16b31f5cc112e814faf119dc424c99ba67
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-add-a-send-port-to-a-send-port-group"></a>送信ポートを送信ポート グループに追加する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、1 つまたは複数の送信ポートを送信ポート グループに追加する方法について説明します。 静的な一方向の送信ポートは、送信ポート グループにのみ追加できます。  
  
 別のアプリケーションに存在する送信ポートを追加することはできません。 別のアプリケーションの送信ポートを追加する場合は、送信ポート グループのあるアプリケーションから目的の送信ポートがあるアプリケーションへの参照を追加する必要があります。 手順については、次を参照してください。[を別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-add-a-send-port-to-a-send-port-group"></a>送信ポート グループへ送信ポートを追加するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポート グループに送信ポートを追加する BizTalk アプリケーションを展開します。  
  
3.  をクリックして**送信ポート グループ**送信ポート グループを右クリックし、クリックして**プロパティ**です。  
  
4.  **送信ポート**、下にあるドロップダウン リストをクリックして**名前**、送信ポート グループに追加する送信ポート をクリックします。 グループに追加する送信ポートごとにこの手順を繰り返します。 新しい送信ポートを作成し、追加して、クリックして**\<新しいポートを送信しています.\>** し、指示に従って、[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。  
  
5.  送信ポートの送信ポート グループに追加したらをクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [作成して、送信ポート グループを構成します。](../core/creating-and-configuring-send-port-groups.md)   
 [送信ポートの作成および構成](../core/creating-and-configuring-send-ports.md)