---
title: インスタンスの情報を表示する方法、受信ポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], viewing
- receive ports, viewing
- viewing, receive ports
ms.assetid: dad038bc-1202-489b-b144-a93bf1f53c0c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e46da8bfb99246b67f93c02fa19689099f8acb24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256802"
---
# <a name="how-to-view-instance-information-for-a-receive-port"></a>受信ポートのインスタンス情報を表示する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、受信ポートのサービス インスタンスを表示する方法について説明します。 受信ポートでメッセージを受け取るたびに、メッセージを処理するサービス インスタンスが作成されます。 このトピックの手順を実行すると、受信ポートのグループ概要ページにインスタンス情報を表示できます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-view-instance-information-for-a-receive-port"></a>受信ポートのインスタンス情報を表示するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートのインスタンス情報を表示する BizTalk アプリケーションを展開します。  
  
3.  をクリックして**受信ポート**受信ポートを選択してをクリックし、**ビュー**、順にクリック**インスタンス情報**です。  
  
     ページ下部のクエリ結果パネルに、受信ポートのすべてのインスタンスが表示されます。  
  
4.  クエリを絞り込んで、同じ受信ポートの別のインスタンス情報を表示 のボックスをクリックして**値**の**Search For**フィールドで、表示、およびをクリックするインスタンスの種類を選択**実行クエリ**です。 クエリの作成の詳細については、「関連項目」で検索に関するトピックを選んで参照してください。  
  
## <a name="see-also"></a>参照  
 [受信ポートの管理](../core/managing-receive-ports.md)   
 [実行中のサービス インスタンスを検索する方法](../core/how-to-search-for-running-service-instances.md)   
 [中断されたサービス インスタンスを検索する方法](../core/how-to-search-for-suspended-service-instances.md)   
 [メッセージを検索する方法](../core/how-to-search-for-messages.md)   
 [サブスクリプションを検索する方法](../core/how-to-search-for-subscriptions.md)