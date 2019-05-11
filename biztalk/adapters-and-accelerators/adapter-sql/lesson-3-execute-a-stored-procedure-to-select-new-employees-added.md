---
title: 'レッスン 3: 追加された新しい従業員を選択するストアド プロシージャの実行 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec7897e9-0c77-41b2-8cc2-61745bd3b028
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a008b2a85b1cfda3383c175bc9ed24b2f012d9cf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368666"
---
# <a name="lesson-3-execute-a-stored-procedure-to-select-new-employees-added"></a>レッスン 3: 追加された新しい従業員を選択するストアド プロシージャを実行します。
このレッスンでは、タスクを理解することが実行される前に、これらのタスクが必要な理由をまず理解する必要があります。 **従業員**ような方法で、新しい従業員を追加するレコードを挿入するテーブルが定義されているが、**状態**列は、新しい従業員が追加されるたびに、常に「0」に設定します。 これは、新しく追加された従業員に対してクエリを実行し、通知を受け取ることも、この列を使用できるようにします。 SQL Server で次の SQL ステートメントを実行してこのクエリは。  
  
```  
SELECT Employee_ID, Name, Designation FROM Employee WHERE Status = 0  
```  
  
 更新する必要がある従業員を追加の一覧を新しく受信後、**状態**「1」を同じクエリを実行して、次回の新しい従業員を追加するために列が表示されないレコードの古い従業員もします。 上記の Select ステートメントは、新しく追加された従業員のみを更新するかどうかを確認する、**従業員**表の次の SQL ステートメントを使用します。  
  
```  
UPDATE Employee SET Status = 1 WHERE Status = 0  
```  
  
 そのため、**状態**古い従業員を対象の列は、新しい従業員が「0」は常に「1」に設定されます  
  
 このレッスンでは、ストアド プロシージャを実行する**UPDATE_EMPLOYEE**、さらに、Select および Update ステートメントを実行します。 このレッスンを完了したら、後に、オーケストレーションは、次を操作します。  
  
1. 変更の通知を受け取る、**従業員**テーブル。  
  
2. 受信した通知メッセージから通知の種類を抽出します。  
  
3. 通知メッセージの挿入操作の場合、オーケストレーションの実行、 **UPDATE_EMPLOYEE**ストアド プロシージャ。  
  
4. ストアド プロシージャで新たに入力されたレコードの読み取り、**従業員**テーブル。 ストアド プロシージャのもの設定、新しいレコードを読んだら、**状態**「1」にそれらのレコードの列  
  
   これでストアド プロシージャを実行する必要がある理由がわかります。 これは、オーケストレーションの一部として実行する方法について検討する必要があります。 オーケストレーションに必要な要求メッセージを**UPDATE_EMPLOYEE**ストアド プロシージャ。 このチュートリアルでは、その場でメッセージが作成され、オーケストレーションに提供するカスタム クラス ライブラリを作成します。 オーケストレーションはメッセージを受信後 SQL アダプターを使用して SQL Server にメッセージを送信し、応答を受信します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ステップ 1: UPDATE_EMPLOYEE ストアド プロシージャの要求メッセージを作成する](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)  
  
-   [手順 2:SQL Server に要求メッセージを送信し、応答を受信する](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)