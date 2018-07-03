---
title: EXECQUERY コマンドを使用して SAP クエリの実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 520153bf-9477-4b35-8953-3f5cb444ab9f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f250befed19f285baefc1c192f25b335701fa6ca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972163"
---
# <a name="execute-an-sap-query-using-the-execquery-command"></a>EXECQUERY コマンドを使用して SAP クエリを実行します。
[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ADO.NET データ ソースとしての SAP システムを公開します。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]、EXECQUERY ステートメントを実行する SAP システムで事前定義されたクエリを実行することができます。  
  
## <a name="how-to-perform-a-query-by-using-the-execquery-command"></a>EXECQUERY コマンドを使用して、クエリを実行する方法  
 定義済みの SAP を実行するクエリを使用して、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]、次の手順に従います。  
  
#### <a name="to-perform-a-query"></a>クエリを実行するには  
  
1. 参照を含める (と、コードでステートメントを使用) に**Microsoft.Data.SAPClient**します。  
  
2. 作成、 **SAPConnection** SAP 接続文字列のデータ プロバイダーを使用してオブジェクト。 接続文字列の詳細については、次を参照してください。 [SAP 接続文字列のデータ プロバイダーの種類について](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)します。  
  
3. 呼び出すことによって、SAP システムへの接続を開く**オープン**上、 **SAPConnection**します。  
  
4. 作成、 **SAPCommand**オブジェクトから、 **SAPConnection**します。  
  
5. EXECQUERY ステートメントの指定、 **CommandText**のプロパティ、 **SAPCommand**します。 かどうか、必要に応じてパラメーターを指定できますを使用して**SAPParameter**オブジェクト。 EXECQUERY ステートメントを使用する SAP システムで定義されているクエリを実行する方法の詳細については、次を参照してください。 [sap EXECQUERY ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md)します。  
  
6. クエリを実行しで結果を取得するコマンドを実行する**SAPDataReader**します。  
  
7. 結果を読み取り、 **SAPDataReader**します。  
  
8. それらの使用が終了したら、閉じる (または dispose)、 **SAPConnection**と**SAPDataReader**します。  
  
   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]も公開、 **SAPClientFactory**クラスで、作成に使用できる**SAPConnection**、 **SAPCommand**と**SAPConnection**オブジェクト。 拡張によって、ADO.NET のクラスの詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP アダプターを使用した ADO.NET インターフェイスの拡張](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)します。  
  
## <a name="example"></a>例  
 次の例は、ZTEST1、クエリの結果をコンソールに書き込みます。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using Microsoft.Data.SAPClient;  
  
namespace SapAdoExecQuery  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
           string connstr = "TYPE=A; ASHOST=YourSapHost; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;";  
           using (SAPConnection conn = new SAPConnection(connstr))  
            {  
                conn.Open();  
                using (SAPCommand cmd = conn.CreateCommand())  
                {  
                    cmd.CommandText = "EXECQUERY ZTEST1 @userGRoup='SYSTQV000024',@P1='0000001390',@P2='0000080150'";  
                    cmd.Parameters.Add(new SAPParameter("@connid", 17));                      
                    using (SAPDataReader dr = cmd.ExecuteReader())  
                    {  
                        do  
                        {  
                            int rows = 0;  
                            while (dr.Read())  
                            {  
                                rows++;  
                                StringBuilder b = new StringBuilder();  
                                for (int i = 0; i < dr.FieldCount; i++)  
                                {  
                                    b.Append(dr[i].ToString()+" ");  
                                }  
                                Console.WriteLine("row {0}: {1} ", rows, b.ToString());  
                            }  
                            Console.WriteLine("Number of rows:{0}", rows);  
                        } while (dr.NextResult());  
                    }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite の使用](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)  
 [サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)