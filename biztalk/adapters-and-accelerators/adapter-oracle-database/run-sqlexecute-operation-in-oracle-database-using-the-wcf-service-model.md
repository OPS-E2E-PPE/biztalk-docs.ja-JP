---
title: WCF サービス モデルを使用して Oracle データベースで SQLEXECUTE 操作の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, performing a SQLEXECUTE operation
- SQLEXECUTE operation, performing a
- how to, invoke the SQLEXECUTE operation
ms.assetid: d3f61e5f-4453-4a76-9bc6-40d91cb58224
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2aedcd9874682ed71af774db72979c152836ab3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004859"
---
# <a name="run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="a7e94-102">WCF サービス モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a7e94-102">Run SQLEXECUTE operation in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="a7e94-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベース アイテムに対する操作の標準セットを明らかになります。</span><span class="sxs-lookup"><span data-stu-id="a7e94-103">The[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces a standard set of operations on Oracle database artifacts.</span></span> <span data-ttu-id="a7e94-104">これらの操作を使用して、Oracle 関数またはプロシージャの呼び出しなどで行うまたは基本的な SQL データ操作言語 (DML) 操作でテーブルを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a7e94-104">By using these operations, you can do things like call an Oracle function or procedure, or perform basic SQL data manipulation language (DML) operations on tables.</span></span> <span data-ttu-id="a7e94-105">ただし、ある可能性があります、ビジネス ロジックによって操作を実行する必要があるシナリオを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]記録されません。</span><span class="sxs-lookup"><span data-stu-id="a7e94-105">However, there may be scenarios driven by your business logic that require you to perform operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not surface.</span></span> <span data-ttu-id="a7e94-106">たとえば、しをたい場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7e94-106">For example, you may want to:</span></span>  
  
- <span data-ttu-id="a7e94-107">表示されませんがデータベースのアイテムに対して操作を実行、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 たとえば、CURVAL または Oracle のシーケンスの NEXTVAL を取得します。</span><span class="sxs-lookup"><span data-stu-id="a7e94-107">Perform an operation on database artifacts that are not surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; for example, get the CURVAL or NEXTVAL of an Oracle SEQUENCE.</span></span>  
  
- <span data-ttu-id="a7e94-108">データ定義言語の操作を実行します。たとえば、テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7e94-108">Perform Data Definition Language operations; for example, create a table.</span></span>  
  
- <span data-ttu-id="a7e94-109">デザイン時に存在しませんでしたが、データベース成果物に対して操作を実行します。たとえば、ビジネス ロジックによって作成される一時テーブル内のレコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="a7e94-109">Perform operations on a database artifact that was not present at design time; for example, update records in a temporary table that is created by your business logic.</span></span>  
  
