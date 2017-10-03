---
title: "チュートリアル 2: 従業員の発注プロセスには、SQL アダプターを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eeb4dd1e-209a-47eb-9c0e-a138e02f0ff2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fca0c11aeb1f84a5e9f05a4df4f995b7c2b52e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-2-employee---purchase-order-process-using-the-sql-adapter"></a>チュートリアル 2: 従業員の発注プロセスには、SQL アダプターを使用します。
このチュートリアルでは、新しい従業員が組織を結合するたびに、機器を配置する購買部門が順序付けプロセスを自動化するは。 従業員の詳細と発注書の詳細の両方で保持されます**従業員**と**Purchase_Order** SQL Server データベース内のテーブルと、それぞれします。 購買部門は、SQL Server データベースで Purchase_Order テーブルを更新して、電子メールを送信して通知を受け取ります。 プロセスでは、次の操作が行われます。  
  
1.  アダプターは受信するたびに通知、**従業員**テーブルが更新されます。 アダプターは、BizTalk オーケストレーションにし、通知を送信します。  
  
2.  BizTalk オーケストレーションの図に、新しいレコードが挿入されるため、通知のかどうかを**従業員**テーブル。 通知が、他の操作の場合、**従業員**テーブル、オーケストレーションの操作は実行されません。  
  
3.  通知が挿入操作の場合、**従業員**新しい従業員レコードを追加した、オーケストレーションを使用してのことを通知する、テーブル、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]新しいレコードの詳細を確認します。  
  
4.  オーケストレーションは、新しい従業員が追加されたレコードの詳細を含む応答を受信します。 オーケストレーションのマップ、 **Employee_ID**と**表記**挿入操作の要求メッセージへの応答でのフィールド、 **Purchase_Order**テーブル。  
  
5.  オーケストレーションを使用して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]挿入操作を実行する、 **Purchase_Order**テーブル。 挿入操作の応答には、購買部門に電子メールとして送信されます。  
  
## <a name="about-the-database-objects-used-in-this-sample"></a>このサンプルで使用されるデータベース オブジェクトについて  
 このチュートリアルでは、サンプルに付属の SQL スクリプトによって作成されたデータベース オブジェクトを使用します。 スクリプトとサンプルの詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。 このチュートリアルで使用するデータベース オブジェクトは次のとおりです。  
  
-   **ADAPTER_SAMPLES**データベース。  
  
-   **従業員**と**Purchase_Order**テーブル。  
  
-   **UPDATE_EMPLOYEE**ストアド プロシージャです。  
  
 このサンプルに用意されている SQL スクリプトを実行すると、これらすべてのデータベース オブジェクトが作成されます。 チュートリアルを開始する前に、スクリプトを実行することを確認してください。  
  
## <a name="sample-based-on-this-tutorial"></a>このチュートリアルに基づくサンプル  
 サンプルは、 **Employee_PurchaseOrder**、これは、このチュートリアルに基づいても付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。  
  
 チュートリアルを実行、アダプターを使用して BizTalk プロジェクトを作成する方法を理解するには、完全に移動し、参照として例を見てことをお勧めします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [レッスン 1: スキーマを生成し、メッセージ作成](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)  
  
-   [レッスン 2: 表示され、通知をフィルター処理](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)  
  
-   [レッスン 3: 追加された新しい従業員を選択するストアド プロシージャを実行します。](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)  
  
-   [レッスン 4: Purchase Order テーブルで挿入操作を実行します。](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)  
  
-   [レッスン 5: ソリューションを配置します。](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)