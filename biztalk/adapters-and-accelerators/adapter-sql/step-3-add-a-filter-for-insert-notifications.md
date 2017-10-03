---
title: "手順 3: 挿入の通知にフィルターを追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53a1e9ef-a179-42a7-b4ae-b1170181053b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97fc32fe7dd657bb45edca91fda0eddaa537b32a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-add-a-filter-for-insert-notifications"></a>手順 3: 挿入の通知にフィルターを追加します。
![手順 3 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **所要時間:** 5 分  
  
 **目標:**ここでは、挿入操作の通知メッセージのフィルター処理するオーケストレーションに判断図形を追加します。 オーケストレーションでの後続の操作は、通知を受け取りましたが Insert 型の場合にのみ実行されます。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 2: 通知メッセージから通知の種類を抽出](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)です。  
  
### <a name="to-filter-for-notification-messages"></a>通知メッセージのフィルター処理するには  
  
1.  追加、**判断**、オーケストレーションに図形の後に、**式**図形です。 ツールボックスからドラッグして、**判断**図形を区分線のすぐ下に、**式**図形です。  
  
     **判断**用に分岐を表示する図形が展開され、**場合**ステートメント**(Rule_1)**の分岐および、 **Else**ステートメントです。  
  
2.  デザイン サーフェイスを右クリックし、**判断**図形をクリックして**プロパティ ウィンドウ**します。  
  
3.  **プロパティ**のウィンドウ、**判断**図形、**名前**プロパティで、「`CheckNotification`です。  
  
4.  デザイン サーフェイスを右クリックし、 **rule_1**図形 (内の**判断**図形)、をクリックして**プロパティ ウィンドウ**します。  
  
5.  **プロパティ**ウィンドウ**[rule_1]**で、**名前**プロパティで、「**挿入**です。  
  
6.  右クリックし、**挿入**図形をクリックして**ブール式の編集**です。  
  
7.  BizTalk 式エディターで、次に入力します。  
  
    ```  
    NotificationType.Equals("Insert")  
    ```  
  
     この状態通知の場合にのみ、後続の操作を実行するオーケストレーションの値、 **NotificationType**変数が**挿入**です。  
  
    > [!NOTE]
    >  この変数を追加した[手順 2: 通知メッセージから通知の種類を抽出](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)通知の種類を SQL Server データベースから受信した通知メッセージから抽出します。  
  
8.  次の図は、進行中のオーケストレーション、**判断**図形が含まれています。  
  
     ![判断図形をオーケストレーションに追加](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-03-add-filter-orch.gif "sql_adap_tut_03_add_filter_orch")  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 この手順で追加した、**判断**図形を受信する通知が挿入操作の場合にのみ、後続の操作を実行する通知メッセージをフィルター処理します。  
  
## <a name="next-steps"></a>次の手順  
 次の手順で追加する Employee テーブルでのストアド プロシージャを UPDATE_EMPLOYE を呼び出すためのオーケストレーション図形」の説明に従って[レッスン 3: 追加された新しい従業員を選択するストアド プロシージャを実行して](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)です。  
  
## <a name="see-also"></a>参照  
 [手順 2: 通知メッセージからの通知の種類を抽出します。](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)   
 [レッスン 2: 表示され、通知をフィルター処理](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)