---
title: WCF サービス Model1 を使用して Oracle データベースの変更通知を受け取る |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0f0e2bf-3e76-43cc-85dc-7483dbce1cb5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed8723cef3351420cbe35e0f9fc85d2ba400b410
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217050"
---
# <a name="receive-oracle-database-change-notifications-using-the-wcf-service-model1"></a><span data-ttu-id="711df-102">WCF サービス Model1 を使用して Oracle データベースの変更通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="711df-102">Receive Oracle Database Change Notifications Using the WCF Service Model1</span></span>
<span data-ttu-id="711df-103">このトピックの内容を構成する方法を示しています、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースからクエリ通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="711df-103">This topic demonstrates how to configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive query notification messages from an Oracle database.</span></span> <span data-ttu-id="711df-104">通知を示すためには、ACCOUNTACTIVITY、列を含むテーブル「処理」を検討してください。</span><span class="sxs-lookup"><span data-stu-id="711df-104">To demonstrate notifications, consider a table, ACCOUNTACTIVITY, with a “Processed” column.</span></span> <span data-ttu-id="711df-105">[状態] 列の値に設定がこのテーブルに新しいレコードが挿入されると、' n ' です。</span><span class="sxs-lookup"><span data-stu-id="711df-105">When a new record is inserted to this table, the value of the Status column is set to ‘n’.</span></span> <span data-ttu-id="711df-106">通知を受信すると「処理済み」の列が含まれるすべてのレコードを取得する SQL ステートメントを使用して通知を登録することによって、アダプターを構成することができます 'n' です。</span><span class="sxs-lookup"><span data-stu-id="711df-106">You can configure the adapter to receive notifications by registering for notifications using a SQL statement that retrieves all records that have “Processed” column as ‘n’.</span></span> <span data-ttu-id="711df-107">これを行うための SQL ステートメントを指定することによって、 **NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="711df-107">You can do so by specifying the SQL statement for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="711df-108">アダプターのクライアントは、通知を受信した後は、Oracle データベースでの後続のタスクを実行するためのロジックを格納できます。</span><span class="sxs-lookup"><span data-stu-id="711df-108">Once the adapter client receives the notification, it can contain the logic to do any subsequent tasks on the Oracle database.</span></span> <span data-ttu-id="711df-109">わかりやすくするため、この例では、アダプターのクライアントの一覧として「処理」列が含まれるテーブル内のすべてのレコード 'n' です。</span><span class="sxs-lookup"><span data-stu-id="711df-109">In this example, for the sake of simplicity, the adapter client lists all the records in the table that have the “Processed” column as ‘n’.</span></span>  
  
## <a name="configuring-notifications-with-the-oracle-database-adapter-binding-properties"></a><span data-ttu-id="711df-110">Oracle データベース アダプターのプロパティをバインドに通知を構成します。</span><span class="sxs-lookup"><span data-stu-id="711df-110">Configuring Notifications with the Oracle Database Adapter Binding Properties</span></span>  
 <span data-ttu-id="711df-111">下の表にまとめて、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用して Oracle データベースから通知の受信を構成するプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="711df-111">The table below summarizes the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding properties that you use to configure receiving notifications from Oracle database.</span></span> <span data-ttu-id="711df-112">これらのバインディング プロパティを指定すると、通知を受信する .NET アプリケーションの実行中にあります。</span><span class="sxs-lookup"><span data-stu-id="711df-112">You must specify these binding properties while running the .NET application to receive notifications.</span></span>  
  
