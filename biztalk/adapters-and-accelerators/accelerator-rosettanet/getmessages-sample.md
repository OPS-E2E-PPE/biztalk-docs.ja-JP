---
title: GetMessages サンプル |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29e575fa-d68b-4975-84b8-da4f17bd2db3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2ebc4ce5b87a0b698f0295fdf29c8f7138efed7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210738"
---
# <a name="getmessages-sample"></a>GetMessages サンプル
ここでは、メッセージ否認不可テーブルまたは基幹業務 (LOB) テーブルから、ユーザーが理解できる形式でメッセージを取得するためのサンプル コードについて説明します。 メッセージ否認不可テーブルには、[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]Archive データベースの MessageStorageIn および MessageStorageOut が含まれます。LOB テーブルには、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA データベースの MessageFromLOB および MessageToLOB が含まれます。  
  
 トラブルシューティングや展開には、`GetMessages` を使用します。 既定では、コードは Base 64 文字列を返します。  
  
> [!NOTE]
>  GetMessages.cs サンプル コードには、2 つのコード セクションが含まれています。1 つのセクションは LOB テーブルからメッセージを取得するためのもので、もう 1 つは否認不可テーブルからメッセージを取得するためのものです。 目的ごとに個別のアプリケーションを作成します。  
  
### <a name="to-retrieve-messages-from-an-lob-table"></a>LOB テーブルからメッセージを取得するには  
  
1.  次のサンプル コードをプログラムに追加します。  
  
     `private static string GetLOBMessage(string sMessageSource, string sMessageID)`  
  
2.  `sMessageSource` パラメーターを MessagesFromLOB テーブル、MessagesToLOB テーブルのいずれかに設定します。  
  
3.  設定、`sMessageID`パラメーターの値を**MessageID**フィールド、データベースにします。  
  
    > [!NOTE]
    >  アプリケーションでは、取得したメッセージを表す文字列を返します。  
  
### <a name="to-retrieve-messages-from-a-non-repudiation-table"></a>否認不可テーブルからメッセージを取得するには  
  
1.  次のサンプル コードをプログラムに追加します。  
  
     `private static string GetNRMessage(string sMessageSource, string sMessageID)`  
  
2.  `sMessageSource` パラメーターを MessageStorageIn テーブル、MessageStorageOut テーブルのいずれかに設定します。  
  
3.  設定、`sMessageID`パラメーターの値を**RecordID**フィールド、データベースにします。  
  
    > [!NOTE]
    >  アプリケーションでは、取得したメッセージを表す文字列を返します。  
  
## <a name="demonstrates"></a>使用例  
 GetMessages サンプルには、次の 2 つのコード セクションが含まれます。  
  
-   1 つのセクションは、否認不可テーブルからバイナリ メッセージを取得して、ユーザーが理解できる ASCII 形式に変換する方法を示します。  
  
-   もう 1 つのセクションは、LOB テーブルからメッセージを取得する方法を示します。 LOB テーブルのメッセージは既に ASCII 形式なので、これは SQL SELECT ステートメントです。  
  
    > [!IMPORTANT]
    >  説明の目的で、このサンプル コードは、SQL インジェクションの脆弱性の可能性がある直接 SQL ステートメントを使用します。 このような脆弱性を排除するために、運用環境では、直接 SQL ステートメントではなく、パラメーター化された SQL ストアド プロシージャを使用することをお勧めします。  
  
## <a name="example"></a>例  
 1 つの否認不可テーブルまたは LOB テーブルのいずれかからメッセージを取得するためには、次のコード例では、2 つのセクションのいずれかを使用します。  
  
```  
using System;  
using System.Text;  
using System.Data.SqlClient;   
using Microsoft.Solutions.BTARN.Shared;  
  
namespace Microsoft.Solutions.BTARN.Admin  
{  
  
      /// <summary>  
      /// Summary description for GetMessages.  
      /// </summary>  
      class GetMessages  
      {  
            /// <summary>  
            /// The main entry point for the application.  
            /// </summary>  
            [STAThread]  
            static void Main(string[] args)  
            {  
                  Console.WriteLine(GetLOBMessage("MessagesFromLOB", "bce5b580daf543a990a4f37331f31e42"));  
                  Console.WriteLine(GetLOBMessage("MessagesToLOB", "bce5b580daf543a990a4f37331f31e42"));  
                  Console.WriteLine(GetNRMessage("MessageStorageIn", "dc06e9cfecd746a889dd6ea7beb3ba21"));  
                  Console.WriteLine(GetNRMessage("MessageStorageOut", "dc06e9cfecd746a889dd6ea7beb3ba21"));  
            }  
  
            /// <summary>  
            /// Retrieve a message from the LOB tables in the BTARNDATA database  
            /// </summary>  
            /// <param name="sMessageSource">Can be either MessagesFromLOB or MessagesToLOB</param>  
            /// <param name="sMessageID">The value of the MessageID field in the database</param>  
            /// <returns>Returns a string that contains the retrieved message</returns>        
            private static string GetLOBMessage(string sMessageSource, string sMessageID)  
            {  
                  SqlDataReader localReader = null;  
                  SqlConnection sqlConnection = null;  
                  SqlCommand sqlCommand = null;  
                  string sReturnedMessage="";              
                  string sQuery;  
  
                  sqlConnection = new SqlConnection(RuntimeGlobal.DataDbConnectionString);  
                  sQuery = "SELECT ServiceContent from " + sMessageSource + " WHERE MessageID=N'" + sMessageID +"'";  
  
                  sqlCommand = new SqlCommand(sQuery, sqlConnection);  
                  sqlConnection.Open();  
  
                  localReader = sqlCommand.ExecuteReader();  
  
                  if (localReader.Read())  
                        sReturnedMessage=localReader.GetString(0);  
  
                  localReader.Close();  
                  sqlConnection.Close();        
                  return sReturnedMessage;              
            }  
  
            /// <summary>  
            /// Retrieve a message from the non-repudiation tables in the BTARNArchive database  
            /// </summary>  
            /// <param name="sMessageSource">Can be either MessageStorageIn or MessageStorageOut</param>  
            /// <param name="sMessageID">The value of the RecordID field in the database</param>  
            /// <returns>Returns a string that contains the retrieved message</returns>  
            private static string GetNRMessage(string sMessageSource, string sMessageID)  
            {  
                  SqlDataReader localReader = null;  
                  SqlConnection sqlConnection = null;  
                  SqlCommand sqlCommand = null;  
                  string sReturnedMessage="";              
                  string sQuery;  
  
                  sqlConnection = new SqlConnection(RuntimeGlobal.ArchiveDbConnectionString);  
                  sQuery = "SELECT Content from " + sMessageSource + " WHERE RecordID=N'" + sMessageID +"'";  
  
                  sqlCommand = new SqlCommand(sQuery, sqlConnection);  
                  sqlConnection.Open();  
  
                  localReader = sqlCommand.ExecuteReader();  
  
                  if (localReader.Read())  
                  {  
                        //Determine the size of the field in bytes and create a new byte array  
                        byte[] bData= new byte[localReader.GetBytes(0, 0, null, 0, 0)];  
  
                        //Read the value of the field into bData  
                        localReader.GetBytes(0, 0, bData, 0, bData.Length);  
  
                        //Convert the byte array into a string  
                        sReturnedMessage=Encoding.ASCII.GetString(bData);  
                  }  
  
                  localReader.Close();  
                  sqlConnection.Close();        
                  return sReturnedMessage;              
            }  
      }  
}  
```  
  
## <a name="see-also"></a>参照  
 [メッセージング サンプル](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)