---
title: WCF サービス モデルを使用して Oracle データベースでの操作を使用してレコードの種類の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RECORD types, performing operations
- WCF service model, performing operations using RECORD types
ms.assetid: e7118a86-7470-48bb-aca0-6200dc0bb67c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31785fd5c804e7f599b575678f1f57d60fcf8ebe
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528867"
---
# <a name="run-operations-using-record-types-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="4d93b-102">WCF サービス モデルを使用して Oracle データベースでの操作を使用してレコードの種類の実行します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-102">Run Operations Using RECORD Types in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="4d93b-103">Oracle のレコードの種類は、PL/SQL 関数およびプロシージャに渡されるパラメーターで階層的な情報を表すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4d93b-103">Oracle RECORD types are used to represent hierarchical information in parameters passed to PL/SQL functions and procedures.</span></span> <span data-ttu-id="4d93b-104">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスの複雑な XML 型としてレコードの種類。</span><span class="sxs-lookup"><span data-stu-id="4d93b-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces RECORD types as complex XML types.</span></span> <span data-ttu-id="4d93b-105">WCF サービス モデルでは、レコードの種類が厳密に型指定された .NET クラスに逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-105">In the WCF service model, RECORD types are deserialized to strongly-typed .NET classes.</span></span> <span data-ttu-id="4d93b-106">レコードのフィールドは、クラスのプロパティとして表されます。</span><span class="sxs-lookup"><span data-stu-id="4d93b-106">The record fields are represented as properties on the class.</span></span>  
  
 <span data-ttu-id="4d93b-107">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次の種類のレコードの種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4d93b-107">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports the following kinds of RECORD types:</span></span>  
  
- <span data-ttu-id="4d93b-108">ストアド プロシージャおよび関数でテーブル %rowtype パラメーターとして宣言されているレコードの種類。</span><span class="sxs-lookup"><span data-stu-id="4d93b-108">RECORD types that are declared as TABLE%ROWTYPE parameters in stored procedures and functions.</span></span>  
  
- <span data-ttu-id="4d93b-109">たとえば、PL/SQL パッケージ内のレコードの型パラメーターとして宣言されているレコードの種類 `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`</span><span class="sxs-lookup"><span data-stu-id="4d93b-109">RECORD types that are declared as TYPE of RECORD parameters in PL/SQL packages for example, `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`</span></span>  
  
- <span data-ttu-id="4d93b-110">入れ子になったレコードを含むレコードの種類。</span><span class="sxs-lookup"><span data-stu-id="4d93b-110">RECORD types that contain nested records.</span></span>  
  
- <span data-ttu-id="4d93b-111">OUT、IN として表示されるレコードの種類またはプロシージャまたは関数への OUT パラメーター。</span><span class="sxs-lookup"><span data-stu-id="4d93b-111">RECORD types that appear as IN, OUT, or IN OUT parameters to procedures or functions.</span></span>  
  
