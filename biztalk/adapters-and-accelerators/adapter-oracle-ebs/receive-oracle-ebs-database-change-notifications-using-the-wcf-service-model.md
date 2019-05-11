---
title: WCF サービス モデルを使用して Oracle E-business Suite データベース変更通知の受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 362193f5-2586-480f-a62e-1ed5e4ef342c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20791bda1cffd0bc28e6f7ef5f326496e6bd96b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374688"
---
# <a name="receive-oracle-e-business-suite-database-change-notifications-using-the-wcf-service-model"></a><span data-ttu-id="00f11-102">WCF サービス モデルを使用して Oracle E-business Suite データベース変更通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="00f11-102">Receive Oracle E-Business Suite database change notifications using the WCF service model</span></span>
<span data-ttu-id="00f11-103">このトピックでは、構成する方法を示します、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースからクエリ通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="00f11-103">This topic demonstrates how to configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive query notification messages from an Oracle database.</span></span> <span data-ttu-id="00f11-104">通知を示すために、テーブル、ACCOUNTACTIVITY、「処理済み」列を含むについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="00f11-104">To demonstrate notifications, consider a table, ACCOUNTACTIVITY, with a “Processed” column.</span></span> <span data-ttu-id="00f11-105">[状態] 列の値を"n"にします設定をこのテーブルに新しいレコードが挿入されると、</span><span class="sxs-lookup"><span data-stu-id="00f11-105">When a new record is inserted to this table, the value of the Status column is set to “n.”</span></span> <span data-ttu-id="00f11-106">"N"と「処理済み」列が含まれるすべてのレコードを取得する SQL ステートメントを使用して通知を登録することで通知を受信するアダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="00f11-106">You can configure the adapter to receive notifications by registering for notifications using a SQL statement that retrieves all records that have “Processed” column as “n.”</span></span> <span data-ttu-id="00f11-107">SQL ステートメントを指定することによって行うことができます、 **NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="00f11-107">You can do so by specifying the SQL statement for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="00f11-108">アダプターのクライアントが通知を受信した後、Oracle データベースで、後続のタスクを実行するロジックを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="00f11-108">After the adapter client receives the notification, it can contain the logic to do any subsequent tasks on the Oracle database.</span></span> <span data-ttu-id="00f11-109">わかりやすくする、この例では、アダプター クライアントは、"n"と「処理済み」列が含まれるテーブル内のすべてのレコードを一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="00f11-109">In this example, for the sake of simplicity, the adapter client lists all the records in the table that have the “Processed” column as “n.”</span></span>  
  
## <a name="configuring-notifications-with-the-oracle-e-business-adapter-binding-properties"></a><span data-ttu-id="00f11-110">Oracle E-business アダプターのバインドのプロパティと通知の構成</span><span class="sxs-lookup"><span data-stu-id="00f11-110">Configuring Notifications with the Oracle E-Business Adapter Binding Properties</span></span>  
 <span data-ttu-id="00f11-111">次の表にまとめたものです、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite から通知を受け取る構成に使用するプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="00f11-111">The table below summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure receiving notifications from Oracle E-Business Suite.</span></span> <span data-ttu-id="00f11-112">通知を受信する .NET アプリケーションを実行中には、これらのバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00f11-112">You must specify these binding properties while running the .NET application to receive notifications.</span></span>  
  
|<span data-ttu-id="00f11-113">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="00f11-113">Binding Property</span></span>|<span data-ttu-id="00f11-114">説明</span><span class="sxs-lookup"><span data-stu-id="00f11-114">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="00f11-115">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="00f11-115">**InboundOperationType**</span></span>|<span data-ttu-id="00f11-116">実行する受信操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="00f11-116">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="00f11-117">通知メッセージを受信するこれを設定**通知**します。</span><span class="sxs-lookup"><span data-stu-id="00f11-117">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="00f11-118">**NotificationPort**</span><span class="sxs-lookup"><span data-stu-id="00f11-118">**NotificationPort**</span></span>|<span data-ttu-id="00f11-119">Oracle データベースからのデータベース変更通知をリッスンする ODP.NET を開く必要があるポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="00f11-119">Specifies the port number that ODP.NET must open to listen for database change notification from Oracle database.</span></span>|  
|<span data-ttu-id="00f11-120">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="00f11-120">**NotificationStatement**</span></span>|<span data-ttu-id="00f11-121">クエリ通知に登録するために使用する Select ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="00f11-121">Specifies the Select statement used to register for query notifications.</span></span> <span data-ttu-id="00f11-122">アダプターは、指定した Select ステートメントの変更の結果セットの場合にのみ、通知メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="00f11-122">The adapter gets a notification message only when the result set for the specified Select statement changes.</span></span>|  
|<span data-ttu-id="00f11-123">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="00f11-123">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="00f11-124">リスナーが開始されると、アダプターがアダプター クライアントに通知を送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="00f11-124">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="00f11-125">これらのプロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="00f11-125">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="00f11-126">使用する方法の詳細については、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite から通知を受信するには、このトピックの残りの部分を読み取る。</span><span class="sxs-lookup"><span data-stu-id="00f11-126">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive notifications from Oracle E-Business Suite, read the remainder of this topic.</span></span>  
  
