---
title: "WCF サービス モデルを使用して Oracle データベース内の大規模なデータ型とテーブルに対する操作を完了 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, performing operations on tables and views
- how to, invoke the ReadLOB and UpdateLOB operations
ms.assetid: 5d0e84d3-7ffa-47c7-aaf2-a1007f7a71a2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88ae5a616e71e27a4d6fa8cd27473665f7bc96b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="complete-operations-on-tables-with-large-data-types-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="afc47-102">WCF サービス モデルを使用して Oracle データベース内の大規模なデータ型とテーブルに対する操作を完了します。</span><span class="sxs-lookup"><span data-stu-id="afc47-102">Complete operations on tables with large data types in Oracle Database using the WCF service model</span></span>
<span data-ttu-id="afc47-103">このセクションには、WCF サービス モデルから ReadLOB および UpdateLOB 操作を呼び出す方法に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="afc47-103">This section contains information about how to invoke the ReadLOB and UpdateLOB operations from the WCF service model.</span></span> <span data-ttu-id="afc47-104">テーブルおよび; LOB 列を含むビューの ReadLOB および UpdateLOB 操作が表示されます。Oracle ラージ オブジェクト (LOB) データの格納に使用される列です。</span><span class="sxs-lookup"><span data-stu-id="afc47-104">The ReadLOB and UpdateLOB operations are surfaced for tables and views that contain LOB columns; that is columns that are used to store Oracle large object (LOB) data.</span></span> <span data-ttu-id="afc47-105">サポートされる Oracle LOB データ型の概要については、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] 、ReadLOB や UpdateLOB 操作の参照と[テーブルおよびビューを含む LOB データをする Oracle データベースで操作を](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="afc47-105">For an overview of the Oracle LOB data types supported by the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] and of the ReadLOB and UpdateLOB operations, see [Operations on Tables and Views That Contain LOB Data in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="afc47-106">LOB データの列は、大量のデータを含めることができます: 最大 4 ギガバイト (GB)。</span><span class="sxs-lookup"><span data-stu-id="afc47-106">LOB data columns can contain large amounts of data—up to 4 gigabytes (GB).</span></span> <span data-ttu-id="afc47-107">WCF クライアントを使用して、LOB 列を操作する際の重要な制限は、WCF サービス モデルではストリーミング UpdateLOB 操作ではなく、ReadLOB 操作にデータのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="afc47-107">A significant limitation of using a WCF client to operate on LOB columns is that the WCF service model only supports data streaming on the ReadLOB operation, not on the UpdateLOB operation.</span></span> <span data-ttu-id="afc47-108">これは、WCF では、ストリーミング サービス モデルから作業する、パラメーターのストリーミングをいる必要がありますその方向に唯一のパラメーターが必要なためです。</span><span class="sxs-lookup"><span data-stu-id="afc47-108">This is because WCF requires that for streaming to work from service model, the parameter to be streamed must be the only parameter in its direction.</span></span> <span data-ttu-id="afc47-109">UpdateLOB 操作 2 つの他の内のパラメーターを持ち (列名と行フィルター) LOB データだけでなくこのため、ストリーミングがサポートされていませんに WCF サービス モデルで。</span><span class="sxs-lookup"><span data-stu-id="afc47-109">The UpdateLOB operation has two other IN parameters (a column name and row filter) in addition to the LOB data; for this reason, streaming is not supported on it in the WCF service model.</span></span> <span data-ttu-id="afc47-110">そのため、大量のデータと、LOB 列を更新する可能性がある場合は、WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="afc47-110">Therefore, if you are updating a LOB column with a large amount of data, you might want to use the WCF channel model.</span></span> <span data-ttu-id="afc47-111">WCF チャネル モデルを使用して、LOB を UpdateLOB 操作を使用してデータをストリームする方法の詳細については、次を参照してください。[ストリーミング Oracle LOB データ型 WCF チャネル モデルを使用して](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="afc47-111">For more information on how to use the WCF channel model to stream LOB data using the UpdateLOB operation, see [Streaming Oracle LOB Data Types by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="afc47-112">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="afc47-112">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="afc47-113">このトピックの例では、/SCOTT/CUSTOMER テーブルを使用します。</span><span class="sxs-lookup"><span data-stu-id="afc47-113">The examples in this topic use the /SCOTT/CUSTOMER table.</span></span> <span data-ttu-id="afc47-114">このテーブルには、写真をという名前の BLOB 列が含まれています。このテーブルを生成するスクリプトは、SDK サンプルの値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="afc47-114">This table contains a BLOB column named PHOTO.A script to generate this table is supplied with the SDK samples.</span></span> <span data-ttu-id="afc47-115">SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)です。</span><span class="sxs-lookup"><span data-stu-id="afc47-115">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="afc47-116">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="afc47-116">The WCF Client Class</span></span>  
 <span data-ttu-id="afc47-117">次の例では、/SCOTT/CUSTOMER テーブルでは、ReadLOB と UpdateLOB 操作に対して生成される WCF クライアント クラスのメソッドのシグニチャを示します。</span><span class="sxs-lookup"><span data-stu-id="afc47-117">The following example shows the method signatures for a WCF client class generated for the ReadLOB and UpdateLOB operations on the /SCOTT/CUSTOMER table.</span></span>  
  
```  
public partial class SCOTTTableCUSTOMERClient : System.ServiceModel.ClientBase<SCOTTTableCUSTOMER>,   
                                                SCOTTTableCUSTOMER   
{  
    public System.IO.Stream ReadLOB(string LOB_COLUMN, string FILTER);   
  
    public void UpdateLOB(string LOB_COLUMN, string FILTER, byte[] Stream);  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="afc47-118">なお**ReadLOB**されることが、データ ストリームを返します**UpdateLOB**ストリームでは動作しません。</span><span class="sxs-lookup"><span data-stu-id="afc47-118">Note that **ReadLOB** returns a data stream, but that **UpdateLOB** does not operate on a stream.</span></span>  
  
## <a name="invoking-the-readlob-and-updatelob-operations"></a><span data-ttu-id="afc47-119">ReadLOB と UpdateLOB 操作の呼び出し</span><span class="sxs-lookup"><span data-stu-id="afc47-119">Invoking the ReadLOB and UpdateLOB Operations</span></span>  
 <span data-ttu-id="afc47-120">両方の**ReadLOB**と**UpdateLOB**メソッドは、1 つのデータベースの行に 1 つの LOB 列でのみ操作できます。</span><span class="sxs-lookup"><span data-stu-id="afc47-120">Both the **ReadLOB** and **UpdateLOB** methods can operate only on a single LOB column in a single database row.</span></span> <span data-ttu-id="afc47-121">ターゲット列/列を識別する、次のパラメーターを設定するとします。</span><span class="sxs-lookup"><span data-stu-id="afc47-121">You set the following parameters to identify the target column/row.</span></span>  
  
|<span data-ttu-id="afc47-122">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afc47-122">Parameter</span></span>|<span data-ttu-id="afc47-123">定義</span><span class="sxs-lookup"><span data-stu-id="afc47-123">Definition</span></span>|  
|---------------|----------------|  
|<span data-ttu-id="afc47-124">LOB_COLUMN</span><span class="sxs-lookup"><span data-stu-id="afc47-124">LOB_COLUMN</span></span>|<span data-ttu-id="afc47-125">フィルター パラメーターで識別される行でのターゲット列の名前たとえば、「写真」とします。</span><span class="sxs-lookup"><span data-stu-id="afc47-125">The name of the target column within the row identified by the FILTER parameter; for example, "PHOTO".</span></span>|  
|<span data-ttu-id="afc47-126">FILTER</span><span class="sxs-lookup"><span data-stu-id="afc47-126">FILTER</span></span>|<span data-ttu-id="afc47-127">SQL SELECT ステートメントです。 対象の行を指定する WHERE 句の内容たとえば、"名前 ='Kim Ralls'"です。</span><span class="sxs-lookup"><span data-stu-id="afc47-127">The contents of a SQL SELECT statement WHERE clause that specifies the target row; for example, "NAME='Kim Ralls'".</span></span> <span data-ttu-id="afc47-128">フィルターは、1 つだけの行を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afc47-128">The filter must specify one and only one row.</span></span> <span data-ttu-id="afc47-129">場合は、フィルターでは、複数の行と一致します。</span><span class="sxs-lookup"><span data-stu-id="afc47-129">If the filter matches more than one row:</span></span><br /><br /> <span data-ttu-id="afc47-130">-   **ReadLOB**最初の一致する行の LOB データを返します。</span><span class="sxs-lookup"><span data-stu-id="afc47-130">-   **ReadLOB** returns LOB data for the first matching row.</span></span><br /><span data-ttu-id="afc47-131">-   **UpdateLOB**例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="afc47-131">-   **UpdateLOB** throws an exception.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="afc47-132">によって返されるストリーム**ReadLOB**はサポートしていません**シーク**です。</span><span class="sxs-lookup"><span data-stu-id="afc47-132">The stream returned by **ReadLOB** does not support **Seek**.</span></span> <span data-ttu-id="afc47-133">つまりなどのプロパティ**長さ**はサポートされていませんか。</span><span class="sxs-lookup"><span data-stu-id="afc47-133">This means that properties such as **Length** are not supported, either.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="afc47-134">**UpdateLOB**トランザクション スコープ内で操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afc47-134">The **UpdateLOB** operation must be performed within a transaction scope.</span></span> <span data-ttu-id="afc47-135">また、 **UseAmbientTransaction** binding プロパティを設定する必要があります**true**実行する前に、 **UpdateLOB**操作します。</span><span class="sxs-lookup"><span data-stu-id="afc47-135">Also, the **UseAmbientTransaction** binding property must be set to **true** before performing the **UpdateLOB** operation.</span></span>  
  
 <span data-ttu-id="afc47-136">次のコードでは、WCF クライアントを使用してファイルから/SCOTT/CUSTOMER テーブル内の BLOB フォト列を更新し、ファイルに新しい列のデータを読み取る方法を示します。</span><span class="sxs-lookup"><span data-stu-id="afc47-136">The following code shows how to use a WCF client to update the BLOB PHOTO column in the /SCOTT/CUSTOMER table from a file and read the new column data back to a file.</span></span> <span data-ttu-id="afc47-137">SDK のサンプルでは、完全なサンプルを参照できます。</span><span class="sxs-lookup"><span data-stu-id="afc47-137">You can find a full sample in the SDK samples.</span></span> <span data-ttu-id="afc47-138">SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)です。</span><span class="sxs-lookup"><span data-stu-id="afc47-138">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Transaction;  
  
// Include for file streaming  
using System.IO;  
  
// Add WCF, WCF LOB Adapter SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for the WCF channel model  
using System.ServiceModel.Channels;  
  
// Include this namespace for the WCF LOB Adapter SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
using CustomerTablens = microsoft.lobservices.oracledb._2007._03;  
  
namespace OracleLobOpsSnippetSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            try  
            {  
                OracleDBBinding binding = new OracleDBBinding();  
                binding.UseAmbientTransaction = true; //set this to true for UpdateLOB operation  
  
                EndpointAddress endpointAddress = new EndpointAddress("oracleDB://ADAPTER");  
  
                using (SCOTTTableCUSTOMERClient customerTableClient =  
                    new SCOTTTableCUSTOMERClient(binding, endpointAddress))  
                {  
                    customerTableClient.ClientCredentials.UserName.UserName = "SCOTT";  
                    customerTableClient.ClientCredentials.UserName.Password = "TIGER";  
  
                    // Open the client to read the LOB data back  
                    customerTableClient.Open();  
  
                    // Add a photo to the customer record    
                    using (FileStream fs = new FileStream("SamplePhoto.jpg", FileMode.Open))  
                    {  
                        Console.WriteLine("Updating photo");  
                        int count = 0;  
                        byte[] photo = new byte[fs.Length];  
                        while ((count += fs.Read(photo, count, (int) (((fs.Length-count)>4096)? 4096:fs.Length-count))) \< fs.Length) ;  
  
                        // UpdateLOB operation must be performed within a transaction scope  
                        using(TransactionScope tx = new TransactionScope())  
                        {  
                           customerTableClient.UpdateLOB("PHOTO", "NAME='Kim Ralls'", photo);  
                           Console.WriteLine("Photo updated");  
                           tx.Complete();  
                        }  
                    }  
  
                    // Read the data back and store it to another file  
                    using (FileStream fs = new FileStream("PhotoCopy.jpg", FileMode.Create))  
                    {  
                        Console.WriteLine("Reading photo data");  
                        Stream photoStream = customerTableClient.ReadLOB("PHOTO", "NAME='Kim Ralls'");  
                        Console.WriteLine("Photo data read -- writing to PhotoCopy.jpg");  
  
                        int count;  
                        int length = 0;  
                        byte[] buffer = new byte[4096];  
                        while ((count = photoStream.Read(buffer, 0, 4096)) > 0)  
                        {  
                            fs.Write(buffer, 0, count);  
                            length+=count;  
                        }  
                        Console.WriteLine("{0} bytes written to PhotoCopy.jpg", length);  
                    }  
  
                }  
  
                Console.WriteLine("Photo updated and read back -- Hit <RETURN> to end");  
                Console.ReadLine();  
  
            }  
            catch (Exception ex)  
            {  
                // handle exception  
                Console.WriteLine("Exception caught: " + ex.Message);  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="afc47-139">参照</span><span class="sxs-lookup"><span data-stu-id="afc47-139">See Also</span></span>  
 [<span data-ttu-id="afc47-140">WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="afc47-140">Develop Oracle Database Applications Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)