|<span data-ttu-id="711df-113">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="711df-113">Binding Property</span></span>|<span data-ttu-id="711df-114">Description</span><span class="sxs-lookup"><span data-stu-id="711df-114">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="711df-115">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="711df-115">**InboundOperationType**</span></span>|<span data-ttu-id="711df-116">受信操作を実行することを指定します。</span><span class="sxs-lookup"><span data-stu-id="711df-116">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="711df-117">通知メッセージを受信するには、これを設定**通知**です。</span><span class="sxs-lookup"><span data-stu-id="711df-117">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="711df-118">**NotificationPort**</span><span class="sxs-lookup"><span data-stu-id="711df-118">**NotificationPort**</span></span>|<span data-ttu-id="711df-119">ODP.NET が Oracle データベースからデータベースの変更通知をリッスンするように開く必要があるポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="711df-119">Specifies the port number that ODP.NET must open to listen for database change notification from Oracle database.</span></span>|  
|<span data-ttu-id="711df-120">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="711df-120">**NotificationStatement**</span></span>|<span data-ttu-id="711df-121">クエリ通知の登録に使用する SELECT ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="711df-121">Specifies the SELECT statement used to register for query notifications.</span></span> <span data-ttu-id="711df-122">アダプターは、指定した SELECT ステートメントの変更の結果セットの場合にのみ、通知メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="711df-122">The adapter gets a notification message only when the result set for the specified SELECT statement changes.</span></span>|  
|<span data-ttu-id="711df-123">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="711df-123">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="711df-124">リスナーが開始されたときに、アダプターがアダプターのクライアントに通知を送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="711df-124">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="711df-125">これらのプロパティの詳細については、次を参照してください。 [Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="711df-125">For a more complete description of these properties, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span> <span data-ttu-id="711df-126">使用する方法の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]さらに通知を受信する Oracle データベースから、読み取る。</span><span class="sxs-lookup"><span data-stu-id="711df-126">For a complete description of how to use the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive notifications from Oracle database, read further.</span></span>  
  
## <a name="configuring-notifications-using-the-wcf-service-model"></a><span data-ttu-id="711df-127">WCF サービス モデルを使用して通知を構成します。</span><span class="sxs-lookup"><span data-stu-id="711df-127">Configuring Notifications Using the WCF Service Model</span></span>  
 <span data-ttu-id="711df-128">WCF サービス モデルを使用して通知を受信するには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="711df-128">To receive the notifications using the WCF service model, you must:</span></span>  
  
-   <span data-ttu-id="711df-129">WCF サービス コントラクト (インターフェイス) を生成、**通知**アダプターによって公開されるメタデータから操作します。</span><span class="sxs-lookup"><span data-stu-id="711df-129">Generate a WCF service contract (interface) for the **Notification** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="711df-130">これを行うには、使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="711df-130">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
-   <span data-ttu-id="711df-131">用の WCF クライアントを生成、**選択**ACCOUNTACTIVITY テーブルで操作します。</span><span class="sxs-lookup"><span data-stu-id="711df-131">Generate a WCF client for the **Select** operation on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="711df-132">これを行うには、使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="711df-132">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
-   <span data-ttu-id="711df-133">このインターフェイスから WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="711df-133">Implement a WCF service from this interface.</span></span>  
  
