---
title: "レッスン 3: 追加された新しい従業員を選択するストアド プロシージャの実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec7897e9-0c77-41b2-8cc2-61745bd3b028
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7af49c026b443fb1ca6a0fb7f35b64cdf1e377f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-3-execute-a-stored-procedure-to-select-new-employees-added"></a>レッスン 3: 追加された新しい従業員を選択するストアド プロシージャを実行します。
タスクを理解することは、このレッスンで実行される、前に、これらのタスクが必要な理由をまず理解する必要があります。 **従業員**ように、新しい従業員を追加するレコードを挿入するテーブルが定義されている、**ステータス**列は、新しい従業員が追加されるたびに、常に「0」に設定します。 これは、新しく追加した従業員を照会および通知の取得もこの列を使用できるようにします。 SQL Server で次の SQL ステートメントを実行して、このクエリは。  
  
```  
SELECT Employee_ID, Name, Designation FROM Employee WHERE Status = 0  
```  
  
 更新する必要がある従業員を追加の一覧を新しく受信後、**ステータス**「1」を同じクエリを実行して、次回新しい従業員を追加するために列が表示されないレコードの古い従業員もします。 上記の Select ステートメントは、新しく追加した従業員のみ、更新が表示されることを確認する、**従業員**表に、次の SQL ステートメントを使用します。  
  
```  
UPDATE Employee SET Status = 1 WHERE Status = 0  
```  
  
 そのため、**ステータス**古い従業員用の列に設定されている「1」の新しい従業員が「0」は常に、  
  
 このレッスンでは、ストアド プロシージャを実行します**UPDATE_EMPLOYEE**、さらに、Select ステートメントおよび Update ステートメントが実行されます。 このレッスンを完了したら、後に、オーケストレーションは、次を操作します。  
  
1.  変更に関する通知を受け取る、**従業員**テーブル。  
  
2.  受信した通知メッセージからの通知の種類を抽出します。  
  
3.  オーケストレーションが実行される挿入操作の通知メッセージがある場合、 **UPDATE_EMPLOYEE**ストアド プロシージャです。  
  
4.  ストアド プロシージャはで新しく入力されたレコードを読み取り、**従業員**テーブル。 ストアド プロシージャの後、新しいレコードを読み取り、設定も、**ステータス**「1」にそれらのレコードの列  
  
 今すぐ、ストアド プロシージャの実行が必要な理由がわかります。 これは、オーケストレーションの一部として実行する方法について検討する必要があります。 オーケストレーションに必要な要求メッセージを**UPDATE_EMPLOYEE**ストアド プロシージャです。 このチュートリアルでは、実行時に、メッセージが作成され、オーケストレーションに提供するカスタム クラス ライブラリを作成します。 オーケストレーションは、メッセージを受信した後、SQL アダプターを使用して SQL Server にメッセージを送信され応答を受信します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: UPDATE_EMPLOYEE の要求メッセージを作成するストアド プロシージャ](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)  
  
-   [手順 2: SQL Server に要求メッセージを送信し、応答を受信](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)