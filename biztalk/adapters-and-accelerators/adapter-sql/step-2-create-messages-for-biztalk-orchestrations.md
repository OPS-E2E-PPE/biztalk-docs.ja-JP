---
title: 手順 2:BizTalk オーケストレーションのメッセージの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47a4fb98-6085-4aeb-ab39-2f2c3858d4e0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 026dd9f832ee0422a49c520db65f0d3b1cd79de7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367823"
---
# <a name="step-2-create-messages-for-biztalk-orchestrations"></a>手順 2:BizTalk オーケストレーションのメッセージを作成します。
![手順 2 の 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")  
  
 **所要時間:** 5 分  
  
 **目標:** このステップでオーケストレーションを BizTalk プロジェクトに追加し、で生成したスキーマのメッセージを作成[手順 1。操作のスキーマを生成](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 1。操作のスキーマを生成](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)します。  
  
### <a name="to-create-messages-in-an-orchestration"></a>オーケストレーションでメッセージを作成するには  
  
1. BizTalk オーケストレーションの BizTalk プロジェクトに追加[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]:  
  
   1.  ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。  
  
   2.  **新しい項目の追加**] ダイアログ ボックスから、**カテゴリ**ボックスで、[**オーケストレーション ファイル**します。 **テンプレート**ボックスで、 **BizTalk オーケストレーション**します。  
  
   3.  BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。 このチュートリアルでは、名前を入力します。`EmployeeOrch.odx`します。  
  
2. 開く、**オーケストレーション**がまだ開いていない場合、BizTalk プロジェクトのウィンドウ。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
3. オーケストレーションへメッセージを追加します。  
  
   1.  **オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。  
  
   2.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  
  
   3.  **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  
  
       |プロパティ|目的|  
       |--------------|----------------|  
       |[Identifier]|「`NotifyReceive`.|  
       |メッセージ型|ドロップダウン リストから展開**スキーマ**、選び**Employee_PurchaseOrder.Notification**Employee_PurchaseOrder は、BizTalk プロジェクトの名前です。 通知は、スキーマの生成、**通知**操作。|  
  
   4.  4 つの新しいメッセージを追加する前の手順を繰り返します: 要求-応答メッセージの設定、UPDATE_EMPLOYEE を呼び出すストアド プロシージャと、別の要求-応答メッセージの設定を実行するための**挿入**操作**Purchase_Order**テーブル。  
  
       |識別子を設定するには|メッセージの種類を設定|  
       |-----------------------|-------------------------|  
       |更新|*Employee_PurchaseOrder.TypedProcedure_dbo します。UPDATE_EMPLOYEE*ここで、TypedProcedure_dbo します。UPDATE_EMPLOYEE は、スキーマを UPDATE_EMPLOYEE ストアド プロシージャです。|  
       |UpdateEmployeeResponse|*Employee_PurchaseOrder.TypedProcedure_dbo.UPDATE_EMPLOYEEResponse*|  
       |InsertPO|*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.Insert*TableOperation_dbo_Purchase_Order.Insert は Purchase_Order テーブルに対する挿入操作のスキーマです。|  
       |InsertPOResponse|*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.InsertResponse*|  
  
   5.  オーケストレーション ファイルと、BizTalk プロジェクトを保存します。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順では、受信と送信操作を使用して SQL Server を実行を呼び出すためのメッセージを作成、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
## <a name="next-steps"></a>次の手順  
 挿入操作の SQL Server とフィルターの通知から通知を受信するオーケストレーション図形を追加する」の説明に従って[レッスン 2。受信して通知をフィルター処理](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)します。  
  
## <a name="see-also"></a>参照  
 [レッスン 1:スキーマを生成し、メッセージの作成](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)   
 [ステップ 1: 操作のスキーマを生成する](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)