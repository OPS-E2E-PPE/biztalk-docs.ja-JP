---
title: WCF サービス モデルを使用して Oracle データベースでの大規模なデータ型を持つテーブルに対する操作の完了 |Microsoft Docs
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
ms.openlocfilehash: 7af4542dae7dc2370058dfc715d455ec571f776e
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528929"
---
# <a name="complete-operations-on-tables-with-large-data-types-in-oracle-database-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle データベースでの大規模なデータ型を持つテーブルに対する操作を完了します。
このセクションには、WCF サービス モデルから ReadLOB および UpdateLOB の操作を呼び出す方法に関する情報が含まれています。 テーブルとビューは LOB 列が含まれているため、ReadLOB および UpdateLOB 操作が表示されます。Oracle のラージ オブジェクト (LOB) データの格納に使用される列です。 サポートされる Oracle LOB データ型の概要については、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] ReadLOB と UpdateLOB 操作の表示と[テーブルとビューを含む LOB データを Oracle データベース内で操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)します。  
  
> [!IMPORTANT]
>  LOB データの列は、大量のデータを含めることができます: 最大 4 ギガバイト (GB)。 WCF クライアントを使用して、LOB 列を操作する重大な制限事項は、WCF サービス モデルではストリーミング UpdateLOB 操作ではなく、ReadLOB 操作でのデータのみをサポートします。 これは、WCF では、サービス モデルを使用するストリーミング、ストリーミングされるようにパラメーター必要があること、方向で唯一のパラメーターが必要なためにです。 UpdateLOB 操作が 2 つの IN パラメーター (列名、行フィルター) は、LOB データだけでなくこのため、ストリーミングはサポートされませんが、WCF サービス モデル。 そのため、大量のデータの LOB 列を更新する場合は、WCF チャネル モデルを使用する可能性があります。 WCF チャネル モデルを使用して、UpdateLOB 操作を使用して LOB データをストリームする方法の詳細については、次を参照してください。[ストリーミング Oracle LOB データ型、WCF チャネル モデルを使用して](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)します。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、/SCOTT/CUSTOMER テーブルを使用します。 このテーブルには、写真をという名前の BLOB 列が含まれています。このテーブルを生成するスクリプトは SDK のサンプルで提供されます。 SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)します。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 次の例では、/SCOTT/CUSTOMER テーブルに対する ReadLOB と UpdateLOB 操作に対して生成された WCF クライアント クラスのメソッド シグネチャを示します。  
  
```  
public partial class SCOTTTableCUSTOMERClient : System.ServiceModel.ClientBase<SCOTTTableCUSTOMER>,   
                                                SCOTTTableCUSTOMER   
{  
    public System.IO.Stream ReadLOB(string LOB_COLUMN, string FILTER);   
  
    public void UpdateLOB(string LOB_COLUMN, string FILTER, byte[] Stream);  
}  
```  
  
> [!NOTE]
>  なお**ReadLOB**が、データ ストリームを返します**UpdateLOB**ストリームについては動作しません。  
  
## <a name="invoking-the-readlob-and-updatelob-operations"></a>ReadLOB と UpdateLOB 操作を呼び出す  
 両方の**ReadLOB**と**UpdateLOB**メソッドは、1 つのデータベースの行に 1 つの LOB 列でのみ操作できます。 ターゲット列や行を識別するために、次のパラメーターを設定するとします。  
  
|パラメーター|定義|  
|---------------|----------------|  
|LOB_COLUMN|フィルター パラメーターで識別される行でのターゲット列の名前たとえば、「PHOTO」とします。|  
|FILTER|SQL SELECT ステートメントは、対象の行を指定する WHERE 句の内容たとえば、"名前 ='Kim 取り外さないこと '"です。 フィルターは、1 つだけの行を指定する必要があります。 場合は、フィルターでは、1 つ以上の行と一致します。<br /><br /> -   **ReadLOB**最初の一致する行の LOB データを返します。<br />-   **UpdateLOB**例外をスローします。|  
  
> [!NOTE]
>  によって返されるストリーム**ReadLOB**はサポートしていません**シーク**します。 つまりなどのプロパティ**長さ**はサポートされていませんか。  
  
> [!CAUTION]
>  **UpdateLOB**トランザクション スコープ内で操作を実行する必要があります。 また、 **UseAmbientTransaction**に設定するプロパティをバインドする必要があります**true**実行する前に、 **UpdateLOB**操作。  
  
 次のコードでは、WCF クライアントを使用して BLOB の写真ファイルから/SCOTT/CUSTOMER テーブル列を更新し、ファイルに新しい列データを読み取る方法を示します。 SDK のサンプルでは、完全なサンプルが見つかります。 SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)します。  
  
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