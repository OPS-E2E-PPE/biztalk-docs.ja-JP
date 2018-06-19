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
# <a name="getmessages-sample"></a><span data-ttu-id="652bf-102">GetMessages サンプル</span><span class="sxs-lookup"><span data-stu-id="652bf-102">GetMessages Sample</span></span>
<span data-ttu-id="652bf-103">ここでは、メッセージ否認不可テーブルまたは基幹業務 (LOB) テーブルから、ユーザーが理解できる形式でメッセージを取得するためのサンプル コードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="652bf-103">This topic provides sample code that you can use to retrieve messages from one of the message non-repudiation tables or one of the line-of-business (LOB) tables in a readable form.</span></span> <span data-ttu-id="652bf-104">メッセージ否認不可テーブルには、[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]Archive データベースの MessageStorageIn および MessageStorageOut が含まれます。LOB テーブルには、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA データベースの MessageFromLOB および MessageToLOB が含まれます。</span><span class="sxs-lookup"><span data-stu-id="652bf-104">The message non-repudiation tables include MessageStorageIn and MessageStorageOut in the [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]Archive database; the LOB tables include MessageFromLOB and MessageToLOB in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA database.</span></span>  
  
 <span data-ttu-id="652bf-105">トラブルシューティングや展開には、`GetMessages` を使用します。</span><span class="sxs-lookup"><span data-stu-id="652bf-105">Use `GetMessages` for either troubleshooting or development.</span></span> <span data-ttu-id="652bf-106">既定では、コードは Base 64 文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="652bf-106">By default, the code returns a base 64 string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="652bf-107">GetMessages.cs サンプル コードには、2 つのコード セクションが含まれています。1 つのセクションは LOB テーブルからメッセージを取得するためのもので、もう 1 つは否認不可テーブルからメッセージを取得するためのものです。</span><span class="sxs-lookup"><span data-stu-id="652bf-107">The GetMessages.cs sample code contains two sections of code—one for retrieving messages from one of the LOB tables, and one for retrieving messages from one of the non-repudiation tables.</span></span> <span data-ttu-id="652bf-108">目的ごとに個別のアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="652bf-108">Create separate applications for each purpose.</span></span>  
  
### <a name="to-retrieve-messages-from-an-lob-table"></a><span data-ttu-id="652bf-109">LOB テーブルからメッセージを取得するには</span><span class="sxs-lookup"><span data-stu-id="652bf-109">To retrieve messages from an LOB table</span></span>  
  
1.  <span data-ttu-id="652bf-110">次のサンプル コードをプログラムに追加します。</span><span class="sxs-lookup"><span data-stu-id="652bf-110">Add the following sample code to your program:</span></span>  
  
     `private static string GetLOBMessage(string sMessageSource, string sMessageID)`  
  
2.  <span data-ttu-id="652bf-111">`sMessageSource` パラメーターを MessagesFromLOB テーブル、MessagesToLOB テーブルのいずれかに設定します。</span><span class="sxs-lookup"><span data-stu-id="652bf-111">Set the `sMessageSource` parameter to either the MessagesFromLOB or MessagesToLOB table.</span></span>  
  
3.  <span data-ttu-id="652bf-112">設定、`sMessageID`パラメーターの値を**MessageID**フィールド、データベースにします。</span><span class="sxs-lookup"><span data-stu-id="652bf-112">Set the `sMessageID` parameter to the value of the **MessageID** field in the database.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="652bf-113">アプリケーションでは、取得したメッセージを表す文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="652bf-113">The application returns a string that contains the retrieved message.</span></span>  
  
### <a name="to-retrieve-messages-from-a-non-repudiation-table"></a><span data-ttu-id="652bf-114">否認不可テーブルからメッセージを取得するには</span><span class="sxs-lookup"><span data-stu-id="652bf-114">To retrieve messages from a non-repudiation table</span></span>  
  
1.  <span data-ttu-id="652bf-115">次のサンプル コードをプログラムに追加します。</span><span class="sxs-lookup"><span data-stu-id="652bf-115">Add the following sample code to your program:</span></span>  
  
     `private static string GetNRMessage(string sMessageSource, string sMessageID)`  
  
2.  <span data-ttu-id="652bf-116">`sMessageSource` パラメーターを MessageStorageIn テーブル、MessageStorageOut テーブルのいずれかに設定します。</span><span class="sxs-lookup"><span data-stu-id="652bf-116">Set the `sMessageSource` parameter to either the MessageStorageIn or MessageStorageOut table.</span></span>  
  
3.  <span data-ttu-id="652bf-117">設定、`sMessageID`パラメーターの値を**RecordID**フィールド、データベースにします。</span><span class="sxs-lookup"><span data-stu-id="652bf-117">Set the `sMessageID` parameter to the value of the **RecordID** field in the database.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="652bf-118">アプリケーションでは、取得したメッセージを表す文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="652bf-118">The application returns a string that contains the retrieved message.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="652bf-119">使用例</span><span class="sxs-lookup"><span data-stu-id="652bf-119">Demonstrates</span></span>  
 <span data-ttu-id="652bf-120">GetMessages サンプルには、次の 2 つのコード セクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="652bf-120">The GetMessages sample includes the following two sections of code:</span></span>  
  
-   <span data-ttu-id="652bf-121">1 つのセクションは、否認不可テーブルからバイナリ メッセージを取得して、ユーザーが理解できる ASCII 形式に変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="652bf-121">One section shows you how to retrieve a binary message from one of the non-repudiation tables, and convert it into readable ASCII form.</span></span>  
  
-   <span data-ttu-id="652bf-122">もう 1 つのセクションは、LOB テーブルからメッセージを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="652bf-122">The other section shows you how to retrieve a message from one of the LOB tables.</span></span> <span data-ttu-id="652bf-123">LOB テーブルのメッセージは既に ASCII 形式なので、これは SQL SELECT ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="652bf-123">Because a message in an LOB table is already in ASCII form, this is a SQL select statement.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="652bf-124">説明の目的で、このサンプル コードは、SQL インジェクションの脆弱性の可能性がある直接 SQL ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="652bf-124">For demonstration purposes, the sample code provided uses a direct SQL statement that is prone to SQL injection vulnerabilities.</span></span> <span data-ttu-id="652bf-125">このような脆弱性を排除するために、運用環境では、直接 SQL ステートメントではなく、パラメーター化された SQL ストアド プロシージャを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="652bf-125">In a production environment, it is recommended that you use parameterized SQL stored procedures, instead of the direct SQL statement, to prevent such vulnerabilities.</span></span>  
  
## <a name="example"></a><span data-ttu-id="652bf-126">例</span><span class="sxs-lookup"><span data-stu-id="652bf-126">Example</span></span>  
 <span data-ttu-id="652bf-127">1 つの否認不可テーブルまたは LOB テーブルのいずれかからメッセージを取得するためには、次のコード例では、2 つのセクションのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="652bf-127">Use one of the two sections in the following code example for retrieving messages from one of the non-repudiation tables or one of the LOB tables.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="652bf-128">参照</span><span class="sxs-lookup"><span data-stu-id="652bf-128">See Also</span></span>  
 [<span data-ttu-id="652bf-129">メッセージング サンプル</span><span class="sxs-lookup"><span data-stu-id="652bf-129">Messaging Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)