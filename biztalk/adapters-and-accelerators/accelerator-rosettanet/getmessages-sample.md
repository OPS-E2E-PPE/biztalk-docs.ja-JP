---
title: GetMessages サンプル |Microsoft Docs
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
ms.openlocfilehash: cb1c30fa6b90ba0e9e523a54b24030dd32b8ff80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283662"
---
# <a name="getmessages-sample"></a>GetMessages サンプル
このトピックでは、メッセージの否認不可テーブルの 1 つまたは判読できる形式で基幹業務 (LOB) テーブルのいずれかからメッセージを取得するのに使用できるサンプル コードを提供します。 メッセージの否認不可テーブルには、MessageStorageIn および MessageStorageOut が含まれます。、[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]アーカイブ データベースは、LOB テーブルの MessageFromLOB および MessageToLOB が含まれて、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ データベース。  
  
 使用`GetMessages`は、トラブルシューティングまたは開発のいずれか。 既定では、コードは、base 64 文字列を返します。  
  
> [!NOTE]
>  GetMessages.cs サンプル コードには、コードの 2 つのセクションが含まれています —、LOB テーブルのいずれかからメッセージを取得するために、否認不可テーブルのいずれかからメッセージを取得する 1 つ 1。 目的ごとに個別のアプリケーションを作成します。  
  
### <a name="to-retrieve-messages-from-an-lob-table"></a>LOB テーブルからメッセージを取得するには  
  
1.  プログラムには、次のサンプル コードを追加します。  
  
     `private static string GetLOBMessage(string sMessageSource, string sMessageID)`  
  
2.  設定、`sMessageSource`パラメーターを MessagesFromLOB または MessagesToLOB テーブルにします。  
  
3.  設定、`sMessageID`パラメーターの値を**MessageID**フィールド、データベースにします。  
  
    > [!NOTE]
    >  アプリケーションでは、取得したメッセージを含む文字列を返します。  
  
### <a name="to-retrieve-messages-from-a-non-repudiation-table"></a>否認不可テーブルからメッセージを取得するには  
  
1.  プログラムには、次のサンプル コードを追加します。  
  
     `private static string GetNRMessage(string sMessageSource, string sMessageID)`  
  
2.  設定、 `sMessageSource` MessageStorageIn テーブルまたは MessageStorageOut テーブルへのパラメーター。  
  
3.  設定、`sMessageID`パラメーターの値を**RecordID**フィールド、データベースにします。  
  
    > [!NOTE]
    >  アプリケーションでは、取得したメッセージを含む文字列を返します。  
  
## <a name="demonstrates"></a>使用例  
 GetMessages サンプルには、コードの次の 2 つのセクションが含まれます。  
  
-   1 つのセクションでは、いずれか、否認不可テーブルからバイナリ メッセージを取得し、判読できる ASCII 形式に変換する方法を示します。  
  
-   その他のセクションでは、1 つの LOB テーブルからメッセージを取得する方法を示します。 LOB テーブル内のメッセージが既に ASCII 形式で、これは、SQL select ステートメント。  
  
    > [!IMPORTANT]
    >  デモのためは、提供されたサンプル コードは、SQL インジェクションの脆弱性しがちな直接 SQL ステートメントを使用します。 運用環境では、このような脆弱性を防ぐために、直接 SQL ステートメントではなく、パラメーター化された SQL ストアド プロシージャを使用することをお勧めします。  
  
## <a name="example"></a>例  
 否認不可テーブルまたは LOB テーブルからメッセージを取得するためには、次のコード例では、2 つのセクションのいずれかを使用します。  
  
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
 [メッセージ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)