-   <span data-ttu-id="711df-134">サービス ホストを使用してこの WCF サービスをホスト (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="711df-134">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="711df-135">WCF サービス コントラクトとクラス</span><span class="sxs-lookup"><span data-stu-id="711df-135">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="711df-136">使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびサポートするためのクラスを作成する、**通知**操作します。</span><span class="sxs-lookup"><span data-stu-id="711df-136">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Notification** operation.</span></span> <span data-ttu-id="711df-137">詳細については、WCF サービス コントラクトを生成する、次を参照してください。 [WCF クライアントまたは Oracle データベース ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="711df-137">For more information about generating a WCF service contract, see [Generate a WCF client or a WCF service contract for Oracle Database solution artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="711df-138">WCF サービス コントラクト (インターフェイス)</span><span class="sxs-lookup"><span data-stu-id="711df-138">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="711df-139">次のコードに対して生成される WCF サービス コントラクト (インターフェイス) を示しています、**通知**操作します。</span><span class="sxs-lookup"><span data-stu-id="711df-139">The following code shows the WCF service contract (interface) generated for the **Notification** operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03", ConfigurationName="Notification_OperationGroup")]  
public interface Notification_OperationGroup {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/Notification/) of message Notification  
    // does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="http://Microsoft.LobServices.OracleDB/2007/03/Notification")]  
    void Notification(Notification request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="711df-140">メッセージ コントラクト</span><span class="sxs-lookup"><span data-stu-id="711df-140">The Message Contracts</span></span>  
 <span data-ttu-id="711df-141">通知操作のメッセージ コントラクトを次に示します。</span><span class="sxs-lookup"><span data-stu-id="711df-141">Following is the message contract for the Notification operation.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Notification", WrapperNamespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", IsWrapped=true)]  
public partial class Notification {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", Order=0)]  
    public microsoft.lobservices.oracledb._2007._03.Notification.NotificationDetails[] Details;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", Order=1)]  
    public string Info;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", Order=2)]  
    public string[] ResourceNames;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", Order=3)]  
    public string Source;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", Order=4)]  
    public string Type;  
  
    public Notification() {  
    }  
  
    public Notification(microsoft.lobservices.oracledb._2007._03.Notification.NotificationDetails[] Details, string Info, string[] ResourceNames, string Source, string Type) {  
        this.Details = Details;  
        this.Info = Info;  
        this.ResourceNames = ResourceNames;  
        this.Source = Source;  
        this.Type = Type;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="711df-142">WCF サービス クラス</span><span class="sxs-lookup"><span data-stu-id="711df-142">WCF Service Class</span></span>  
 <span data-ttu-id="711df-143">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装、WCF サービス クラスのスタブを持つファイルも生成します。</span><span class="sxs-lookup"><span data-stu-id="711df-143">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="711df-144">ファイルの名前は、OracleDBBindingService.cs です。</span><span class="sxs-lookup"><span data-stu-id="711df-144">The name of the file is OracleDBBindingService.cs.</span></span> <span data-ttu-id="711df-145">処理するロジックを挿入することができます、**通知**このクラスに直接操作します。</span><span class="sxs-lookup"><span data-stu-id="711df-145">You can insert the logic to process the **Notification** operation directly into this class.</span></span> <span data-ttu-id="711df-146">次のコードによって生成された WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="711df-146">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace OracleDBBindingNamespace {  
  
    public class OracleDBBindingService : Notification_OperationGroup {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/Notification/) of message Notification  
        // does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
        public virtual void Notification(Notification request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-database-change-notifications-using-wcf-service-model"></a><span data-ttu-id="711df-147">WCF サービスのモデルを使用して、受信側のデータベース変更通知</span><span class="sxs-lookup"><span data-stu-id="711df-147">Receiving Database Change Notifications Using WCF Service Model</span></span>  
 <span data-ttu-id="711df-148">このセクションの内容を使用してクエリ通知を受信する .NET アプリケーションを作成する方法の手順を説明する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="711df-148">This section provides instructions on how to write a .NET application to receive query notifications using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
#### <a name="to-receive-query-notifications"></a><span data-ttu-id="711df-149">クエリ通知を受信するには</span><span class="sxs-lookup"><span data-stu-id="711df-149">To receive query notifications</span></span>  
  
1.  <span data-ttu-id="711df-150">使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]用の WCF クライアントを生成する**選択**での操作、 **ACCOUNTACTIVITY**テーブル。</span><span class="sxs-lookup"><span data-stu-id="711df-150">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF client for **Select** operation on the **ACCOUNTACTIVITY** table.</span></span> <span data-ttu-id="711df-151">通知メッセージを受信後に Select 操作を実行するのにこのクライアントを使用します。</span><span class="sxs-lookup"><span data-stu-id="711df-151">You will use this client to perform Select operations after receiving a notification message.</span></span> <span data-ttu-id="711df-152">新しいクラスを TableOperation.cs をプロジェクトに追加し、Select 操作を実行する次のコード スニペットを追加します。</span><span class="sxs-lookup"><span data-stu-id="711df-152">Add a new class, TableOperation.cs to your project and add the following code snippet to perform a Select operation.</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
  
    namespace Notification_ServiceModel  
    {  
        class TableOperation  
        {  
            public void TableOp()  
            {  
                //////////////////////////////////////////////////////////////////////  
                // CREATING THE CLIENT AND SETTING CLIENT CREDENTIALS  
                //////////////////////////////////////////////////////////////////////  
  
                SCOTT_Table_ACCOUNTACTIVITYClient client = new SCOTT_Table_ACCOUNTACTIVITYClient("OracleDBBinding_SCOTT_Table_ACCOUNTACTIVITY");  
                client.ClientCredentials.UserName.UserName = "SCOTT";  
                client.ClientCredentials.UserName.Password = "TIGER";  
  
                ////////////////////////////////////////////////////////////////////  
                // OPENING THE CLIENT  
                //////////////////////////////////////////////////////////////////////  
                try  
                {  
                    Console.WriteLine("Opening the client ...");  
                    client.Open();  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Exception: " + ex.Message);  
                    throw;  
                }  
  
                ////////////////////////////////////////////////////////////////////////////////////////  
                // SELECTING THE LAST INSERTED VALUE  
                ////////////////////////////////////////////////////////////////////////////////////////  
  
                Console.WriteLine("The application will now select the last inserted record");  
  
                microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] selectRecords;  
  
                try  
                {  
                    selectRecords = client.Select("*", "WHERE PROCESSED = 'n'");  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Exception: " + ex.Message);  
                    throw;  
                }  
  
                Console.WriteLine("The details of the newly added records are:");  
                Console.WriteLine("********************************************");  
                for (int i = 0; i < selectRecords.Length; i++)  
                {  
                    Console.WriteLine("Transaction ID   : " + selectRecords[i].TID);  
                    Console.WriteLine("Account ID       : " + selectRecords[i].ACCOUNT);  
                    Console.WriteLine("Processed Status : " + selectRecords[i].PROCESSED);  
                    Console.WriteLine();  
                }  
                Console.WriteLine("********************************************");  
            }  
        }  
    }  
  
    ```  
  
2.  <span data-ttu-id="711df-153">使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびためのヘルパー クラスを生成する、**通知**操作します。</span><span class="sxs-lookup"><span data-stu-id="711df-153">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Notification** operation.</span></span>  
  
     <span data-ttu-id="711df-154">詳細については、次を参照してください。 [WCF クライアントまたは Oracle データベース ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="711df-154">For more information, see [Generate a WCF client or a WCF service contract for Oracle Database solution artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span></span> <span data-ttu-id="711df-155">サービス コントラクトとヘルパー クラスを生成するときに、必要に応じてバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="711df-155">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="711df-156">これは、生成された構成ファイルで正しく設定されていることを保証します。</span><span class="sxs-lookup"><span data-stu-id="711df-156">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
3.  <span data-ttu-id="711df-157">手順 2. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="711df-157">Implement a WCF service from the interface and helper classes generated in step 2.</span></span> <span data-ttu-id="711df-158">**通知**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、操作を中止する例外をスローできます、**通知**操作ですそれ以外の場合、メソッドは。何も返しません。</span><span class="sxs-lookup"><span data-stu-id="711df-158">The **Notification** method of this class can throw an exception to abort the operation, if an error is encountered processing the data received from the **Notification** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="711df-159">次のように、WCF サービス クラスを属性する必要があります。</span><span class="sxs-lookup"><span data-stu-id="711df-159">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     <span data-ttu-id="711df-160">内で、**通知**メソッドを直接、アプリケーション ロジックを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="711df-160">Within the **Notification** method, you can implement your application logic directly.</span></span> <span data-ttu-id="711df-161">このクラスは、OracleDBBindingService.cs で確認できます。</span><span class="sxs-lookup"><span data-stu-id="711df-161">This class can be found in OracleDBBindingService.cs.</span></span> <span data-ttu-id="711df-162">この例では、このコードはサブ クラス、 **OracleDBBindingService**クラスです。</span><span class="sxs-lookup"><span data-stu-id="711df-162">This code in this example sub-classes the **OracleDBBindingService** class.</span></span> <span data-ttu-id="711df-163">このコードでは、受信した通知メッセージは、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="711df-163">In this code, the notification message received is written to the console.</span></span> <span data-ttu-id="711df-164">さらに、 **TableOp**メソッド内で、 **TableOperation**選択操作を実行するクラスが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="711df-164">Additionally, the **TableOp** method within the **TableOperation** class is invoked to perform the Select operation.</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
        public class NotificationService : OracleDBBindingNamespace.OracleDBBindingService  
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
    ```  
  
4.  <span data-ttu-id="711df-165">Oracle データベースの資格情報を渡すには、次のクラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="711df-165">You must implement the following class to pass credentials for the Oracle database.</span></span> <span data-ttu-id="711df-166">アプリケーションの後半では、資格情報を渡すには、このクラスがインスタンス化されします。</span><span class="sxs-lookup"><span data-stu-id="711df-166">In the latter part of the application, you will instantiate this class to pass on the credentials.</span></span>  
  
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
  
5.  <span data-ttu-id="711df-167">作成、 **OracleDBBinding**とバインドのプロパティを指定することでクエリ通知を受信するアダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="711df-167">Create an **OracleDBBinding** and configure the adapter to receive query notifications by specifying the binding properties.</span></span> <span data-ttu-id="711df-168">これは、コードで明示的にまたは構成で宣言によって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="711df-168">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="711df-169">指定する必要がありますには、少なくとも、 **InboundOperationType**と**NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="711df-169">At a minimum, you must specify the **InboundOperationType** and **NotificationStatement** binding properties.</span></span>  
  
    ```  
    OracleDBBinding binding = new OracleDBBinding();  
    binding.InboundOperationType = InboundOperation.Notification;  
    binding.NotificationStatement = "SELECT TID,ACCOUNT,PROCESSED FROM APPS.ACCOUNTACTIVITY WHERE PROCESSED = 'n'";  
    binding.NotifyOnListenerStart = true;  
    binding.NotificationPort = 10;  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="711df-170">値、 **NotificationPort** Windows ファイアウォールの例外一覧に追加する必要があります同じポート番号に binding プロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="711df-170">The value for the **NotificationPort** binding property must be set to the same port number that you must have added to the Windows Firewall exceptions list.</span></span> <span data-ttu-id="711df-171">Windows ファイアウォールの例外リストにポートを追加する方法については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=196959](http://go.microsoft.com/fwlink/?LinkId=196959)です。</span><span class="sxs-lookup"><span data-stu-id="711df-171">For instructions on how to add ports to Windows Firewall exceptions list, see [http://go.microsoft.com/fwlink/?LinkId=196959](http://go.microsoft.com/fwlink/?LinkId=196959).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="711df-172">設定しない場合、 **NotificationPort**バインディング プロパティ、アダプターのこのバインドのプロパティに達すると-1 の既定値は想定します。</span><span class="sxs-lookup"><span data-stu-id="711df-172">If you do not set the **NotificationPort** binding property, the adapter will assume the default value of -1 for this binding property.</span></span> <span data-ttu-id="711df-173">このような場合は、完全に通知メッセージを受け取るための Windows ファイアウォールを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="711df-173">In such a case, you will have to completely disable Windows Firewall to receive notification messages.</span></span>  
  
6.  <span data-ttu-id="711df-174">インスタンス化して Oracle データベースの資格情報の指定、 **NotificationCredentials**手順 4. で作成したクラスです。</span><span class="sxs-lookup"><span data-stu-id="711df-174">Specify Oracle database credentials by instantiating the **NotificationCredentials** class you created in Step 4.</span></span>  
  
    ```  
    NotificationCredentials credentials = new NotificationCredentials();  
    credentials.UserName.UserName = "SCOTT";  
    credentials.UserName.Password = "TIGER";  
    ```  
  
7.  <span data-ttu-id="711df-175">手順 3 で作成した WCF サービスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="711df-175">Create an instance of the WCF service created in step 3.</span></span>  
  
    ```  
    // create service instance  
    NotificationService service = new NotificationService();  
    ```  
  
8.  <span data-ttu-id="711df-176">インスタンスを作成する**System.ServiceModel.ServiceHost** WCF サービスと基本接続 URI を使用しています。</span><span class="sxs-lookup"><span data-stu-id="711df-176">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="711df-177">また、ここで、資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="711df-177">You must also specify the credentials here.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("oracledb://adapter") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
9. <span data-ttu-id="711df-178">サービス ホストにサービス エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="711df-178">Add a service endpoint to the service host.</span></span> <span data-ttu-id="711df-179">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="711df-179">To do this:</span></span>  
  
    -   <span data-ttu-id="711df-180">手順 5. で作成したバインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="711df-180">Use the binding created in step 5.</span></span>  
  
    -   <span data-ttu-id="711df-181">接続の資格情報を含む URI を指定し、必要に応じて、入力方向の id。</span><span class="sxs-lookup"><span data-stu-id="711df-181">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
    -   <span data-ttu-id="711df-182">"Notification_OperationGroup"としてコントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="711df-182">Specify the contract as "Notification_OperationGroup".</span></span>  
  
    ```  
    // Add service endpoint: be sure to specify Notification_OperationGroup as the contract  
    Uri ConnectionUri = new Uri("oracledb://adapter");  
    serviceHost.AddServiceEndpoint("Notification_OperationGroup", binding, ConnectionUri);  
    ```  
  
10. <span data-ttu-id="711df-183">通知メッセージを受信するには、サービス ホストを開きます。</span><span class="sxs-lookup"><span data-stu-id="711df-183">To receive notification message, open the service host.</span></span>  
  
    ```  
    // Open the service host to begin receiving notifications  
    serviceHost.Open();  
    ```  
  
11. <span data-ttu-id="711df-184">通知の受信を停止するには、サービス ホストを閉じます。</span><span class="sxs-lookup"><span data-stu-id="711df-184">To stop receiving notifications, close the service host.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="711df-185">例</span><span class="sxs-lookup"><span data-stu-id="711df-185">Example</span></span>  
 <span data-ttu-id="711df-186">次の例では、ACCOUNTACTIVITY テーブルの通知メッセージを受信する .NET アプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="711df-186">The following example shows a .NET application to receive notification messages for the ACCOUNTACTIVITY table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="711df-187">次のコード スニペットをインスタンス化、 **TableOperation.cs**クラスとなり、 **TableOp**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="711df-187">The following code snippet instantiates a **TableOperation.cs** class and invokes the **TableOp** method.</span></span> <span data-ttu-id="711df-188">クラスとメソッドについては、手順 1. で説明します。</span><span class="sxs-lookup"><span data-stu-id="711df-188">The class and the method are described in Step 1.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Microsoft.Adapters.OracleDB;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace Notification_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class NotificationService : OracleDBBindingNamespace.OracleDBBindingService  
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
                Console.WriteLine("Sample started...");  
                Console.WriteLine("Press any key to start receiving notifications...");  
                Console.ReadLine();  
  
                OracleDBBinding binding = new OracleDBBinding();  
                binding.InboundOperationType = InboundOperation.Notification;  
                binding.NotificationStatement = "SELECT TID,ACCOUNT,PROCESSED FROM APPS.ACCOUNTACTIVITY WHERE PROCESSED = 'n'";  
                binding.NotifyOnListenerStart = true;  
                binding.NotificationPort = 10;  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("oracledb://adapter");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // an InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("oracledb://adapter") };  
  
                NotificationCredentials credentials = new NotificationCredentials();  
                credentials.UserName.UserName = "SCOTT";  
                credentials.UserName.Password = "TIGER";  
  
                Console.WriteLine("Opening service host...");  
                NotificationService service = new NotificationService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("Notification_OperationGroup", binding, ConnectionUri);  
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
  
                /* If there is an error it will be specified in the inner exception */  
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop polling  
                if (serviceHost.State == CommunicationState.Opened)  
                    serviceHost.Close();  
                else  
                    serviceHost.Abort();  
            }  
  
        }  
    }  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="711df-189">参照</span><span class="sxs-lookup"><span data-stu-id="711df-189">See Also</span></span>  
 [<span data-ttu-id="711df-190">WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="711df-190">Develop Oracle Database applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)