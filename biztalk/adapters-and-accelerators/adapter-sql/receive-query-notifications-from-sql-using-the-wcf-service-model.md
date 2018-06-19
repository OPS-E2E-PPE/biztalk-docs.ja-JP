---
title: WCF サービス モデルを使用して SQL からクエリ通知を受け取る |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9def31-3c5a-4326-b798-31bde0ff2568
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b21d2123b646a02669a9da65efc5069931e64c69
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964088"
---
# <a name="receive-query-notifications-from-sql-using-the-wcf-service-model"></a><span data-ttu-id="e0a59-102">WCF サービス モデルを使用して SQL のクエリ通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-102">Receive Query Notifications from SQL using the WCF Service Model</span></span>
<span data-ttu-id="e0a59-103">このトピックの内容を構成する方法を示しています、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server データベースからクエリ通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-103">This topic demonstrates how to configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive query notification messages from a SQL Server database.</span></span> <span data-ttu-id="e0a59-104">通知を示すためには、テーブル、従業員、"Status"列を含むを検討してください。</span><span class="sxs-lookup"><span data-stu-id="e0a59-104">To demonstrate notifications, consider a table, Employee, with a “Status” column.</span></span> <span data-ttu-id="e0a59-105">このテーブルに新しいレコードが挿入されると、[状態] 列の値は 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-105">When a new record is inserted to this table, the value of the Status column is set to 0.</span></span> <span data-ttu-id="e0a59-106">[状態] 列が「0」であるすべてのレコードを取得する SQL ステートメントを使用して通知を登録することによって通知を受信するアダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-106">You can configure the adapter to receive notifications by registering for notifications using a SQL statement that retrieves all records that have Status column as “0.”</span></span> <span data-ttu-id="e0a59-107">これを行うための SQL ステートメントを指定することによって、 **NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e0a59-107">You can do so by specifying the SQL statement for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="e0a59-108">アダプターのクライアントは、通知を受信した後、SQL Server データベースで、それ以降の作業を実行するためのロジックを格納できます。</span><span class="sxs-lookup"><span data-stu-id="e0a59-108">After the adapter client receives the notification, it can contain the logic to do any subsequent tasks on the SQL Server database.</span></span> <span data-ttu-id="e0a59-109">わかりやすくするため、この例では、アダプターのクライアントが「0」として、[状態] 列を持つテーブル内のすべてのレコードを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-109">In this example, for the sake of simplicity, the adapter client lists all the records in the table that have the Status column as “0.”</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0a59-110">ユーザー定義型の列を含むテーブルでの操作を実行する場合、必ずするを参照してください[操作と、SQL アダプターを使用してユーザー定義型のテーブルとビューを](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)トピック アプリケーションの開発を開始する前に.</span><span class="sxs-lookup"><span data-stu-id="e0a59-110">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on tables and views with user-defined types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) topic before you start developing your application.</span></span>  
  
## <a name="configuring-notifications-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="e0a59-111">SQL アダプターのプロパティのバインドと通知の構成</span><span class="sxs-lookup"><span data-stu-id="e0a59-111">Configuring Notifications with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="e0a59-112">次の表、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティ構成の SQL Server から通知を受信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-112">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure receiving notifications from SQL Server.</span></span> <span data-ttu-id="e0a59-113">これらのバインディング プロパティを指定すると、SQL Server データベースから通知を受信する .NET アプリケーションの実行中にあります。</span><span class="sxs-lookup"><span data-stu-id="e0a59-113">You must specify these binding properties while running the .NET application to receive the notifications from a SQL Server database.</span></span>  
  