- <span data-ttu-id="4d93b-112">関数の戻り値であるレコードの種類。</span><span class="sxs-lookup"><span data-stu-id="4d93b-112">RECORD types that are RETURN values of functions.</span></span>  
  
  <span data-ttu-id="4d93b-113">このトピックでは、WCF サービス モデルでのレコードの種類の表示方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-113">This topic shows how RECORD types are represented in the WCF service model.</span></span> <span data-ttu-id="4d93b-114">Oracle プロシージャと関数を呼び出す方法については、次を参照してください。[関数を呼び出すと、WCF サービス モデルを使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-114">For information about how to call Oracle procedures and functions, see [Invoke Functions and Procedures in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="4d93b-115">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="4d93b-115">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="4d93b-116">このトピックの例では、SCOTT/ACCOUNT_PKG Oracle の PL/SQL パッケージを使用します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-116">The examples in this topic use the /SCOTT/ACCOUNT_PKG Oracle PL/SQL PACKAGE.</span></span> <span data-ttu-id="4d93b-117">ACCOUNT_PKG から、次の要素が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4d93b-117">The following elements are used from ACCOUNT_PKG.</span></span>  
  
```  
TYPE address_rec_type IS RECORD (street customer.street%TYPE, city customer.city%TYPE, state customer.state%TYPE);  
  
FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;  
  
TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);  
  
FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;  
```  
  
 <span data-ttu-id="4d93b-118">このパッケージを生成するスクリプトが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="4d93b-118">A script to generate this package is supplied with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] samples.</span></span> <span data-ttu-id="4d93b-119">詳細については、スクリプトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d93b-119">For more information, see the script</span></span>  
  
 <span data-ttu-id="4d93b-120">サンプルの詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-120">For more information about the samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="record-types-in-the-wcf-service-model"></a><span data-ttu-id="4d93b-121">WCF サービス モデル内のレコードの種類</span><span class="sxs-lookup"><span data-stu-id="4d93b-121">RECORD Types in the WCF Service Model</span></span>  
 <span data-ttu-id="4d93b-122">Oracle のレコードの種類は、複雑な XML 型として表されます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-122">Oracle RECORD types are represented as complex XML types by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="4d93b-123">WCF サービス モデルで複雑な XML 型が、クラスによって表され、このクラスのプロパティは、Oracle のレコードの種類のフィールドを表します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-123">In the WCF service model, complex XML types are represented by a class, and the properties of this class represent the fields of the Oracle RECORD type.</span></span> <span data-ttu-id="4d93b-124">レコード型のパラメーターを表すクラスは、関数またはプロシージャのスキーマとパッケージ (ある場合) に限定されている名前空間に生成されます。</span><span class="sxs-lookup"><span data-stu-id="4d93b-124">The class that represents a RECORD type parameter is generated in a namespace that is qualified by the PACKAGE (if any) and SCHEMA of the function or procedure.</span></span> <span data-ttu-id="4d93b-125">この名前空間には、関数またはプロシージャ パラメーターの一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-125">This namespace uniquely identifies the function or procedure of the parameter.</span></span> <span data-ttu-id="4d93b-126">次の名前空間での Oracle パッケージの ACCOUNT_PKG CREATE_ACCOUNT プロシージャにレコードの型パラメーターを作成するなど。`microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT`します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-126">For example, the RECORD type parameters to the CREATE_ACCOUNT procedure in the Oracle PACKAGE ACCOUNT_PKG are created in the following namespace: `microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT`.</span></span> <span data-ttu-id="4d93b-127">プロシージャおよび関数での複合型を表すために WCF サービス モデルで使用する名前空間の詳細については、次を参照してください。[関数を呼び出すと、WCF サービス モデルを使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-127">For more information about the namespaces used in the WCF service model to represent complex types in procedures and functions, see [Invoke Functions and Procedures in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="4d93b-128">レコード型のパラメーターの名前空間は、プロシージャまたは関数によって決まりますが、レコードの種類が宣言されているレコードの型パラメーターに対して生成されたクラスの名前がところで決定されます。</span><span class="sxs-lookup"><span data-stu-id="4d93b-128">While the namespace of a RECORD type parameter is determined by the procedure or function, the name of the class generated for the RECORD type parameter is determined by the way in which the RECORD type is declared.</span></span> <span data-ttu-id="4d93b-129">次の表は、Oracle のレコードの型パラメーターを宣言することの 2 つの方法に基づいて、クラスの名前を生成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-129">The following table shows how the name of the class is generated based on the two different ways of declaring the Oracle RECORD type parameter.</span></span>  
  
|<span data-ttu-id="4d93b-130">Oracle のレコードの種類</span><span class="sxs-lookup"><span data-stu-id="4d93b-130">Oracle RECORD type</span></span>|<span data-ttu-id="4d93b-131">名前</span><span class="sxs-lookup"><span data-stu-id="4d93b-131">Name</span></span>|<span data-ttu-id="4d93b-132">例</span><span class="sxs-lookup"><span data-stu-id="4d93b-132">Example</span></span>|  
|------------------------|----------|-------------|  
|<span data-ttu-id="4d93b-133">テーブル %rowtype のプロシージャまたは関数のパラメーター</span><span class="sxs-lookup"><span data-stu-id="4d93b-133">TABLE%ROWTYPE procedure or function parameter</span></span>|<span data-ttu-id="4d93b-134">[パラメーター名]レコード</span><span class="sxs-lookup"><span data-stu-id="4d93b-134">[PARAMETER_NAME]RECORD</span></span>|<span data-ttu-id="4d93b-135">ACCTRECORD</span><span class="sxs-lookup"><span data-stu-id="4d93b-135">ACCTRECORD</span></span>|  
|<span data-ttu-id="4d93b-136">レコードのパッケージのパラメーターの型</span><span class="sxs-lookup"><span data-stu-id="4d93b-136">TYPE of RECORD package parameter</span></span>|<span data-ttu-id="4d93b-137">[PACKAGE_NAME][RECORD_TYPE_NAME]RECORD</span><span class="sxs-lookup"><span data-stu-id="4d93b-137">[PACKAGE_NAME][RECORD_TYPE_NAME]RECORD</span></span>|<span data-ttu-id="4d93b-138">ACCOUNT_PKGACCTINFO_REC_TYPERECORD</span><span class="sxs-lookup"><span data-stu-id="4d93b-138">ACCOUNT_PKGACCTINFO_REC_TYPERECORD</span></span>|  
  
 <span data-ttu-id="4d93b-139">[パラメーター名]; プロシージャまたは関数のパラメーターの名前を =たとえば、アカウント</span><span class="sxs-lookup"><span data-stu-id="4d93b-139">[PARAMETER_NAME] = the name of the procedure or function parameter; for example, ACCT.</span></span>  
  
 <span data-ttu-id="4d93b-140">[PACKAGE_NAME] = Oracle パッケージの名前。</span><span class="sxs-lookup"><span data-stu-id="4d93b-140">[PACKAGE_NAME] = the name of the Oracle package.</span></span>  
  
 <span data-ttu-id="4d93b-141">[RECORD_TYPE_NAME]; レコードの種類の宣言で指定された名前を =たとえば、ACCTINFO_REC_TYPE です。</span><span class="sxs-lookup"><span data-stu-id="4d93b-141">[RECORD_TYPE_NAME] = the name specified in the RECORD TYPE declaration; for example, ACCTINFO_REC_TYPE.</span></span>  
  
 <span data-ttu-id="4d93b-142">次のコードでは、2 つの Oracle 関数に対して生成された WCF クライアントのメソッド シグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-142">The following code shows the method signatures of the WCF client generated for two Oracle functions.</span></span> <span data-ttu-id="4d93b-143">/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT 関数は 2 つ単純なレコードで、型パラメーターを受け取り、/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO 関数が入れ子になった 2 つのレコード型を含むレコードの型パラメーターを返します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-143">The /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT function takes two simple RECORD type IN parameters, and the /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO function returns a RECORD type parameter that contains two nested RECORD types.</span></span> <span data-ttu-id="4d93b-144">Oracle 関数の宣言は、コードの先頭に含まれています。</span><span class="sxs-lookup"><span data-stu-id="4d93b-144">The Oracle function declarations are included at the top of the code.</span></span> <span data-ttu-id="4d93b-145">各関数のパラメーターは、一意の名前空間によって修飾されます。</span><span class="sxs-lookup"><span data-stu-id="4d93b-145">The parameters of each function are qualified by a unique namespace.</span></span>  
  
```  
FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;  
FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;  
  
public partial class SCOTTPackageACCOUNT_PKGClient : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKG>, SCOTTPackageACCOUNT_PKG {  
  
    ...  
  
    public System.Nullable<decimal> CREATE_ACCOUNT(microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCTRECORD ACCT, microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCOUNT_PKGADDRESS_REC_TYPERECORD ADDR);  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGACCTINFO_REC_TYPERECORD GET_ACCOUNTINFO(System.Nullable<decimal> AID);  
}  
```  
  
 <span data-ttu-id="4d93b-146">次のコードは、CREATE_ACCOUNT 関数のパラメーターに対して生成されたクラスを示しています。 `FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;`</span><span class="sxs-lookup"><span data-stu-id="4d93b-146">The following code shows the classes generated for the parameters of the CREATE_ACCOUNT function: `FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;`</span></span>  
  
 <span data-ttu-id="4d93b-147">この関数はテーブル %rowtype で宣言されたパラメーターおよびパッケージの種類のレコード型で宣言パラメーター (`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`)。</span><span class="sxs-lookup"><span data-stu-id="4d93b-147">This function has a parameter declared with a TABLE%ROWTYPE and a parameter declared with a TYPE of RECORD package type (`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`).</span></span>  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT {  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class ACCTRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {…}  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class ACCOUNT_PKGADDRESS_REC_TYPERECORD : object, System.Runtime.Serialization.IExtensibleDataObject {…}  
  
}  
```  
  
### <a name="representation-of-a-simple-record-type"></a><span data-ttu-id="4d93b-148">単純なレコード型の表現</span><span class="sxs-lookup"><span data-stu-id="4d93b-148">Representation of a Simple Record Type</span></span>  
 <span data-ttu-id="4d93b-149">次のコードでは、単純なレコードの種類を WCF サービス モデルで表現する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-149">The following code shows how a simple RECORD type is represented in the WCF service model.</span></span> <span data-ttu-id="4d93b-150">このコードの展開ビューを示しています、 **ACCOUNTRECORD** CREATE_ACCOUNT 関数では、アカウント %rowtype パラメーターを表すクラスです。</span><span class="sxs-lookup"><span data-stu-id="4d93b-150">This code shows the expanded view of the **ACCOUNTRECORD** class that represents the ACCOUNT%ROWTYPE parameter in the CREATE_ACCOUNT function.</span></span> <span data-ttu-id="4d93b-151">このクラスでは、レコードのフィールド (行の列) はプロパティとして表されます。</span><span class="sxs-lookup"><span data-stu-id="4d93b-151">In this class, the record fields (row columns) are represented as properties.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
[System.Runtime.Serialization.DataContractAttribute()]  
public partial class ACCTRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
    private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
    private System.Nullable<decimal> ACCTIDField;  
  
    private string NAMEField;  
  
    private System.Nullable<decimal> BALANCEField;  
  
    public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
        get {  
            return this.extensionDataField;  
        }  
        set {  
            this.extensionDataField = value;  
        }  
    }  
  
    [System.Runtime.Serialization.DataMemberAttribute()]  
    public System.Nullable<decimal> ACCTID {  
        get {  
            return this.ACCTIDField;  
        }  
        set {  
            this.ACCTIDField = value;  
        }  
    }  
  
    [System.Runtime.Serialization.DataMemberAttribute()]  
    public string NAME {  
        get {  
            return this.NAMEField;  
        }  
        set {  
            this.NAMEField = value;  
        }  
    }  
  
    [System.Runtime.Serialization.DataMemberAttribute(Order=2)]  
    public System.Nullable<decimal> BALANCE {  
        get {  
            return this.BALANCEField;  
        }  
        set {  
            this.BALANCEField = value;  
        }  
    }  
}  
```  
  
### <a name="representation-of-a-record-type-that-contains-nested-records"></a><span data-ttu-id="4d93b-152">入れ子になったレコードを含むレコード型の表現</span><span class="sxs-lookup"><span data-stu-id="4d93b-152">Representation of a Record Type that Contains Nested Records</span></span>  
 <span data-ttu-id="4d93b-153">次のコードでは、入れ子になったレコードを格納するレコード型の表現を示します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-153">The following code shows the representation of a RECORD type that contains nested records.</span></span> <span data-ttu-id="4d93b-154">この特定のレコードの種類は GET_ACCOUNTINFO 関数の戻り値 (`FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;`)。</span><span class="sxs-lookup"><span data-stu-id="4d93b-154">This particular RECORD type is the RETURN value of the GET_ACCOUNTINFO function (`FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;`).</span></span> <span data-ttu-id="4d93b-155">ACCTINFO_REC_TYPE タイプのレコードの構造を使用して宣言されているパッケージのパラメーターは、(`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`)。</span><span class="sxs-lookup"><span data-stu-id="4d93b-155">The ACCTINFO_REC_TYPE is a package parameter declared using a TYPE of RECORD construct (`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`).</span></span> <span data-ttu-id="4d93b-156">2 つの単純なレコードを入れ子になった型、テーブル % の行のレコードおよびレコードの種類、パッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4d93b-156">It contains two nested simple record types, a TABLE%ROW record and a package TYPE of RECORD record.</span></span> <span data-ttu-id="4d93b-157">これら 2 つの単純なレコードは、親レコードと同じ名前空間で宣言され、予期される名前付け規則に従ってください。</span><span class="sxs-lookup"><span data-stu-id="4d93b-157">These two simple records are declared in the same namespace as their parent record and follow the expected naming convention.</span></span>  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class ACCOUNT_PKGACCTINFO_REC_TYPERECORD : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
        private microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCTRECORD ACCTField;  
  
        private microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGADDRESS_REC_TYPERECORD ADDRESSField;  
  
        public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
            get {  
                return this.extensionDataField;  
            }  
            set {  
                this.extensionDataField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true)]  
        public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCTRECORD ACCT {  
            get {  
                return this.ACCTField;  
            }  
            set {  
                this.ACCTField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true)]  
        public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGADDRESS_REC_TYPERECORD ADDRESS {  
            get {  
                return this.ADDRESSField;  
            }  
            set {  
                this.ADDRESSField = value;  
            }  
        }  
    }  
