---
title: オーケストレーションのインスタンス情報を表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, viewing
- managing [orchestrations], viewing
ms.assetid: 860ac2b2-c556-4e1f-8b7f-18ab8be52db4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 694beca5172f50052e0e58ce1087048ee149c6d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383141"
---
# <a name="how-to-view-instance-information-for-an-orchestration"></a>オーケストレーションのインスタンス情報を表示する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションのインスタンス情報を表示する方法について説明します。 サービス インスタンスは、BizTalk Server は、いずれかのオーケストレーションのインスタンスの処理、またはさらに処理または追跡のため、メッセージ ボックスにシリアル化します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-view-instance-information-for-an-orchestration"></a>オーケストレーションのインスタンス情報を表示するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]展開し、BizTalk グループを展開し、**アプリケーション**、し、インスタンス情報を表示するオーケストレーションを含むアプリケーションを展開します。  
  
3. をクリックして**オーケストレーション**を選択、オーケストレーション インスタンスの情報を表示する] をクリックして**ビュー**、し、[**インスタンス情報**。  
  
    ページの下部に、クエリ結果 パネルには、オーケストレーションのすべてのインスタンスが表示されます。  
  
    オーケストレーションのクエリおよびビューの別のインスタンス情報を絞り込む、下にあるボックスをクリックします。**値**、検索対象フィールドの表示、およびクリックするインスタンスの種類を選択します。**クエリの実行**します。 クエリの作成に関する詳細については、参照の検索のトピックを参照してください。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [実行中のサービス インスタンスを検索する方法](../core/how-to-search-for-running-service-instances.md)   
 [中断されたサービス インスタンスを検索する方法](../core/how-to-search-for-suspended-service-instances.md)   
 [メッセージを検索する方法](../core/how-to-search-for-messages.md)   
 [サブスクリプションを検索する方法](../core/how-to-search-for-subscriptions.md)