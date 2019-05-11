---
title: チュートリアル 2:従業員 - 発注プロセス SQL アダプタの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eeb4dd1e-209a-47eb-9c0e-a138e02f0ff2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa2e0968743f88c9ae7d5b5ca683f0fb46d81f5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367486"
---
# <a name="tutorial-2-employee---purchase-order-process-using-the-sql-adapter"></a>チュートリアル 2:従業員 - 発注プロセス SQL アダプタの使用
このチュートリアルで、機器を配置する購買部門が毎回新しい従業員が組織に加わったを注文プロセスを自動化しています。 従業員の詳細と発注書の詳細の両方で管理**従業員**と**Purchase_Order**それぞれ、SQL Server データベース内のテーブルします。 購買部門は、SQL Server データベースで Purchase_Order テーブルを更新することを電子メールを送信して通知されます。 プロセスでは、次の操作が行われます。  
  
1. アダプターは受信するたびに通知、**従業員**テーブルを更新します。 次に、アダプターは、BizTalk オーケストレーションに、通知を送信します。  
  
2. BizTalk オーケストレーションが、通知が用に新しいレコードが挿入されるかどうかを判定、**従業員**テーブル。 通知の上の他の操作の場合、**従業員**テーブル、オーケストレーションの操作は実行されません。  
  
3. 場合は、通知が挿入操作では、**従業員**新しい従業員レコードが追加された、オーケストレーションを使用してのことを通知する、テーブル、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]新しいレコードの詳細を確認します。  
  
4. オーケストレーションでは、新しい追加された従業員レコードの詳細を含む応答を受信します。 オーケストレーションのマップ、 **Employee_ID**と**指定**挿入操作の要求メッセージに対する応答でフィールドに、 **Purchase_Order**テーブル。  
  
5. 次にオーケストレーションを使用して、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 、挿入操作を実行する、 **Purchase_Order**テーブル。 挿入操作の応答は、購買部門に電子メールとして送信されます。  
  
## <a name="about-the-database-objects-used-in-this-sample"></a>このサンプルで使用されるデータベース オブジェクトについて  
 このチュートリアルでは、サンプルに付属する SQL スクリプトによって作成されたデータベース オブジェクトを使用します。 スクリプトとサンプルの詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。 このチュートリアルで使用するデータベース オブジェクトは次のとおりです。  
  
- **ADAPTER_SAMPLES**データベース。  
  
- **従業員**と**Purchase_Order**テーブル。  
  
- **UPDATE_EMPLOYEE**ストアド プロシージャ。  
  
  このサンプルで提供される SQL スクリプトを実行するときに、これらすべてのデータベース オブジェクトが作成されます。 チュートリアルを開始する前に、スクリプトを実行することを確認します。  
  
## <a name="sample-based-on-this-tutorial"></a>このチュートリアルに基づくサンプル  
 サンプルについては、 **Employee_PurchaseOrder**でも提供するは、このチュートリアルに基づいて、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。  
  
 アダプターを使用して BizTalk プロジェクトを作成する方法を理解するには、完全にチュートリアルを読み進めるし、参照としてサンプルを見ることをお勧めします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [レッスン 1:スキーマを生成してメッセージを作成する](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)  
  
-   [レッスン 2:通知を受信してフィルター処理する](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)  
  
-   [レッスン 3:ストアド プロシージャを実行して、追加された新しい従業員を選択する](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)  
  
-   [レッスン 4:注文テーブルに対して挿入操作を実行する](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)  
  
-   [レッスン 5: ソリューションを展開する](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)