## <a name="configuring-notifications-using-the-wcf-service-model"></a><span data-ttu-id="00f11-127">WCF サービス モデルを使用して通知を構成します。</span><span class="sxs-lookup"><span data-stu-id="00f11-127">Configuring Notifications Using the WCF Service Model</span></span>  
 <span data-ttu-id="00f11-128">WCF サービス モデルを使用して通知を受信するには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="00f11-128">To receive the notifications using the WCF service model, you must:</span></span>  
  
- <span data-ttu-id="00f11-129">WCF サービス コントラクト (インターフェイス) を生成、**通知**アダプターによって公開されているメタデータから操作します。</span><span class="sxs-lookup"><span data-stu-id="00f11-129">Generate a WCF service contract (interface) for the **Notification** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="00f11-130">これを行うには、使用する可能性があります、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="00f11-130">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
- <span data-ttu-id="00f11-131">用の WCF クライアントを生成、**選択**ACCOUNTACTIVITY テーブルに対する操作。</span><span class="sxs-lookup"><span data-stu-id="00f11-131">Generate a WCF client for the **Select** operation on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="00f11-132">これを行うには、使用する可能性があります、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="00f11-132">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
- <span data-ttu-id="00f11-133">このインターフェイスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="00f11-133">Implement a WCF service from this interface.</span></span>  
  
- <span data-ttu-id="00f11-134">サービス ホストを使用してこの WCF サービス ホスト (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="00f11-134">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="00f11-135">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="00f11-135">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="00f11-136">このトピックの例では、ACCOUNTACTIVITY テーブル通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="00f11-136">The examples in this topic receives notification for the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="00f11-137">テーブルを生成するスクリプトは、サンプルで提供されます。</span><span class="sxs-lookup"><span data-stu-id="00f11-137">A script to generate the table is supplied with the samples.</span></span> <span data-ttu-id="00f11-138">サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="00f11-138">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="00f11-139">サンプルについては、 **Notification_ServiceModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="00f11-139">A sample, **Notification_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="00f11-140">WCF サービス コントラクトとクラス</span><span class="sxs-lookup"><span data-stu-id="00f11-140">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="00f11-141">使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とサポートのクラスを作成する、**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="00f11-141">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Notification** operation.</span></span> <span data-ttu-id="00f11-142">WCF サービス コントラクトを生成する詳細については、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="00f11-142">For more information about generating a WCF service contract, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="00f11-143">WCF サービス コントラクト (インターフェイス)</span><span class="sxs-lookup"><span data-stu-id="00f11-143">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="00f11-144">次のコードに対して生成された WCF サービス コントラクト (インターフェイス) を示しています、**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="00f11-144">The following code shows the WCF service contract (interface) generated for the **Notification** operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/", ConfigurationName="Notification_")]  
public interface Notification_ {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/Notification/) of message Notification   
    // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="Notification")]  
    void Notification(Notification request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="00f11-145">メッセージ コントラクト</span><span class="sxs-lookup"><span data-stu-id="00f11-145">The Message Contracts</span></span>  
 <span data-ttu-id="00f11-146">通知操作のメッセージ コントラクトを次に示します。</span><span class="sxs-lookup"><span data-stu-id="00f11-146">Following is the message contract for the Notification operation.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Notification", WrapperNamespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", IsWrapped=true)]  
