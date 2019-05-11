---
title: 送信ポートのインスタンス情報を表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, viewing
- managing [send ports], viewing
- viewing, send ports
ms.assetid: 37cf6561-5341-4a05-b531-33ab0334966e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcb1dc5c055a28ce3a651546e21744017c6bc5dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333093"
---
# <a name="how-to-view-instance-information-for-a-send-port"></a>送信ポートのインスタンス情報を表示する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、実行の一覧を表示する方法を説明します。 送信ポートのインスタンスのサービスを提供します。 サービス インスタンスは、メッセージが送信ポートに送信されるときに作成される送信ポート サービスのインスタンスです。 このトピックの手順を実行するときに、送信ポートのグループ概要ページにインスタンス情報が表示されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループまたは BizTalk Server Operators グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-view-instance-information-for-a-send-port"></a>送信ポートのインスタンス情報を表示するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループと、送信ポートのサービス インスタンスの情報を表示する BizTalk アプリケーションを展開します。  
  
3. をクリックして**送信ポート**、送信ポートを右クリックし、 をポイント**ビュー**、 をクリックし、**インスタンス情報**します。  
  
    ページの下部に、クエリ結果 パネルには、送信ポートのすべての実行中のインスタンスが表示されます。  
  
4. クエリを絞り込むし、送信ポートの別のサービス インスタンスの情報を表示、下にあるボックスをクリックします。**値**、検索対象フィールドの表示、およびクリックするインスタンスの種類を選択します。**クエリの実行**します。 クエリの作成に関する詳細については、参照の検索のトピックを参照してください。  
  
## <a name="see-also"></a>参照  
 [作成と送信ポートの構成](../core/creating-and-configuring-send-ports.md)   
 [実行中のサービス インスタンスを検索する方法](../core/how-to-search-for-running-service-instances.md)   
 [中断されたサービス インスタンスを検索する方法](../core/how-to-search-for-suspended-service-instances.md)   
 [メッセージを検索する方法](../core/how-to-search-for-messages.md)   
 [サブスクリプションを検索する方法](../core/how-to-search-for-subscriptions.md)