- <span data-ttu-id="a7e94-110">操作よりもテーブルでより複雑な DML 操作を実行する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェス; JOIN 句を含むクエリを実行するなど。</span><span class="sxs-lookup"><span data-stu-id="a7e94-110">Perform more complex DML operations on tables than the operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces; for example, to perform a query that includes a JOIN clause.</span></span>  
  
  <span data-ttu-id="a7e94-111">このようなシナリオでの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]SQLEXECUTE 操作を表示します。</span><span class="sxs-lookup"><span data-stu-id="a7e94-111">For these kinds of scenarios, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces the SQLEXECUTE operation.</span></span> <span data-ttu-id="a7e94-112">SQLEXECUTE 操作を使用すると、Oracle データベースでパラメーター化 SQL ステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a7e94-112">By using the SQLEXECUTE operation, you can perform a parameterized SQL statement on the Oracle database.</span></span> <span data-ttu-id="a7e94-113">SQLEXECUTE 操作のセットごとに、同じ SQL ステートメントを実行するためのパラメーター セットで構成される、入力パラメーター ブロックをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a7e94-113">The SQLEXECUTE operation supports an input parameter block comprised of parameter sets that enable you to execute the same SQL statement once for each set.</span></span> <span data-ttu-id="a7e94-114">SQLEXECUTE 操作は、ジェネリック レコード セット内の SQL ステートメントの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="a7e94-114">The SQLEXECUTE operation returns the results of the SQL statement in a generic record set.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="a7e94-115">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="a7e94-115">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="a7e94-116">このトピックで使用して Oracle シーケンスの例では、TID_SEQ という名前です。</span><span class="sxs-lookup"><span data-stu-id="a7e94-116">The examples in this topic use an Oracle SEQUENCE named TID_SEQ.</span></span> <span data-ttu-id="a7e94-117">このシーケンスを生成するスクリプトは SDK のサンプルで提供されます。</span><span class="sxs-lookup"><span data-stu-id="a7e94-117">A script to generate this SEQUENCE is supplied with the SDK samples.</span></span> <span data-ttu-id="a7e94-118">SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)します。</span><span class="sxs-lookup"><span data-stu-id="a7e94-118">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="a7e94-119">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="a7e94-119">The WCF Client Class</span></span>  
 <span data-ttu-id="a7e94-120">WCF サービス モデルは、専用の WCF クライアントを生成します**SQLEXECUTEClient**、SQLEXECUTE 操作。</span><span class="sxs-lookup"><span data-stu-id="a7e94-120">The WCF service model generates a dedicated WCF client, **SQLEXECUTEClient**, for the SQLEXECUTE operation.</span></span> <span data-ttu-id="a7e94-121">次のコードは、 **SQLEXECUTEClient** SQLEXECUTE 操作を呼び出すために呼び出すメソッドのシグネチャとします。</span><span class="sxs-lookup"><span data-stu-id="a7e94-121">The following code shows the **SQLEXECUTEClient** and the signature of the method that you call to invoke the SQLEXECUTE operation.</span></span>  
  
```  
public partial class SQLEXECUTEClient : System.ServiceModel.ClientBase<SQLEXECUTE>, SQLEXECUTE {  
  
    ...  
  
    public microsoft.lobservices.oracledb._2007._03.GenRecordRow[] SQLEXECUTE(string SQLSTATEMENT, string PARAMETERSCHEMA, microsoft.lobservices.oracledb._2007._03.PARAMETERDATA[] PARAMETERSET);   
}  
```  
  
 <span data-ttu-id="a7e94-122">SQLEXECUTE 操作には、汎用のレコード セットが返されます。</span><span class="sxs-lookup"><span data-stu-id="a7e94-122">The SQLEXECUTE operation returns a generic record set.</span></span> <span data-ttu-id="a7e94-123">このレコード セットが含まれています、値には (ある場合) その SQLEXECUTE 操作の実行ステートメントによって返されます。</span><span class="sxs-lookup"><span data-stu-id="a7e94-123">This record set contains the values (if any) that are returned by the statements that the SQLEXECUTE operation executes.</span></span> <span data-ttu-id="a7e94-124">文字列として表される入力パラメーターのコレクションを含む各 PARAMETERDATA オブジェクトのコレクションで SQLEXECUTE 操作には、入力パラメーターのセットを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="a7e94-124">You can pass sets of input parameters to the SQLEXECUTE operation in a collection of PARAMETERDATA objects, each of which contains a collection of input parameters represented as strings.</span></span> <span data-ttu-id="a7e94-125">次のコードでは、PARAMETERDATA セットの定義を示します。</span><span class="sxs-lookup"><span data-stu-id="a7e94-125">The following code shows the definition of a PARAMETERDATA set.</span></span>  
  
```  
namespace microsoft.lobservices.oracledb._2007._03 {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class PARAMETERDATA : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        ...  
  
        private string[] PARAMETERField;  
  
        ...  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public string[] PARAMETER {  
            get {  
                return this.PARAMETERField;  
            }  
            set {  
                this.PARAMETERField = value;  
            }  
        }  
    }  
}  
```  
  
