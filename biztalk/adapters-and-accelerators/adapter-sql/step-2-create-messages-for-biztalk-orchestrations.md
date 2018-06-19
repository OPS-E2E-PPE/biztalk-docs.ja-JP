---
title: '手順 2: BizTalk オーケストレーションのメッセージを作成する |Microsoft ドキュメント'
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
ms.openlocfilehash: 89b121d95992eb30240e38da434d1125df9db681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226114"
---
# <a name="step-2-create-messages-for-biztalk-orchestrations"></a>手順 2: BizTalk オーケストレーションのメッセージを作成します。
![手順 2 の 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")  
  
 **所要時間:** 5 分  
  
 **目標:** このステップでオーケストレーションを BizTalk プロジェクトに追加およびで生成したスキーマのメッセージを作成[手順 1: 操作のスキーマの生成](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 1: 操作のスキーマの生成](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)です。  
  
### <a name="to-create-messages-in-an-orchestration"></a>オーケストレーションでメッセージを作成するには  
  
1.  BizTalk オーケストレーションの BizTalk プロジェクトに追加[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]:  
  
    1.  ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。  
  
    2.  **新しい項目の追加** ダイアログ ボックスから、**カテゴリ**ボックスで、クリックして**オーケストレーション ファイル**です。 **テンプレート**ボックスで、クリックして**BizTalk オーケストレーション**です。  
  
    3.  BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。 このチュートリアルでは、名前を入力してください。`EmployeeOrch.odx`です。  
  
2.  開く、**オーケストレーション**がまだ開いていない場合、BizTalk プロジェクトのウィンドウ。 これを行うには、をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
3.  メッセージをオーケストレーションに追加します。  
  
    1.  **オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。  
  
    2.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
    3.  **プロパティ**ウィンドウ**Message_1**を次の操作します。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |[Identifier]|「`NotifyReceive`.|  
        |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して**Employee_PurchaseOrder.Notification**Employee_PurchaseOrder は、BizTalk プロジェクトの名前。 通知は、スキーマの生成、**通知**操作します。|  
  
    4.  次の 4 つの新しいメッセージを追加する前の手順を繰り返します — ストアド プロシージャの呼び出し、UPDATE_EMPLOYEE と別の要求-応答メッセージの設定を実行するための要求-応答メッセージが設定、**挿入**操作**Purchase_Order**テーブル。  
  
        |識別子に設定します。|メッセージの種類を設定|  
        |-----------------------|-------------------------|  
        |更新|*Employee_PurchaseOrder.TypedProcedure_dbo です。UPDATE_EMPLOYEE*ここで、TypedProcedure_dbo です。UPDATE_EMPLOYEE は、スキーマ、UPDATE_EMPLOYEE をストアド プロシージャです。|  
        |UpdateEmployeeResponse|*Employee_PurchaseOrder.TypedProcedure_dbo です。UPDATE_EMPLOYEEResponse*|  
        |InsertPO|*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.Insert*TableOperation_dbo_Purchase_Order.Insert は Purchase_Order テーブルに対する挿入操作のスキーマです。|  
        |InsertPOResponse|*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.InsertResponse*|  
  
    5.  オーケストレーション ファイルと、BizTalk プロジェクトを保存します。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 この手順で SQL Server を使用してに対する受信と送信操作を呼び出すためのメッセージを作成した、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
## <a name="next-steps"></a>次の手順  
 挿入操作では、SQL Server とフィルターの通知から通知を受信するオーケストレーション図形を追加する」の説明に従って[レッスン 2: 受信とフィルター通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)です。  
  
## <a name="see-also"></a>参照  
 [レッスン 1: スキーマを生成し、メッセージ作成](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)   
 [手順 1: 操作のスキーマを生成します。](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)