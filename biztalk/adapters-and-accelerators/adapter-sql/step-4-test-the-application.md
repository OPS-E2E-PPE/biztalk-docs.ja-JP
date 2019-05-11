---
title: 手順 4:アプリケーションのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 488b13fa-7a71-4430-bbf5-dbf47ba55562
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bf58bdbfb999016d76ecc48adfbf203bdcbcc5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367617"
---
# <a name="step-4-test-the-application"></a>手順 4:アプリケーションをテストします。
![手順 4 の 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **所要時間:** 10 分  
  
 **目標:** 内のレコードを挿入することで、アプリケーションをテストするこの手順で、**従業員**のテーブル、 **ADAPTER_SAMPLES**データベース。 オーケストレーションへの変更に関する通知を受け取る場合は、アプリケーションが正常に動作して、**従業員**テーブル。 次にオーケストレーションは、受信した通知の種類を抽出します。 オーケストレーションが実行される挿入操作では、通知がある場合、 **UPDATE_EMPLOYEE**ストアド プロシージャと、応答を受信します。 値を抽出します**Employee_ID**と**名前**の応答からにそれらを挿入し、 **Purchase_Order**テーブル。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を開始する前に、次を確認する必要があります。  
  
-   要求メッセージを呼び出し、 **UPDATE_EMPLOYEE**ストアド プロシージャは C:\TestLocation\CreateEmployeeMessage でご利用いただけます。 要求メッセージは、次のようになります。  
  
    ```  
    <UPDATE_EMPLOYEE xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedProcedures/dbo" />  
    ```  
  
-   要求メッセージに対して、挿入操作を呼び出す、 **Purchase_Order**テーブルが C:\TestLocation\CreatePOMessage でご利用いただけます。 要求メッセージは、次のようになります。  
  
    ```  
    <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Purchase_Order">  
      <Rows>  
        <Purchase_Order xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
          <Employee_ID>10</Employee_ID><Employee_Name>Employee_Name</Employee_Name>  
        </Purchase_Order>  
      </Rows>  
    </Insert>  
    ```  
  
    > [!NOTE]
    >  値、 **Employee_ID**と**Employee_Name**フィールドは、プレース ホルダーです。 実行時にオーケストレーションでは、実際の値が挿入されます。  
  
-   完了する必要があります[手順 3。構成し、アプリケーションを起動](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)します。  
  
### <a name="to-test-the-application"></a>アプリケーションをテストするには  
  
1.  内のレコードを挿入、**従業員**テーブル。 SQL Server Management Studio から次のステートメントを実行して行うことができます。  
  
    ```  
    INSERT INTO [ADAPTER_SAMPLES].[dbo].[Employee] ([Name] ,[Designation] ,[Salary])  
    VALUES('John Smith' ,'Manager' ,500000)  
    ```  
  
2.  チェック、**従業員**データベース内のテーブル。 によって、新しいレコードが追加されたことがわかります、**状態**列が「0」を返します。  
  
3.  更新の保持、**従業員**レコードのテーブルします。 表示になります、**状態**新しいレコードの列が「1」に設定されてようになりました  
  
4.  チェック、 **Purchase_Order**テーブル。 同じ employee name フィールドと、指定のレコード、Insert ステートメントで指定したとは、テーブルに追加することがわかります。  
  
5.  SMTP ポートの構成で、電子メールのエイリアスを指定した場合も、挿入操作の応答メッセージに電子メールが送信されます。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 内のレコードを挿入することで、SampleApplication アプリケーションをテスト、**従業員**テーブル。  
  
## <a name="next-steps"></a>次の手順  
 場合は、テストが成功した、おめでとうございます! 完了した、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]チュートリアル。  
  
 テストが成功しなかった場合はすべての必要なオブジェクトを追加し、プロパティを正しく設定することを確認する作業を慎重に確認します。  
  
## <a name="see-also"></a>参照  
 [ステップ 3:構成し、アプリケーションを起動します](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)   
 [レッスン 5: ソリューションを展開する](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)