public partial class Notification {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=0)]  
    public schemas.microsoft.com.OracleEBS._2008._05.Notification.NotificationDetails[] Details;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=1)]  
    public string Info;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=2)]  
    public string[] ResourceNames;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=3)]  
    public string Source;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=4)]  
    public string Type;  
  
    public Notification() {  
    }  
  
    public Notification(schemas.microsoft.com.OracleEBS._2008._05.Notification.NotificationDetails[] Details, string Info, string[] ResourceNames, string Source, string Type) {  
        this.Details = Details;  
        this.Info = Info;  
        this.ResourceNames = ResourceNames;  
        this.Source = Source;  
        this.Type = Type;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="00f11-147">WCF サービス クラス</span><span class="sxs-lookup"><span data-stu-id="00f11-147">WCF Service Class</span></span>  
 <span data-ttu-id="00f11-148">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装された WCF サービス クラスのスタブを持つファイルも生成されます。</span><span class="sxs-lookup"><span data-stu-id="00f11-148">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="00f11-149">ファイルの名前は、OracleEBSBindingService.cs です。</span><span class="sxs-lookup"><span data-stu-id="00f11-149">The name of the file is OracleEBSBindingService.cs.</span></span> <span data-ttu-id="00f11-150">処理するロジックを挿入することができます、**通知**このクラスに直接操作します。</span><span class="sxs-lookup"><span data-stu-id="00f11-150">You can insert the logic to process the **Notification** operation directly into this class.</span></span> <span data-ttu-id="00f11-151">次のコードによって生成される WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="00f11-151">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace OracleEBSBindingNamespace {  
  
    public class OracleEBSBindingService : Notification_ {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/Notification/) of message Notification   
        // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
        public virtual void Notification(Notification request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-query-notifications-using-wcf-service-model"></a><span data-ttu-id="00f11-152">WCF サービス モデルを使用してクエリ通知の受信</span><span class="sxs-lookup"><span data-stu-id="00f11-152">Receiving Query Notifications Using WCF Service Model</span></span>  
 <span data-ttu-id="00f11-153">このセクションを使用してクエリ通知を受信する .NET アプリケーションを作成する方法の説明、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="00f11-153">This section provides instructions on how to write a .NET application to receive query notifications using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
#### <a name="to-receive-query-notifications"></a><span data-ttu-id="00f11-154">クエリ通知を受信するには</span><span class="sxs-lookup"><span data-stu-id="00f11-154">To receive query notifications</span></span>  
  
1. <span data-ttu-id="00f11-155">使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]用の WCF クライアントを生成する**選択**操作、 **ACCOUNTACTIVITY**テーブル。</span><span class="sxs-lookup"><span data-stu-id="00f11-155">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF client for **Select** operation on the **ACCOUNTACTIVITY** table.</span></span> <span data-ttu-id="00f11-156">このクライアントを使用して、通知メッセージを受信した後、Select 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="00f11-156">You will use this client to perform Select operations after receiving a notification message.</span></span> <span data-ttu-id="00f11-157">TableOperation.cs、新しいクラスをプロジェクトに追加し、選択操作を実行する次のコード スニペットを追加します。</span><span class="sxs-lookup"><span data-stu-id="00f11-157">Add a new class, TableOperation.cs, to your project and add the following code snippet to perform a Select operation.</span></span>  
  
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
  
               Tables_APPS_ACCOUNTACTIVITYClient client = new Tables_APPS_ACCOUNTACTIVITYClient();  
               client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
               client.ClientCredentials.UserName.Password = "<Enter password here>";  
  
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
               // SELECTING THE LAST INSERTED VALUES  
               ////////////////////////////////////////////////////////////////////////////////////////  
               Console.WriteLine("The application will now select the last inserted record");  
  
               schemas.microsoft.com.OracleEBS._2008._05.TableViewRecord.APPS.ACCOUNTACTIVITY.SelectRecord[] selectRecords;  
  
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
  
2. <span data-ttu-id="00f11-158">使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とのヘルパー クラスを生成する、**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="00f11-158">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Notification** operation.</span></span>  
  
    <span data-ttu-id="00f11-159">詳細については、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="00f11-159">For more information, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span> <span data-ttu-id="00f11-160">必要に応じて、サービス コントラクトとヘルパー クラスを生成するときにバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="00f11-160">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="00f11-161">これは、生成された構成ファイルで設定は正しくことを保証します。</span><span class="sxs-lookup"><span data-stu-id="00f11-161">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
3. <span data-ttu-id="00f11-162">手順 2 で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="00f11-162">Implement a WCF service from the interface and helper classes generated in step 2.</span></span> <span data-ttu-id="00f11-163">**通知**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、操作を中止する例外をスローできます、**通知**操作ですそれ以外の場合、メソッドでは。何も返しません。</span><span class="sxs-lookup"><span data-stu-id="00f11-163">The **Notification** method of this class can throw an exception to abort the operation, if an error is encountered processing the data received from the **Notification** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="00f11-164">次のように、WCF サービス クラスを属性する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00f11-164">You must attribute the WCF service class as follows:</span></span>  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  
  
    <span data-ttu-id="00f11-165">内で、**通知**メソッドを直接、アプリケーション ロジックを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="00f11-165">Within the **Notification** method, you can implement your application logic directly.</span></span> <span data-ttu-id="00f11-166">このクラスは、OracleEBSBindingService.cs で確認できます。</span><span class="sxs-lookup"><span data-stu-id="00f11-166">This class can be found in OracleEBSBindingService.cs.</span></span> <span data-ttu-id="00f11-167">この例では、このコードはサブ クラス、 **OracleEBSBindingService**クラス。</span><span class="sxs-lookup"><span data-stu-id="00f11-167">This code in this example sub-classes the **OracleEBSBindingService** class.</span></span> <span data-ttu-id="00f11-168">このコードでは、通知メッセージを受信は、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="00f11-168">In this code, the notification message received is written to the console.</span></span> <span data-ttu-id="00f11-169">さらに、 **TableOp**内のメソッド、 **TableOperation**選択操作を実行するクラスが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="00f11-169">Additionally, the **TableOp** method within the **TableOperation** class is invoked to perform the Select operation.</span></span>  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
   public class NotificationService : OracleEBSBindingNamespace.OracleEBSBindingService  
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
  
4. <span data-ttu-id="00f11-170">Oracle E-business suite の資格情報を渡すには、次のクラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00f11-170">You must implement the following class to pass credentials for the Oracle E-Business Suite.</span></span> <span data-ttu-id="00f11-171">アプリケーションの後半部分の資格情報を渡すには、このクラスをインスタンス化されます。</span><span class="sxs-lookup"><span data-stu-id="00f11-171">In the latter part of the application, you will instantiate this class to pass on the credentials.</span></span>  
  
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
  
5. <span data-ttu-id="00f11-172">作成、 **OracleEBSBinding**とバインドのプロパティを指定することでクエリ通知を受信するアダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="00f11-172">Create an **OracleEBSBinding** and configure the adapter to receive query notifications by specifying the binding properties.</span></span> <span data-ttu-id="00f11-173">コードで明示的に、または構成で宣言的に、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="00f11-173">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="00f11-174">指定する必要がありますには、少なくとも、 **InboundOperationType**と**NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="00f11-174">At a minimum, you must specify the **InboundOperationType** and **NotificationStatement** binding properties.</span></span>  
  
   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   binding.InboundOperationType = InboundOperation.Notification;  
   binding.NotificationStatement = "SELECT TID,ACCOUNT,PROCESSED FROM APPS.ACCOUNTACTIVITY WHERE PROCESSED = 'n'";  
   binding.NotifyOnListenerStart = true;  
   binding.NotificationPort = 10;  
   ```  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="00f11-175">値、 **NotificationPort**プロパティのバインドは、Windows ファイアウォールの例外リストに追加する必要があります、同じポート番号に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00f11-175">The value for the **NotificationPort** binding property must be set to the same port number that you must have added to the Windows Firewall exceptions list.</span></span> <span data-ttu-id="00f11-176">Windows ファイアウォールの例外リストにポートを追加する方法については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)します。</span><span class="sxs-lookup"><span data-stu-id="00f11-176">For instructions on how to add ports to Windows Firewall exceptions list, see [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959).</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="00f11-177">設定しない場合、 **NotificationPort**バインディング プロパティ、アダプターは、このバインドのプロパティの場合は-1 の既定値を想定しています。</span><span class="sxs-lookup"><span data-stu-id="00f11-177">If you do not set the **NotificationPort** binding property, the adapter will assume the default value of -1 for this binding property.</span></span> <span data-ttu-id="00f11-178">このような場合は、通知メッセージを受信する Windows ファイアウォールを完全に無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00f11-178">In such a case, you will have to completely disable Windows Firewall to receive notification messages.</span></span>  
  
6. <span data-ttu-id="00f11-179">Oracle E-business Suite の資格情報を指定するには、インスタンス化する、 **NotificationCredentials**手順 4. で作成したクラス。</span><span class="sxs-lookup"><span data-stu-id="00f11-179">Specify Oracle E-Business Suite credentials by instantiating the **NotificationCredentials** class you created in Step 4.</span></span>  
  
   ```  
   NotificationCredentials credentials = new NotificationCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  
  
7. <span data-ttu-id="00f11-180">手順 3 で作成した WCF サービスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="00f11-180">Create an instance of the WCF service created in step 3.</span></span>  
  
   ```  
   // create service instance  
   NotificationService service = new NotificationService();  
   ```  
  
8. <span data-ttu-id="00f11-181">インスタンスを作成**System.ServiceModel.ServiceHost** WCF サービスと基本の接続 URI を使用しています。</span><span class="sxs-lookup"><span data-stu-id="00f11-181">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="00f11-182">ここで、資格情報を指定することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="00f11-182">You must also specify the credentials here.</span></span>  
  
   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  
  
   ```  
  
9. <span data-ttu-id="00f11-183">サービス ホストにサービス エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="00f11-183">Add a service endpoint to the service host.</span></span> <span data-ttu-id="00f11-184">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="00f11-184">To do this:</span></span>  
  
   - <span data-ttu-id="00f11-185">手順 5. で作成したバインドを使用します。</span><span class="sxs-lookup"><span data-stu-id="00f11-185">Use the binding created in step 5.</span></span>  
  
   - <span data-ttu-id="00f11-186">接続の資格情報を含む URI を指定し、必要に応じて、受信の id。</span><span class="sxs-lookup"><span data-stu-id="00f11-186">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
   - <span data-ttu-id="00f11-187">"Notification_"としてコントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="00f11-187">Specify the contract as "Notification_".</span></span>  
  
     ```  
     // Add service endpoint: be sure to specify Notification_ as the contract  
     Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name?");  
     serviceHost.AddServiceEndpoint("Notification_", binding, ConnectionUri);  
     ```  
  
10. <span data-ttu-id="00f11-188">通知メッセージを受信するには、サービス ホストを開きます。</span><span class="sxs-lookup"><span data-stu-id="00f11-188">To receive notification message, open the service host.</span></span>  
  
    ```  
    // Open the service host to begin receiving notifications  
    serviceHost.Open();  
    ```  
  
11. <span data-ttu-id="00f11-189">通知の受信を停止するには、サービス ホストを閉じます。</span><span class="sxs-lookup"><span data-stu-id="00f11-189">To stop receiving notifications, close the service host.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="00f11-190">例</span><span class="sxs-lookup"><span data-stu-id="00f11-190">Example</span></span>  
 <span data-ttu-id="00f11-191">次の例では、ACCOUNTACTIVITY テーブル通知メッセージを受信する .NET アプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="00f11-191">The following example shows a .NET application to receive notification messages for the ACCOUNTACTIVITY table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00f11-192">次のコード スニペットをインスタンス化、 **TableOperation.cs**クラスを呼び出す、 **TableOp**メソッド。</span><span class="sxs-lookup"><span data-stu-id="00f11-192">The following code snippet instantiates a **TableOperation.cs** class and invokes the **TableOp** method.</span></span> <span data-ttu-id="00f11-193">クラスとメソッドについては、手順 1. で説明します。</span><span class="sxs-lookup"><span data-stu-id="00f11-193">The class and the method are described in Step 1.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
using Microsoft.Adapters.OracleEBS;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace Notification_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class NotificationService : OracleEBSBindingNamespace.OracleEBSBindingService  
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
  
                OracleEBSBinding binding = new OracleEBSBinding();  
                binding.InboundOperationType = InboundOperation.Notification;  
                binding.NotificationStatement = "SELECT TID,ACCOUNT,PROCESSED FROM APPS.ACCOUNTACTIVITY WHERE PROCESSED = 'n'";  
                binding.NotifyOnListenerStart = true;  
                binding.NotificationPort = 10;  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // an InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
  
                NotificationCredentials credentials = new NotificationCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                NotificationService service = new NotificationService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("Notification_", binding, ConnectionUri);  
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
  
## <a name="see-also"></a><span data-ttu-id="00f11-194">参照</span><span class="sxs-lookup"><span data-stu-id="00f11-194">See Also</span></span>  
 [<span data-ttu-id="00f11-195">WCF サービス モデルを使用して Oracle E-business Suite のアプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="00f11-195">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)