---
title: "手順 4: アプリケーションのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 488b13fa-7a71-4430-bbf5-dbf47ba55562
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 347c2bcf459d7e9ce7b1fb9efc07579be81d989d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-the-application"></a>手順 4: アプリケーションをテストします。
![4 のステップ 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **所要時間:** 10 分  
  
 **目標:**内のレコードを挿入することで、アプリケーションをテストするこの手順で、**従業員**のテーブル、 **ADAPTER_SAMPLES**データベース。 オーケストレーションはへの変更の通知を受け取る場合は、アプリケーションが正しく機能する、**従業員**テーブル。 オーケストレーションは、受信した通知の種類を抽出します。 オーケストレーションが実行される挿入操作の通知がある場合、 **UPDATE_EMPLOYEE**ストアド プロシージャと、応答を受信します。 オーケストレーションの値を抽出する**Employee_ID**と**名前**応答からし、それらに挿入、 **Purchase_Order**テーブル。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を始める前に、次を確認する必要があります。  
  
-   要求メッセージを呼び出し、 **UPDATE_EMPLOYEE**ストアド プロシージャは C:\TestLocation\CreateEmployeeMessage に使用します。 要求メッセージは、次のようになります。  
  
    ```  
    <UPDATE_EMPLOYEE xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedProcedures/dbo" />  
    ```  
  
-   に対して、挿入操作を呼び出すための要求メッセージ、 **Purchase_Order**テーブルは C:\TestLocation\CreatePOMessage に使用します。 要求メッセージは、次のようになります。  
  
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
  
-   完了する必要があります[手順 3: 構成し、アプリケーションを起動](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)です。  
  
### <a name="to-test-the-application"></a>アプリケーションをテストするには  
  
1.  内のレコードを挿入、**従業員**テーブル。 SQL Server Management Studio から次のステートメントを実行して、これを行うことができます。  
  
    ```  
    INSERT INTO [ADAPTER_SAMPLES].[dbo].[Employee] ([Name] ,[Designation] ,[Salary])  
    VALUES('John Smith' ,'Manager' ,500000)  
    ```  
  
2.  チェック、**従業員**データベース内のテーブルです。 によって、新しいレコードが追加されていることを確認は、**ステータス**列が「0」を返します。  
  
3.  更新を保持、**従業員**レコードの表にします。 表示になります、**ステータス**新しいレコードの列は、現在「1」に設定  
  
4.  チェック、 **Purchase_Order**テーブル。 同じ従業員名の指定、レコード、Insert ステートメントに示されているがテーブルに追加することがわかります。  
  
5.  SMTP ポート構成では、電子メールのエイリアスを指定した場合も、挿入操作の応答メッセージに電子メールが送信されます。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 内のレコードを挿入することで、SampleApplication アプリケーションをテスト、**従業員**テーブル。  
  
## <a name="next-steps"></a>次の手順  
 テストが成功した場合、ソリューションに問題ありません。 完了して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]チュートリアルです。  
  
 テストが成功しなかった場合は、必要なオブジェクトをすべて追加しているかどうかと、プロパティを正しく設定しているかどうかを確認してください。  
  
## <a name="see-also"></a>参照  
 [手順 3: を構成し、アプリケーションを起動](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)   
 [レッスン 5: ソリューションを配置します。](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)