## <a name="invoking-the-sqlexecute-operation"></a><span data-ttu-id="a7e94-126">SQLEXECUTE 操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="a7e94-126">Invoking the SQLEXECUTE Operation</span></span>  
 <span data-ttu-id="a7e94-127">SQLEXECUTE 操作を呼び出すには、WCF クライアントを使用してするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a7e94-127">To invoke the SQLEXECUTE operation by using a WCF client, perform the following steps.</span></span>  
  
1. <span data-ttu-id="a7e94-128">生成、 **SQLEXECUTEClient**対象のテーブルまたはビューのクラス。</span><span class="sxs-lookup"><span data-stu-id="a7e94-128">Generate a **SQLEXECUTEClient** class for the target table or view.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="a7e94-129">SQLEXECUTE 操作は、ルート ノードの下に表示される (**/**) で、**カテゴリを選択**ペインで、**アダプター サービス参照の追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="a7e94-129">The SQLEXECUTE operation is surfaced under the root node (**/**) in the **Select a category** pane in the **Add Adapter Service Reference** dialog box.</span></span>  
  
2. <span data-ttu-id="a7e94-130">インスタンスを作成、 **SQLEXECUTEClient**クラス、および呼び出す、 **SQLEXECUTE** Oracle データベースで SQL ステートメントを実行するメソッド。</span><span class="sxs-lookup"><span data-stu-id="a7e94-130">Create an instance of the **SQLEXECUTEClient** class, and invoke the **SQLEXECUTE** method to execute SQL statements on the Oracle database.</span></span>  
  
   <span data-ttu-id="a7e94-131">WCF クライアント クラスを作成し、操作を呼び出す方法についての詳細、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="a7e94-131">For more detailed information about how to create a WCF client class and invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Overview of the WCF service model with the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span></span>  
  
   <span data-ttu-id="a7e94-132">次の例では、 **SQLEXECUTEClient**次の SQL ステートメントを実行することによって、TID_SEQ、Oracle シーケンスの次の値を取得する:`SELECT tid_seq.nextval id from DUAL`します。</span><span class="sxs-lookup"><span data-stu-id="a7e94-132">The following example uses the **SQLEXECUTEClient** to get the next value of an Oracle SEQUENCE, TID_SEQ, by executing the following SQL statement: `SELECT tid_seq.nextval id from DUAL`.</span></span> <span data-ttu-id="a7e94-133">出力は、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="a7e94-133">The output is then written to the console.</span></span>  
  
```  
using (SQLEXECUTEClient sqlClient = new SQLEXECUTEClient("OracleDBBinding_SQLEXECUTE"))  
{  
    sqlClient.ClientCredentials.UserName.UserName = "SCOTT";  
    sqlClient.ClientCredentials.UserName.Password = "TIGER";  
    try  
    {  
        sqlClient.Open();  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Error opening SQL client " + ex.Message);  
        throw;  
    }  
    microsoft.lobservices.oracledb._2007._03.GenRecordRow[] sequenceRec =   
        new microsoft.lobservices.oracledb._2007._03.GenRecordRow[0];  
  
    try  
    {  
        sequenceRec = sqlClient.SQLEXECUTE("SELECT tid_seq.nextval id from DUAL", null, null);  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Error executing SQL client " + ex.Message);  
        throw;  
    }  
  
    if (sequenceRec.Length > 0)  
    {  
        Console.WriteLine("TID_SEQUENCE value is {0}", sequenceRec[0].GenRecordColumn[0].ColumnValue);  
    }  
    else  
    {  
    Console.WriteLine("Couldn't get next TID_SEQUENCE value");  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7e94-134">参照</span><span class="sxs-lookup"><span data-stu-id="a7e94-134">See Also</span></span>  
 [<span data-ttu-id="a7e94-135">WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="a7e94-135">Develop Oracle Database applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)