```  
  
## <a name="using-record-types-in-your-code"></a><span data-ttu-id="4d93b-158">コード内のレコードの種類を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-158">Using RECORD Types in Your Code</span></span>  
 <span data-ttu-id="4d93b-159">レコードの種類を使用して、コードでは簡単です。</span><span class="sxs-lookup"><span data-stu-id="4d93b-159">Using RECORD types in your code is straightforward.</span></span> <span data-ttu-id="4d93b-160">レコード型のパラメーターを持つ関数またはプロシージャを呼び出すには、レコード型または型のインスタンスを作成し、WCF クライアントで、適切なメソッドに渡すことです。</span><span class="sxs-lookup"><span data-stu-id="4d93b-160">To invoke a procedure or function with a RECORD type parameter, you create an instance of the RECORD type or types and pass it to the appropriate method on the WCF client.</span></span> <span data-ttu-id="4d93b-161">プロシージャまたは関数から返される任意の出力のプロパティを読み取ることができます、IN OUT パラメーターまたは関数の戻り値または場合は、レコードの種類として宣言されます。</span><span class="sxs-lookup"><span data-stu-id="4d93b-161">When the procedure or function returns, you can read properties on any OUT or IN OUT parameters or function RETURN values that are declared as RECORD types.</span></span> <span data-ttu-id="4d93b-162">WCF サービス モデルを使用してプロシージャと関数を呼び出す方法の詳細については、次を参照してください。[関数を呼び出すと、WCF サービス モデルを使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-162">For more information about how to invoke procedures and functions by using the WCF service model, see [Invoke Functions and Procedures in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4d93b-163">Oracle のレコード型のパラメーター (と関数の戻り値) は、その関数またはプロシージャ (、およびパッケージ) の名前空間によって修飾されます。</span><span class="sxs-lookup"><span data-stu-id="4d93b-163">Oracle RECORD type parameters (and function returns) are qualified by the namespace of their function or procedure (and package).</span></span> <span data-ttu-id="4d93b-164">これは、2 つの別のプロシージャまたは関数で使用されているレコードの種類が各プロシージャまたは関数の別の名前空間にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-164">This means that a RECORD type that is used in two different procedures or functions will have a different namespace for each procedure or function.</span></span> <span data-ttu-id="4d93b-165">特定のプロシージャまたは関数を使用する場合は、レコードの種類を正しく修飾するためを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d93b-165">You must be sure to qualify the RECORD type correctly when you use it for a specific procedure or function.</span></span> <span data-ttu-id="4d93b-166">たとえば、パッケージに 2 つの異なる関数を IN パラメーターとして使用されるレコードの種類 (レコードの種類の宣言) が各関数に対して生成された一意の名前空間に対応する各宣言に WCF クライアント コードで 2 回宣言されます。</span><span class="sxs-lookup"><span data-stu-id="4d93b-166">For example, a package RECORD type (RECORD of TYPE declaration) that is used as an IN parameter to two different functions will be declared twice in the WCF client code with each declaration corresponding to the unique namespace generated for each function.</span></span> <span data-ttu-id="4d93b-167">それぞれの各関数に渡すパラメーターで、正しい名前空間を使用することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d93b-167">You must be sure to use the correct namespace on the parameter that you pass to each respective function.</span></span>  
  
 <span data-ttu-id="4d93b-168">次の例では、2 つの単純なレコード パラメーター CREATE_ACCOUNT 関数が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4d93b-168">In the following example, the CREATE_ACCOUNT function is called with two simple record parameters.</span></span> <span data-ttu-id="4d93b-169">次に、GET_ACCOUNTINFO 関数が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4d93b-169">Next, the GET_ACCOUNTINFO function is called.</span></span> <span data-ttu-id="4d93b-170">この関数は、入れ子になったレコードを含むレコードの種類を返します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-170">This function returns a RECORD type that contains nested records.</span></span> <span data-ttu-id="4d93b-171">選択したフィールドが、返されるレコードの値は、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="4d93b-171">Selected field values from the returned RECORD are written to the console.</span></span> <span data-ttu-id="4d93b-172">手順を実行する Oracle データベースの資格情報を設定し、WCF クライアントを開くには、この例から省略されます。</span><span class="sxs-lookup"><span data-stu-id="4d93b-172">Steps to set credentials for the Oracle database and to open the WCF client are omitted from this example.</span></span>  
  
```  
// Add WCF, WCF Adapter LOB SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for WCF Adapter LOB SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
…  
  