|<span data-ttu-id="e0a59-114">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="e0a59-114">Binding Property</span></span>|<span data-ttu-id="e0a59-115">Description</span><span class="sxs-lookup"><span data-stu-id="e0a59-115">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="e0a59-116">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="e0a59-116">**InboundOperationType**</span></span>|<span data-ttu-id="e0a59-117">受信操作を実行することを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-117">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="e0a59-118">通知メッセージを受信するには、これを設定**通知**です。</span><span class="sxs-lookup"><span data-stu-id="e0a59-118">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="e0a59-119">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="e0a59-119">**NotificationStatement**</span></span>|<span data-ttu-id="e0a59-120">SQL ステートメントを指定します (選択または EXEC \<*ストアド プロシージャ*\>) のクエリ通知を登録するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-120">Specifies the SQL statement (SELECT or EXEC \<*stored procedure*\>) used to register for query notifications.</span></span> <span data-ttu-id="e0a59-121">アダプターは、指定された SQL ステートメントの変更の結果セットの場合にのみ、SQL Server から通知メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-121">The adapter gets a notification message from SQL Server only when the result set for the specified SQL statement changes.</span></span>|  
|<span data-ttu-id="e0a59-122">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="e0a59-122">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="e0a59-123">リスナーが開始されたときに、アダプターがアダプターのクライアントに通知を送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-123">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="e0a59-124">これらのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="e0a59-124">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="e0a59-125">使用する方法の詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]さらに通知を受信する SQL Server から、読み取る。</span><span class="sxs-lookup"><span data-stu-id="e0a59-125">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive notifications from SQL Server, read further.</span></span>  
  
## <a name="configuring-notifications-using-the-wcf-service-model"></a><span data-ttu-id="e0a59-126">WCF サービス モデルを使用して通知を構成します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-126">Configuring Notifications Using the WCF Service Model</span></span>  
 <span data-ttu-id="e0a59-127">WCF サービス モデルを使用して通知を受信するには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0a59-127">To receive the notifications using the WCF service model, you must:</span></span>  
  
1.  <span data-ttu-id="e0a59-128">WCF サービス コントラクト (インターフェイス) を生成、**通知**アダプターによって公開されるメタデータから操作します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-128">Generate a WCF service contract (interface) for the **Notification** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="e0a59-129">これを行うには、使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e0a59-129">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
2.  <span data-ttu-id="e0a59-130">用の WCF クライアントを生成、**選択**Employee テーブルに対して操作します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-130">Generate a WCF client for the **Select** operation on the Employee table.</span></span> <span data-ttu-id="e0a59-131">これを行うには、使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e0a59-131">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
3.  <span data-ttu-id="e0a59-132">このインターフェイスから WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-132">Implement a WCF service from this interface.</span></span>  
  
