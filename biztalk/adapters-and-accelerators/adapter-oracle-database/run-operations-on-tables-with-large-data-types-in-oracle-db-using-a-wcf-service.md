---
title: WCF サービス モデルを使用して Oracle データベース内の大規模なデータ型とテーブルに対する操作を完了 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, performing operations on tables and views
- how to, invoke the ReadLOB and UpdateLOB operations
ms.assetid: 5d0e84d3-7ffa-47c7-aaf2-a1007f7a71a2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88ae5a616e71e27a4d6fa8cd27473665f7bc96b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215610"
---
# <a name="complete-operations-on-tables-with-large-data-types-in-oracle-database-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle データベース内の大規模なデータ型とテーブルに対する操作を完了します。
このセクションには、WCF サービス モデルから ReadLOB および UpdateLOB 操作を呼び出す方法に関する情報が含まれています。 テーブルおよび; LOB 列を含むビューの ReadLOB および UpdateLOB 操作が表示されます。Oracle ラージ オブジェクト (LOB) データの格納に使用される列です。 サポートされる Oracle LOB データ型の概要については、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] 、ReadLOB や UpdateLOB 操作の参照と[テーブルおよびビューを含む LOB データをする Oracle データベースで操作を](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)です。  
  
> [!IMPORTANT]
>  LOB データの列は、大量のデータを含めることができます: 最大 4 ギガバイト (GB)。 WCF クライアントを使用して、LOB 列を操作する際の重要な制限は、WCF サービス モデルではストリーミング UpdateLOB 操作ではなく、ReadLOB 操作にデータのみをサポートします。 これは、WCF では、ストリーミング サービス モデルから作業する、パラメーターのストリーミングをいる必要がありますその方向に唯一のパラメーターが必要なためです。 UpdateLOB 操作 2 つの他の内のパラメーターを持ち (列名と行フィルター) LOB データだけでなくこのため、ストリーミングがサポートされていませんに WCF サービス モデルで。 そのため、大量のデータと、LOB 列を更新する可能性がある場合は、WCF チャネル モデルを使用します。 WCF チャネル モデルを使用して、LOB を UpdateLOB 操作を使用してデータをストリームする方法の詳細については、次を参照してください。[ストリーミング Oracle LOB データ型 WCF チャネル モデルを使用して](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)です。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、/SCOTT/CUSTOMER テーブルを使用します。 このテーブルには、写真をという名前の BLOB 列が含まれています。このテーブルを生成するスクリプトは、SDK サンプルの値が提供されます。 SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)です。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 次の例では、/SCOTT/CUSTOMER テーブルでは、ReadLOB と UpdateLOB 操作に対して生成される WCF クライアント クラスのメソッドのシグニチャを示します。  
  
```  
public partial class SCOTTTableCUSTOMERClient : System.ServiceModel.ClientBase<SCOTTTableCUSTOMER>,   
                                                SCOTTTableCUSTOMER   
{  
    public System.IO.Stream ReadLOB(string LOB_COLUMN, string FILTER);   
  
    public void UpdateLOB(string LOB_COLUMN, string FILTER, byte[] Stream);  
}  
```  
  
> [!NOTE]
>  なお**ReadLOB**されることが、データ ストリームを返します**UpdateLOB**ストリームでは動作しません。  
  
## <a name="invoking-the-readlob-and-updatelob-operations"></a>ReadLOB と UpdateLOB 操作の呼び出し  
 両方の**ReadLOB**と**UpdateLOB**メソッドは、1 つのデータベースの行に 1 つの LOB 列でのみ操作できます。 ターゲット列/列を識別する、次のパラメーターを設定するとします。  
  
|パラメーター|定義|  
|---------------|----------------|  
|LOB_COLUMN|フィルター パラメーターで識別される行でのターゲット列の名前たとえば、「写真」とします。|  
|FILTER|SQL SELECT ステートメントです。 対象の行を指定する WHERE 句の内容たとえば、"名前 ='Kim Ralls'"です。 フィルターは、1 つだけの行を指定する必要があります。 場合は、フィルターでは、複数の行と一致します。<br /><br /> -   **ReadLOB**最初の一致する行の LOB データを返します。<br />-   **UpdateLOB**例外をスローします。|  
  
> [!NOTE]
>  によって返されるストリーム**ReadLOB**はサポートしていません**シーク**です。 つまりなどのプロパティ**長さ**はサポートされていませんか。  
  
> [!CAUTION]
>  **UpdateLOB**トランザクション スコープ内で操作を実行する必要があります。 また、 **UseAmbientTransaction** binding プロパティを設定する必要があります**true**実行する前に、 **UpdateLOB**操作します。  
  
 次のコードでは、WCF クライアントを使用してファイルから/SCOTT/CUSTOMER テーブル内の BLOB フォト列を更新し、ファイルに新しい列のデータを読み取る方法を示します。 SDK のサンプルでは、完全なサンプルを参照できます。 SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)です。  
  
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
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)