// Create the client from configuration  
using (SCOTTPackageACCOUNT_PKGClient accountPkgClient = new SCOTTPackageACCOUNT_PKGClient("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG"))  
{  
  
    ...  
  
    decimal acctId;  
  
    // Create an account record  
    // Note: ACCTRECORD is defined in both namespaces so specify the definition  
    // that corresponds to the client.  
  
    microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCTRECORD acctRec =   
        new microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCTRECORD();  
  
    // Set any value for ACCTID -- new account ID is returned by CREATE_ACCOUNT  
    acctRec.ACCTID = 0;  
    acctRec.NAME = "Anton Kirilov";  
    acctRec.BALANCE = 9583;  
  
    // Create address record  
    microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCOUNT_PKGADDRESS_REC_TYPERECORD addrRec = new microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCOUNT_PKGADDRESS_REC_TYPERECORD();  
    addrRec.STREET = "234 Main St";  
    addrRec.CITY = "Boston";  
    addrRec.STATE = "MA";  
  
    // Create account  
    try  
    {  
        acctId = (decimal)accountPkgClient.CREATE_ACCOUNT(acctRec, addrRec);  
    }  
    catch (Exception ex)  
    {  
        // handle exception  
        ...  
    }  
  
    ...  
  
    // Account info record  
    microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGACCTINFO_REC_TYPERECORD acctInfo =  
    new microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGACCTINFO_REC_TYPERECORD();  
  
    // Get account info for the account just created  
    // acctInfo is returned as a nested record type  
    try  
    {  
     acctInfo = accountPkgClient.GET_ACCOUNTINFO(acctId);  
    }  
    catch (Exception ex)  
    {  
    // handle exception  
    ...  
    }  
  
    // Write the account info to the console  
    Console.WriteLine("The account info is:");  
    Console.WriteLine("Name:\t\t\t{0}", acctInfo.ACCT.NAME);  
    Console.WriteLine("Street:\t\t\t{0}", acctInfo.ADDRESS.STREET);  
    Console.WriteLine("City:\t\t\t{0}", acctInfo.ADDRESS.CITY);  
    Console.WriteLine("State:\t\t\t{0}", acctInfo.ADDRESS.STATE);  
    Console.WriteLine("Account Id:\t\t{0}", acctInfo.ACCT.ACCTID);  
    Console.WriteLine("Account Balance:\t{0:C}", acctInfo.ACCT.BALANCE);  
  
    Console.WriteLine("\nHit <RETURN> to finish");  
    Console.ReadLine();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d93b-173">参照</span><span class="sxs-lookup"><span data-stu-id="4d93b-173">See Also</span></span>  
 [<span data-ttu-id="4d93b-174">WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="4d93b-174">Develop Oracle Database applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)