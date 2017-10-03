---
title: "WCF サービス モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, performing a SQLEXECUTE operation
- SQLEXECUTE operation, performing a
- how to, invoke the SQLEXECUTE operation
ms.assetid: d3f61e5f-4453-4a76-9bc6-40d91cb58224
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6bda1c864e7a6eff442099d6caf1a2bba98e7f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="fe4ef-102">WCF サービス モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-102">Run SQLEXECUTE operation in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="fe4ef-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle のデータベース成果物の操作の標準セットを表示します。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-103">The[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces a standard set of operations on Oracle database artifacts.</span></span> <span data-ttu-id="fe4ef-104">これらの操作を使用すると、Oracle 関数またはプロシージャの呼び出しなどの操作または基本的な SQL データ操作言語 (DML) 操作でテーブルを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-104">By using these operations, you can do things like call an Oracle function or procedure, or perform basic SQL data manipulation language (DML) operations on tables.</span></span> <span data-ttu-id="fe4ef-105">ただし、シナリオが考えられます、ビジネス ロジックによって操作を実行する必要があること、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]発生しません。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-105">However, there may be scenarios driven by your business logic that require you to perform operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not surface.</span></span> <span data-ttu-id="fe4ef-106">たとえばをする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-106">For example, you may want to:</span></span>  
  
-   <span data-ttu-id="fe4ef-107">表示されませんがデータベースのアイテムに対して操作を実行、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 たとえば、CURVAL または Oracle シーケンスの NEXTVAL を取得します。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-107">Perform an operation on database artifacts that are not surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; for example, get the CURVAL or NEXTVAL of an Oracle SEQUENCE.</span></span>  
  
-   <span data-ttu-id="fe4ef-108">データ定義言語の操作です。たとえば、テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-108">Perform Data Definition Language operations; for example, create a table.</span></span>  
  
-   <span data-ttu-id="fe4ef-109">デザイン時に存在しませんでした、データベースの成果物の操作を実行します。たとえば、ビジネス ロジックによって作成される一時テーブル内のレコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-109">Perform operations on a database artifact that was not present at design time; for example, update records in a temporary table that is created by your business logic.</span></span>  
  
-   <span data-ttu-id="fe4ef-110">操作よりもテーブルでより複雑な DML 操作を実行する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェス; たとえば、クエリを実行して、含む JOIN 句です。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-110">Perform more complex DML operations on tables than the operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces; for example, to perform a query that includes a JOIN clause.</span></span>  
  
 <span data-ttu-id="fe4ef-111">これらのシナリオでは、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] SQLEXECUTE 操作を表示します。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-111">For these kinds of scenarios, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces the SQLEXECUTE operation.</span></span> <span data-ttu-id="fe4ef-112">SQLEXECUTE 操作を使用すると、Oracle データベースでパラメーター化された SQL ステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-112">By using the SQLEXECUTE operation, you can perform a parameterized SQL statement on the Oracle database.</span></span> <span data-ttu-id="fe4ef-113">SQLEXECUTE 操作には、セットごとに、同じ SQL ステートメントを実行できるようにするパラメーター セットで構成される入力パラメーター ブロックがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-113">The SQLEXECUTE operation supports an input parameter block comprised of parameter sets that enable you to execute the same SQL statement once for each set.</span></span> <span data-ttu-id="fe4ef-114">SQLEXECUTE 操作は、レコード セットの汎用的な SQL ステートメントの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-114">The SQLEXECUTE operation returns the results of the SQL statement in a generic record set.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="fe4ef-115">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="fe4ef-115">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="fe4ef-116">このトピックは、Oracle シーケンスを使用しての例では、TID_SEQ という名前です。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-116">The examples in this topic use an Oracle SEQUENCE named TID_SEQ.</span></span> <span data-ttu-id="fe4ef-117">このシーケンスを生成するスクリプトは、SDK サンプルの値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-117">A script to generate this SEQUENCE is supplied with the SDK samples.</span></span> <span data-ttu-id="fe4ef-118">SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)です。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-118">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="fe4ef-119">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="fe4ef-119">The WCF Client Class</span></span>  
 <span data-ttu-id="fe4ef-120">WCF サービス モデルには、専用の WCF クライアントが生成されます**SQLEXECUTEClient**、SQLEXECUTE 操作します。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-120">The WCF service model generates a dedicated WCF client, **SQLEXECUTEClient**, for the SQLEXECUTE operation.</span></span> <span data-ttu-id="fe4ef-121">次のコードは、 **SQLEXECUTEClient**と SQLEXECUTE 操作を呼び出すに呼び出すメソッドのシグネチャ。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-121">The following code shows the **SQLEXECUTEClient** and the signature of the method that you call to invoke the SQLEXECUTE operation.</span></span>  
  
