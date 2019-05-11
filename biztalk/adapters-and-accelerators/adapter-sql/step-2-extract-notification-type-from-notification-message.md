---
title: 手順 2:通知の種類を通知メッセージから抽出 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72f3e805-0f5f-42fa-8fe3-78ccbb375f74
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cca1b44daa45f5502957fa783cdf5e4e2ebca1e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367787"
---
# <a name="step-2-extract-notification-type-from-notification-message"></a>手順 2:通知メッセージからの通知の種類を抽出します。
![ステップ 2/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **所要時間:** 5 分  
  
 **目標:** この手順では、SQL Server データベースから受信した通知の種類を抽出する式図形を追加します。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 1。通知を受信するオーケストレーション図形を追加](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)します。  
  
### <a name="to-extract-the-notification-type-from-the-notification-message"></a>通知の種類を通知メッセージから抽出するには  
  
1.  作成した BizTalk オーケストレーションに変数を追加[手順 1。通知を受信するオーケストレーション図形を追加](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)します。  
  
    1.  オーケストレーションの種類を右クリックして**変数**、 をクリックし、**新しい変数**します。  
  
    2.  新しい変数を右クリックして**Variable_1**、 をクリック**プロパティ ウィンドウ**します。 変数の次のプロパティを設定します。  
  
        |このプロパティを設定します。|この値を|  
        |-----------------------|-------------------|  
        |**[Identifier]**|notificationType|  
        |**型**|System.String|  
  
2.  追加、**式**BizTalk オーケストレーションに図形。 オーケストレーション ツールボックスからドラッグして、**式**図形をオーケストレーション デザイン画面と、ドロップした後、**受信**図形  
  
     内で、**式**図形、SQL Server から受信した通知メッセージの種類を抽出する xpath クエリを追加します。 Xpath クエリを作成する前に、通知メッセージの形式について見てみましょう。 一般的な通知メッセージには、次のようになります。  
  
    ```  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
3.  通知の種類に関する情報は内で使用できるように、`<info>`親内のタグ`<Notification>`タグ。 そのため、次の xpath クエリ内の追加、**式**図形。  
  
    ```  
    NotificationType = xpath(NotifyReceive,"string(/*[local-name()='Notification']/*[local-name()='Info']/text())");  
    ```  
  
     ここでは、 **NotificationType** xpath クエリによって抽出された値を格納するために作成する変数です。 **NotifyReceive**で作成したメッセージは、[手順 2。BizTalk オーケストレーションのメッセージを作成する](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)通知メッセージを受信します。  
  
4.  次の図は、進行中のオーケストレーション、**式**図形が含まれています。  
  
     ![式図形をオーケストレーションに追加](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-02-add-expression-orch.gif "sql_adap_tut_02_add_expression_orch")  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順で追加した、**式**図形を SQL Server データベースから受信した通知の種類を抽出します。  
  
## <a name="next-steps"></a>次の手順  
 判断図形の挿入の通知をフィルター処理を追加する」の説明に従って[手順 3。挿入通知用のフィルターの追加](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)します。  
  
## <a name="see-also"></a>参照  
 [ステップ 1: 通知を受信するオーケストレーション図形を追加します。](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)   
 [ステップ 3:挿入通知用のフィルターを追加します。](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)   
 [レッスン 2:通知を受信してフィルター処理する](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)