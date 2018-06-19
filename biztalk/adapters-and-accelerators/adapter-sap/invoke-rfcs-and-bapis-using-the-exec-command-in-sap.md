---
title: 呼び出しの Rfc および Bapi の SAP で EXEC コマンドの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EXEC command, invoking RFCs and BAPIs
- BAPIs and RFCs, invoking by using the EXEC command
- RFCs and BAPIs, invoking by using the EXEC command
ms.assetid: 55443679-2fa8-4c13-ac3b-1c85b5166cd2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 500e0f932a8245f76954aa7a8785dbec012321e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217218"
---
# <a name="invoke-rfcs-and-bapis-using-the-exec-command-in-sap"></a>呼び出しの Rfc および Bapi の SAP で EXEC コマンドの使用
[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ADO.NET データ ソースとしての SAP システムを公開します。 使用して[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]、EXEC コマンドで、SAP システムの Rfc および Bapi を呼び出すことができます。  
  
## <a name="how-to-invoke-rfcs-and-bapis-on-the-sap-system"></a>SAP システムで呼び出す Rfc および Bapi する方法  
 RFC または BAPI を使用してを呼び出す、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]、次の手順を実行します。  
  
#### <a name="to-invoke-an-rfc-or-bapi"></a>RFC または BAPI を呼び出す  
  
1.  参照を含める (および、コードでステートメントを使用) する**Microsoft.Data.SAPClient**です。  
  
2.  作成、 **SAPConnection** SAP 接続文字列のデータ プロバイダーを使用するオブジェクト。 接続文字列の詳細については、次を参照してください。 [SAP 接続文字列のデータ プロバイダーの種類の説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)です。  
  
3.  呼び出すことによって、SAP システムへの接続を開く**開く**上、 **SAPConnection**です。  
  
4.  作成、 **SAPCommand**オブジェクトから、 **SAPConnection**です。  
  
5.  BAPI または RFC 呼び出しを指定、 **CommandText**のプロパティ、 **SAPCommand**です。 かどうか、必要に応じてパラメーターを指定できますを使用して**SAPParameter**オブジェクト。 EXEC ステートメントを使用して BAPI または RFC 呼び出しを指定する方法の詳細については、次を参照してください。 [SAP の EXEC ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md)です。 RFC または BAPI を指定する方法の例については、次を参照してください。 [EXEC ステートメントの例](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md)です。  
  
6.  RFC または BAPI を呼び出すしで結果を取得するコマンドを実行、 **SAPDataReader**です。  
  
7.  結果を参照してから、 **SAPDataReader**です。  
  
8.  それらの使用が終了したら、終了 (または破棄)、 **SAPConnection**と**SAPDataReader**です。  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]も公開、 **SAPClientFactory**クラスは、作成に使用できる**SAPConnection**、 **SAPCommand**と**SAPConnection**オブジェクト。 によって拡張された ADO.NET クラスの詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP アダプターを持つ ADO.NET インターフェイスを拡張](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)です。  
  
## <a name="example"></a>例  
 次の例では、"AB"で始まる名前のすべての顧客の顧客情報を取得する SD_RFC_CUSTOMER_GET を呼び出します。 顧客レコードをコンソールに書き込みます。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using Microsoft.Data.SAPClient;  
  
namespace SapAdoExec  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string connstr = "TYPE=A; ASHOST=YourSAPHost; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;";  
  
            using (SAPConnection conn = new SAPConnection(connstr))  
            {  
                conn.Open();  
  
                using (SAPCommand cmd = conn.CreateCommand())  
                {  
                    cmd.CommandText = "exec sd_rfc_customer_get @name1='AB*' ";  
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
                                    b.Append(dr[i].ToString() + " ");  
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
 [使用して、.NET Framework Data Provider 用 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)   
 [サンプル](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)