```  
public partial class SQLEXECUTEClient : System.ServiceModel.ClientBase<SQLEXECUTE>, SQLEXECUTE {  
  
    ...  
  
    public microsoft.lobservices.oracledb._2007._03.GenRecordRow[] SQLEXECUTE(string SQLSTATEMENT, string PARAMETERSCHEMA, microsoft.lobservices.oracledb._2007._03.PARAMETERDATA[] PARAMETERSET);   
}  
```  
  
 <span data-ttu-id="fe4ef-122">SQLEXECUTE 操作では、汎用のレコード セットを返します。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-122">The SQLEXECUTE operation returns a generic record set.</span></span> <span data-ttu-id="fe4ef-123">このレコード セットが含まれています値には (存在する場合)、SQLEXECUTE 操作が実行されるステートメントによって返されます。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-123">This record set contains the values (if any) that are returned by the statements that the SQLEXECUTE operation executes.</span></span> <span data-ttu-id="fe4ef-124">SQLEXECUTE 操作 PARAMETERDATA オブジェクトの文字列で表される入力パラメーターのコレクションを含む各コレクションには、入力パラメーターのセットを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-124">You can pass sets of input parameters to the SQLEXECUTE operation in a collection of PARAMETERDATA objects, each of which contains a collection of input parameters represented as strings.</span></span> <span data-ttu-id="fe4ef-125">次のコードは、PARAMETERDATA 一連の定義を示しています。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-125">The following code shows the definition of a PARAMETERDATA set.</span></span>  
  
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
  
## <a name="invoking-the-sqlexecute-operation"></a><span data-ttu-id="fe4ef-126">SQLEXECUTE 操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="fe4ef-126">Invoking the SQLEXECUTE Operation</span></span>  
 <span data-ttu-id="fe4ef-127">WCF クライアントを使用して、SQLEXECUTE 操作を呼び出すには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-127">To invoke the SQLEXECUTE operation by using a WCF client, perform the following steps.</span></span>  
  
1.  <span data-ttu-id="fe4ef-128">生成、 **SQLEXECUTEClient**対象のテーブルまたはビューのクラスです。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-128">Generate a **SQLEXECUTEClient** class for the target table or view.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="fe4ef-129">SQLEXECUTE 操作がルート ノードの下に表示される (**/**) で、**カテゴリを選択**ペインで、**アダプター サービス参照の追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-129">The SQLEXECUTE operation is surfaced under the root node (**/**) in the **Select a category** pane in the **Add Adapter Service Reference** dialog box.</span></span>  
  
2.  <span data-ttu-id="fe4ef-130">インスタンスを作成、 **SQLEXECUTEClient**クラス、および呼び出し、 **SQLEXECUTE** Oracle データベースで SQL ステートメントを実行するメソッド。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-130">Create an instance of the **SQLEXECUTEClient** class, and invoke the **SQLEXECUTE** method to execute SQL statements on the Oracle database.</span></span>  
  
 <span data-ttu-id="fe4ef-131">詳細については、WCF クライアント クラスを作成し、に対して操作を呼び出す方法については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-131">For more detailed information about how to create a WCF client class and invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Overview of the WCF service model with the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span></span>  
  
 <span data-ttu-id="fe4ef-132">次の例では、 **SQLEXECUTEClient**を次の SQL ステートメントを実行することによって Oracle シーケンス、TID_SEQ の次の値を取得する:`SELECT tid_seq.nextval id from DUAL`です。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-132">The following example uses the **SQLEXECUTEClient** to get the next value of an Oracle SEQUENCE, TID_SEQ, by executing the following SQL statement: `SELECT tid_seq.nextval id from DUAL`.</span></span> <span data-ttu-id="fe4ef-133">出力がコンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-133">The output is then written to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fe4ef-134">参照</span><span class="sxs-lookup"><span data-stu-id="fe4ef-134">See Also</span></span>  
 [<span data-ttu-id="fe4ef-135">WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="fe4ef-135">Develop Oracle Database applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)