4.  <span data-ttu-id="e0a59-133">サービス ホストを使用してこの WCF サービスをホスト (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="e0a59-133">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="e0a59-134">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="e0a59-134">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="e0a59-135">このトピックの例では、Employee テーブルに対して通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-135">The examples in this topic receive notification for the Employee table.</span></span> <span data-ttu-id="e0a59-136">テーブルを生成するスクリプトは、サンプルの値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e0a59-136">A script to generate the table is supplied with the samples.</span></span> <span data-ttu-id="e0a59-137">サンプルの詳細については、次を参照してください。 [SQL アダプタ サンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="e0a59-137">For more information about the samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="e0a59-138">サンプルは、 **Notification_ServiceModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="e0a59-138">A sample, **Notification_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="e0a59-139">WCF サービス コントラクトとクラス</span><span class="sxs-lookup"><span data-stu-id="e0a59-139">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="e0a59-140">使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびサポートするためのクラスを作成する、**通知**操作します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-140">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Notification** operation.</span></span> <span data-ttu-id="e0a59-141">詳細については、WCF サービス コントラクトを生成する、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="e0a59-141">For more information about generating a WCF service contract, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="e0a59-142">WCF サービス コントラクト (インターフェイス)</span><span class="sxs-lookup"><span data-stu-id="e0a59-142">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="e0a59-143">次のコードに対して生成される WCF サービス コントラクト (インターフェイス) を示しています、**通知**操作します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-143">The following code shows the WCF service contract (interface) generated for the **Notification** operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/", ConfigurationName="NotificationOperation")]  
public interface NotificationOperation {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Notification/) of message  
    // Notification does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="Notification")]  
    void Notification(Notification request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="e0a59-144">メッセージ コントラクト</span><span class="sxs-lookup"><span data-stu-id="e0a59-144">The Message Contracts</span></span>  
 <span data-ttu-id="e0a59-145">通知操作のメッセージ コントラクトを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-145">Following is the message contract for the Notification operation.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Notification", WrapperNamespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", IsWrapped=true)]  
public partial class Notification {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=0)]  
    public string Info;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=1)]  
    public string Source;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=2)]  
    public string Type;  
  
    public Notification() {  
    }  
  
    public Notification(string Info, string Source, string Type) {  
        this.Info = Info;  
        this.Source = Source;  
        this.Type = Type;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="e0a59-146">WCF サービス クラス</span><span class="sxs-lookup"><span data-stu-id="e0a59-146">WCF Service Class</span></span>  
 <span data-ttu-id="e0a59-147">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装、WCF サービス クラスのスタブを持つファイルも生成します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-147">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="e0a59-148">ファイルの名前は、SqlAdapterBindingService.cs です。</span><span class="sxs-lookup"><span data-stu-id="e0a59-148">The name of the file is SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="e0a59-149">処理するロジックを挿入することができます、**通知**このクラスに直接操作します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-149">You can insert the logic to process the **Notification** operation directly into this class.</span></span> <span data-ttu-id="e0a59-150">次のコードによって生成された WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e0a59-150">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace SqlAdapterBindingNamespace {  
  
    public class SqlAdapterBindingService : NotificationOperation {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Notification/)   
        // of message Notification does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
        public virtual void Notification(Notification request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-query-notifications-using-wcf-service-model"></a><span data-ttu-id="e0a59-151">WCF サービスのモデルを使用してクエリ通知を受信</span><span class="sxs-lookup"><span data-stu-id="e0a59-151">Receiving Query Notifications Using WCF Service Model</span></span>  
 <span data-ttu-id="e0a59-152">このセクションの内容を使用してクエリ通知を受信する .NET アプリケーションを作成する方法の手順を説明する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e0a59-152">This section provides instructions on how to write a .NET application to receive query notifications using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
#### <a name="to-receive-query-notifications"></a><span data-ttu-id="e0a59-153">クエリ通知を受信するには</span><span class="sxs-lookup"><span data-stu-id="e0a59-153">To receive query notifications</span></span>  
  
1.  <span data-ttu-id="e0a59-154">使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]用の WCF クライアントを生成する**選択**での操作、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="e0a59-154">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF client for **Select** operation on the **Employee** table.</span></span> <span data-ttu-id="e0a59-155">通知メッセージを受信後に Select 操作を実行するのにこのクライアントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-155">You will use this client to perform Select operations after receiving a notification message.</span></span> <span data-ttu-id="e0a59-156">新しいクラスを TableOperation.cs をプロジェクトに追加し、Select 操作を実行する次のコード スニペットを追加します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-156">Add a new class, TableOperation.cs to your project and add the following code snippet to perform a Select operation.</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
  
    namespace Notification_ServiceModel  
    {  
        public class TableOperation  
        {  
            public void TableOp()  
            {  
                ///////////////////////////////////////////////////////////////////////  
                // CREATING THE CLIENT  
                ///////////////////////////////////////////////////////////////////////  
  
                TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee");  
  
                client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
                client.ClientCredentials.UserName.Password = "<Enter password here>";  
  
                ///////////////////////////////////////////////////////////////////////  
                // OPENING THE CLIENT  
                ///////////////////////////////////////////////////////////////////////  
  
                try  
                {  
                    Console.WriteLine("Opening Client...");  
                    client.Open();  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Exception: " + ex.Message);  
                    throw;  
                }  
  
                ///////////////////////////////////////////////////////////////////////  
                // SELECTING THE LAST INSERTED RECORD FROM THE TABLE  
                ///////////////////////////////////////////////////////////////////////  
                schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] selectRecords;  
  
                try  
                {  
                    selectRecords = client.Select("*", "where Status=0");  
                }  
  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Exception: " + ex.Message);  
                    throw;  
                }  
  
                Console.WriteLine("The details of the newly added employee are:");  
                Console.WriteLine("********************************************");  
                for (int i = 0; i < selectRecords.Length; i++)  
                {  
                    Console.WriteLine("Employee Name      : " + selectRecords[i].Name);  
                    Console.WriteLine("Employee Designation: " + selectRecords[i].Designation);  
                    Console.WriteLine("Employee Status    : " + selectRecords[i].Status);  
                    Console.WriteLine();  
                }  
                Console.WriteLine("********************************************");  
  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e0a59-157">このコード スニペットは、Point UDT 列を含む Employee テーブルでの操作を実行するため、アプリケーションの実行中に、プロジェクトの \bin\Debug フォルダーの下、UDT の DLL を配置することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-157">Because this code snippet performs operations on the Employee table that contains a Point UDT column, make sure you put the UDT DLL under the project’s \bin\Debug folder while running the application.</span></span>  
  
2.  <span data-ttu-id="e0a59-158">使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびためのヘルパー クラスを生成する、**通知**操作します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-158">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Notification** operation.</span></span>  
  
     <span data-ttu-id="e0a59-159">詳細については、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="e0a59-159">For more information, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span> <span data-ttu-id="e0a59-160">サービス コントラクトとヘルパー クラスを生成するときに、必要に応じてバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e0a59-160">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="e0a59-161">これは、生成された構成ファイルで正しく設定されていることを保証します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-161">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
3.  <span data-ttu-id="e0a59-162">手順 2. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-162">Implement a WCF service from the interface and helper classes generated in step 2.</span></span> <span data-ttu-id="e0a59-163">**通知**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、操作を中止する例外をスローできます、**通知**操作ですそれ以外の場合、メソッドは。何も返しません。</span><span class="sxs-lookup"><span data-stu-id="e0a59-163">The **Notification** method of this class can throw an exception to abort the operation, if an error is encountered processing the data received from the **Notification** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="e0a59-164">次のように、WCF サービス クラスを属性する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0a59-164">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     <span data-ttu-id="e0a59-165">内で、**通知**メソッドを直接、アプリケーション ロジックを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="e0a59-165">Within the **Notification** method, you can implement your application logic directly.</span></span> <span data-ttu-id="e0a59-166">このクラスは、SqlAdapterBindingService.cs で確認できます。</span><span class="sxs-lookup"><span data-stu-id="e0a59-166">This class can be found in SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="e0a59-167">この例では、このコードはサブ クラス、 **SqlAdapterBindingService**クラスです。</span><span class="sxs-lookup"><span data-stu-id="e0a59-167">This code in this example sub-classes the **SqlAdapterBindingService** class.</span></span> <span data-ttu-id="e0a59-168">このコードでは、受信した通知メッセージは、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="e0a59-168">In this code, the notification message received is written to the console.</span></span> <span data-ttu-id="e0a59-169">さらに、 **TableOp**メソッド内で、 **TableOperation**選択操作を実行するクラスが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e0a59-169">Additionally, the **TableOp** method within the **TableOperation** class is invoked to perform the Select operation.</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class NotificationService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void Notification(Notification request)  
        {  
            Console.WriteLine("\nNew Notification Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine(request.Info);  
            Console.WriteLine(request.Source);  
            Console.WriteLine(request.Type);  
            Console.WriteLine("*************************************************");  
  
            // Invoke th TableOp method in the TableOperation class  
            TableOperation Ops = new TableOperation();  
            Ops.TableOp();  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="e0a59-170">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]資格情報を受け入れません接続 URI の一部として、SQL Server データベースの資格情報を渡すには、次のクラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0a59-170">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not accept credentials as part of the connection URI, you must implement the following class to pass credentials for the SQL Server database.</span></span> <span data-ttu-id="e0a59-171">アプリケーションの後半で、SQL Server 資格情報を渡すには、このクラスがインスタンス化されします。</span><span class="sxs-lookup"><span data-stu-id="e0a59-171">In the latter part of the application, you will instantiate this class to pass on the SQL Server credentials.</span></span>  
  
    ```  
    class NotificationCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new NotificationCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
    ```  
  
5.  <span data-ttu-id="e0a59-172">作成、 **SqlAdapterBinding**とバインドのプロパティを指定することでクエリ通知を受信するアダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-172">Create a **SqlAdapterBinding** and configure the adapter to receive query notifications by specifying the binding properties.</span></span> <span data-ttu-id="e0a59-173">これは、コードで明示的にまたは構成で宣言によって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e0a59-173">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="e0a59-174">指定する必要がありますには、少なくとも、 **InboundOperationType**と**NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e0a59-174">At a minimum, you must specify the **InboundOperationType** and **NotificationStatement** binding properties.</span></span>  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    binding.InboundOperationType = InboundOperation.Notification;  
    binding.NotificationStatement = "SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0";  
    binding.NotifyOnListenerStart = true;  
    ```  
  
6.  <span data-ttu-id="e0a59-175">SQL Server データベース資格情報を指定するには、インスタンス化する、 **NotificationCredentials**手順 4. で作成したクラスです。</span><span class="sxs-lookup"><span data-stu-id="e0a59-175">Specify SQL Server database credentials by instantiating the **NotificationCredentials** class you created in Step 4.</span></span>  
  
    ```  
    NotificationCredentials credentials = new NotificationCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
7.  <span data-ttu-id="e0a59-176">手順 3 で作成した WCF サービスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-176">Create an instance of the WCF service created in step 3.</span></span>  
  
    ```  
    // create service instance  
    NotificationService service = new NotificationService();  
    ```  
  
8.  <span data-ttu-id="e0a59-177">インスタンスを作成する**System.ServiceModel.ServiceHost** WCF サービスと基本接続 URI を使用しています。</span><span class="sxs-lookup"><span data-stu-id="e0a59-177">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="e0a59-178">また、ここで、資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0a59-178">You must also specify the credentials here.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
9. <span data-ttu-id="e0a59-179">サービス ホストにサービス エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-179">Add a service endpoint to the service host.</span></span> <span data-ttu-id="e0a59-180">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="e0a59-180">To do this:</span></span>  
  
    -   <span data-ttu-id="e0a59-181">手順 5. で作成したバインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-181">Use the binding created in step 5.</span></span>  
  
    -   <span data-ttu-id="e0a59-182">接続の資格情報を含む URI を指定し、必要に応じて、入力方向の id。</span><span class="sxs-lookup"><span data-stu-id="e0a59-182">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
    -   <span data-ttu-id="e0a59-183">"NotificationOperation"としてコントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-183">Specify the contract as "NotificationOperation".</span></span>  
  
    ```  
    // Add service endpoint: be sure to specify NotificationOperation as the contract  
    Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
    serviceHost.AddServiceEndpoint("NotificationOperation", binding, ConnectionUri);  
    ```  
  
10. <span data-ttu-id="e0a59-184">通知メッセージを受信するには、サービス ホストを開きます。</span><span class="sxs-lookup"><span data-stu-id="e0a59-184">To receive notification message, open the service host.</span></span>  
  
    ```  
    // Open the service host to begin receiving notifications  
    serviceHost.Open();  
    ```  
  
11. <span data-ttu-id="e0a59-185">通知の受信を停止するには、サービス ホストを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e0a59-185">To stop receiving notifications, close the service host.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="e0a59-186">例</span><span class="sxs-lookup"><span data-stu-id="e0a59-186">Example</span></span>  
 <span data-ttu-id="e0a59-187">次の例では、Employee テーブルの通知メッセージを受信する .NET アプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-187">The following example shows a .NET application to receive notification messages for the Employee table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0a59-188">次のコード スニペットをインスタンス化、 **TableOperation.cs**クラスとなり、 **TableOp**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="e0a59-188">The following code snippet instantiates a **TableOperation.cs** class and invokes the **TableOp** method.</span></span> <span data-ttu-id="e0a59-189">クラスとメソッドについては、手順 1. で説明します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-189">The class and the method are described in Step 1.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
using Microsoft.Adapters.Sql;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace Notification_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    public class NotificationService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void Notification(Notification request)  
        {  
            Console.WriteLine("\nNew Notification Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine(request.Info);  
            Console.WriteLine(request.Source);  
            Console.WriteLine(request.Type);  
            Console.WriteLine("*************************************************");  
            TableOperation Ops = new TableOperation();  
            Ops.TableOp();  
        }  
    }  
  
    class NotificationCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new NotificationCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost serviceHost = null;  
            try  
            {  
                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.Notification;  
                binding.NotificationStatement = "SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0";  
                binding.NotifyOnListenerStart = true;  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId (if any) that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // a query_string (InboundID); otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
  
                NotificationCredentials credentials = new NotificationCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                NotificationService service = new NotificationService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("NotificationOperation", binding, ConnectionUri);  
                serviceHost.Open();  
                Console.WriteLine("Service host opened...");  
                Console.WriteLine("Waiting for notification...");  
  
                Console.WriteLine("\nHit <RETURN> to stop receiving notification");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                // If there is an error it will be specified in the inner exception   
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop receiving notifications  
                if (serviceHost.State == CommunicationState.Opened)  
                    serviceHost.Close();  
                else  
                    serviceHost.Abort();  
            }  
        }  
    }  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0a59-190">参照</span><span class="sxs-lookup"><span data-stu-id="e0a59-190">See Also</span></span>  
[<span data-ttu-id="e0a59-191">WCF サービス モデルを使用して SQL アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="e0a59-191">Develop SQL applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)