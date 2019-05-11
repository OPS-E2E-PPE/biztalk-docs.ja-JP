---
title: 手順 3:挿入通知用のフィルターの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53a1e9ef-a179-42a7-b4ae-b1170181053b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e49f4f914771a26618dd92126b49143492d627b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367925"
---
# <a name="step-3-add-a-filter-for-insert-notifications"></a>手順 3:挿入通知用のフィルターを追加します。
![ステップ 3/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **所要時間:** 5 分  
  
 **目標:** この手順では、挿入操作の通知メッセージのフィルター処理するオーケストレーションに判断図形を追加します。 オーケストレーション内の後続の操作は、受信した通知が挿入の型の場合にのみ実行されます。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 2。通知の種類を通知メッセージから抽出](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)します。  
  
### <a name="to-filter-for-notification-messages"></a>通知メッセージのフィルター処理するには  
  
1.  追加、**判断**、オーケストレーションに図形の後に、**式**図形。 ツールボックスからドラッグして、**判断**図形を区分線のすぐ下に、**式**図形。  
  
     **判断**図形の分岐が表示が展開、**場合**ステートメント **([rule_1])** の分岐および、 **Else**ステートメント。  
  
2.  デザイン サーフェイスを右クリックし、**判断**図形をクリックして**プロパティ ウィンドウ**します。  
  
3.  **プロパティ**のウィンドウ、**判断**図形、**名前**プロパティに「`CheckNotification`します。  
  
4.  デザイン サーフェイスを右クリックし、 **rule_1**図形 (内の**判断**図形) を順にクリックします**プロパティ ウィンドウ**します。  
  
5.  **プロパティ**ウィンドウ **[rule_1]** で、**名前**プロパティに「**挿入**します。  
  
6.  右クリックし、**挿入**図形をクリックして**ブール式の編集**します。  
  
7.  BizTalk 式エディターでは、次を入力します。  
  
    ```  
    NotificationType.Equals("Insert")  
    ```  
  
     この条件は場合にのみ後続の操作を実行するオーケストレーション内の値、 **NotificationType**変数が**挿入**します。  
  
    > [!NOTE]
    >  この変数を追加した[手順 2。通知の種類を通知メッセージから抽出](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)を SQL Server データベースから受信した通知メッセージから通知の種類を抽出します。  
  
8.  次の図は、進行中のオーケストレーション、**判断**図形が含まれています。  
  
     ![判断図形をオーケストレーションに追加](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-03-add-filter-orch.gif "sql_adap_tut_03_add_filter_orch")  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順で追加した、**判断**図形を受信した通知が挿入操作の場合にのみ後続の操作を実行する通知メッセージをフィルター処理します。  
  
## <a name="next-steps"></a>次の手順  
 次の手順で追加するオーケストレーション図形を UPDATE_EMPLOYE を呼び出すストアド プロシージャを使用、従業員テーブルを」の説明に従って[レッスン 3。追加された新しい従業員を選択するストアド プロシージャの実行](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)します。  
  
## <a name="see-also"></a>参照  
 [手順 2:通知メッセージからの通知の種類を抽出します。](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)   
 [レッスン 2:通知を受信してフィルター処理する](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)