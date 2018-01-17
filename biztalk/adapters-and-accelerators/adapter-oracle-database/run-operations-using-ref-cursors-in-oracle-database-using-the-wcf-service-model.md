---
title: "WCF サービス モデルを使用して Oracle データベースで操作を使用して REF CURSOR を実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, performing operations using REF CURSORS
- REF CURSORS, performing operations
ms.assetid: b4cb9ede-eae1-44d7-8ba5-7e1261ccfa3b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb527a4451388475ce69a5321d0d05616fc8afde
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="8bc7c-102">WCF サービス モデルを使用して Oracle データベースでの操作を使用して REF CURSOR の実行します。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-102">Run Operations Using REF CURSORS in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="8bc7c-103">REF CURSOR は、Oracle データベースに結果セットへのポインターを表す Oracle PL/SQL データ型です。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-103">A REF CURSOR is an Oracle PL/SQL data type that represents a pointer to a result set in the Oracle database.</span></span> <span data-ttu-id="8bc7c-104">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]プロシージャ、関数、およびパッケージ内の REF CURSOR パラメーターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports REF CURSOR parameters in procedures, functions, and packages.</span></span> <span data-ttu-id="8bc7c-105">REF CURSOR パラメーターには、厳密に型指定または厳密に型指定されたプロシージャまたは関数の宣言方法に応じてを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-105">REF CURSOR parameters can be strongly-typed or weakly-typed depending on how they are declared in the procedure or function.</span></span> <span data-ttu-id="8bc7c-106">REF CURSOR パラメーターを表現する方法の詳細について、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[REF CURSOR のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)です。次の表では、WCF サービス モデルでの REF CURSOR パラメーターを表現する方法をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-106">For a detailed explanation of how REF CURSOR parameters are represented by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Message Schemas for REF CURSORS](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md).The following table summarizes how REF CURSOR parameters are represented in the WCF service model.</span></span>  
  
|<span data-ttu-id="8bc7c-107">パラメーターの方向</span><span class="sxs-lookup"><span data-stu-id="8bc7c-107">Parameter Direction</span></span>|<span data-ttu-id="8bc7c-108">厳密に型指定された REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="8bc7c-108">Strongly-typed REF CURSOR</span></span>|<span data-ttu-id="8bc7c-109">弱い型指定の REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="8bc7c-109">Weakly-typed REF CURSOR</span></span>|  
|-------------------------|--------------------------------|------------------------------|  
|<span data-ttu-id="8bc7c-110">IN</span><span class="sxs-lookup"><span data-stu-id="8bc7c-110">IN</span></span>|`string [PARAM_NAME]`<br /><br /> <span data-ttu-id="8bc7c-111">PL/SQL ブロックを含む文字列です。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-111">String that contains a PL/SQL block.</span></span> <span data-ttu-id="8bc7c-112">PL/SQL ブロックは、"オープンの SELECT"ステートメントを実行するか、関数またはプロシージャを呼び出すことによって開かれた REF CURSOR を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-112">The PL/SQL block must return an opened REF CURSOR either by executing an "OPEN FOR SELECT" statement or by invoking a function or procedure.</span></span> <span data-ttu-id="8bc7c-113">疑問符 (?) では、REF CURSOR を返す、パラメーターの位置を示します。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-113">A question mark (?) indicates the position of the REF CURSOR that returns the parameter.</span></span> <span data-ttu-id="8bc7c-114">たとえば、"OPEN を開始しますか。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-114">For example, "BEGIN OPEN ?</span></span> <span data-ttu-id="8bc7c-115">SELECT \* MY_TABLE; から最後に、"または"BEGIN MY_PROC (PARM1、?、PARM2);終了;"です。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-115">FOR SELECT \* FROM MY_TABLE; END", or "BEGIN MY_PROC(PARM1, ?, PARM2); END;".</span></span>|<span data-ttu-id="8bc7c-116">厳密に型指定と同じ</span><span class="sxs-lookup"><span data-stu-id="8bc7c-116">Same as strongly-typed</span></span>|  
|<span data-ttu-id="8bc7c-117">OUT</span><span class="sxs-lookup"><span data-stu-id="8bc7c-117">OUT</span></span>|`out [PROC_NS].[PARAM_NAME]RECORD[] [PARAM_NAME]`<br /><br /> <span data-ttu-id="8bc7c-118">厳密に型指定されたレコード セット。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-118">A strongly-typed record set.</span></span>|`out [GENERIC_NS].GenRecordRow[] [PARAM_NAME]`<br /><br /> <span data-ttu-id="8bc7c-119">厳密に型指定されたジェネリック レコード セット。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-119">A weakly-typed generic record set.</span></span>|  
|<span data-ttu-id="8bc7c-120">OUT IN</span><span class="sxs-lookup"><span data-stu-id="8bc7c-120">IN OUT</span></span>|<span data-ttu-id="8bc7c-121">REF CURSOR 出力パラメーターは、IN、OUT パラメーターに分割されます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-121">IN OUT REF CURSOR parameters are split into an IN and an OUT parameter.</span></span> <span data-ttu-id="8bc7c-122">IN パラメーターは、OUT パラメーターと区別するためのメソッド シグネチャで"_IN"に付加されます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-122">The IN parameter is appended with "_IN" in the method signature to distinguish it from the OUT parameter.</span></span> <span data-ttu-id="8bc7c-123">OUT パラメーターは、厳密に型指定されたレコード セットで表されます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-123">The OUT parameter is represented by a strongly-typed record set.</span></span><br /><br /> `string [PARAM_NAME]_IN`<br /><br /> `out [PROC_NS].[PARAM_NAME]RECORD[] [PARAM_NAME]`|<span data-ttu-id="8bc7c-124">REF CURSOR 出力パラメーターは、IN、OUT パラメーターに分割されます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-124">IN OUT REF CURSOR parameters are split into an IN and an OUT parameter.</span></span> <span data-ttu-id="8bc7c-125">IN パラメーターには、OUT パラメーターと区別するためには、"_IN"が追加されます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-125">The IN parameter is appended with "_IN" to distinguish it from the OUT parameter.</span></span> <span data-ttu-id="8bc7c-126">OUT パラメーターは、弱い型指定のレコード セットで表されます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-126">The OUT parameter is represented by a weakly-typed record set.</span></span><br /><br /> `string [PARAM_NAME]_IN`<br /><br /> `out [GENERIC_NS].GenRecordRow[] [PARAM_NAME]`|  
  
 <span data-ttu-id="8bc7c-127">[PARAM_NAME]、Oracle データベースで関数またはプロシージャの定義でパラメーターの名前を =たとえば、MYREFCURSOR です。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-127">[PARAM_NAME] = the name of the parameter in the function or procedure definition on the Oracle database; for example, MYREFCURSOR.</span></span>  
  
 <span data-ttu-id="8bc7c-128">[PROC_NS] パッケージ、プロシージャ、または関数のパラメーターを含むに生成された一意の名前空間を =たとえば、"microsoft.lobservices.oracledb._2007._03.SCOTT です。Package.ACCOUNT_PKG です。GET_ACTIVITY"です。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-128">[PROC_NS] = The unique namespace generated to contain parameters of the package, procedure, or function; for example, "microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY".</span></span>  
  
 <span data-ttu-id="8bc7c-129">[GENERIC_NS]、ジェネリックのレコード セットが定義されている名前空間を ="microsoft.lobservices.oracledb._2007._03"です。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-129">[GENERIC_NS] = The namespace in which the generic record set is defined, "microsoft.lobservices.oracledb._2007._03".</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="8bc7c-130">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="8bc7c-130">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="8bc7c-131">このトピックの例では、SCOTT/パッケージ/ACCOUNT_PKG の Oracle パッケージを使用します。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-131">The examples in this topic use the /SCOTT/Package/ACCOUNT_PKG Oracle PACKAGE.</span></span> <span data-ttu-id="8bc7c-132">次の手順は ACCOUNT_PKG から使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-132">The following procedure is used from ACCOUNT_PKG:</span></span>  
  
```  
PROCEDURE get_activity(inrecs IN SYS_REFCURSOR, status OUT NUMBER, inoutrecs IN OUT activity_ref_type, outrecs OUT SYS_REFCURSOR);  
```  
  
 <span data-ttu-id="8bc7c-133">このパッケージを生成するスクリプトは、SDK サンプルの値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-133">A script to generate this package is supplied with the SDK samples.</span></span> <span data-ttu-id="8bc7c-134">SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)です。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-134">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="ref-cursor-parameters-in-the-wcf-service-model"></a><span data-ttu-id="8bc7c-135">WCF サービス モデルの REF CURSOR パラメーター</span><span class="sxs-lookup"><span data-stu-id="8bc7c-135">REF CURSOR Parameters in the WCF Service Model</span></span>  
 <span data-ttu-id="8bc7c-136">次の例では、クラスおよび/SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY プロシージャに対して生成される WCF クライアントを表示します。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-136">The following examples show the classes and WCF client generated for the /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY procedure.</span></span> <span data-ttu-id="8bc7c-137">この手順が弱い型指定に、厳密に型指定された IN OUT REF CURSOR パラメーターや REF CURSOR 出力パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-137">This procedure has weakly-typed IN and OUT REF CURSOR parameters and a strongly-typed IN OUT REF CURSOR parameter.</span></span>  
  
 <span data-ttu-id="8bc7c-138">GET_ACTIVITY を呼び出すために WCF クライアントで生成されるメソッドのシグネチャを次に示します。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-138">Here is the signature of the method that is generated in the WCF client to invoke GET_ACTIVITY.</span></span>  
  
```  
public System.Nullable<decimal> GET_ACTIVITY(string INRECS, string INOUTRECS_IN, out microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY.INOUTRECSRECORD[] INOUTRECS, out microsoft.lobservices.oracledb._2007._03.GenRecordRow[] OUTRECS);  
```  
  
 <span data-ttu-id="8bc7c-139">**GET_ACTIVITY**メソッド、INOUTRECS の 2 つのパラメーターは分割 IN OUT パラメーター。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-139">In the **GET_ACTIVITY** method, the IN OUT parameter INOUTRECS is split into two parameters:</span></span>  
  
-   <span data-ttu-id="8bc7c-140">INOUTRECS_IN は、REF CURSOR パラメーターを表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-140">INOUTRECS_IN is a string that represents an IN REF CURSOR parameter.</span></span>  
  
-   <span data-ttu-id="8bc7c-141">INOUTRECS は、REF CURSOR 出力パラメーターを表す厳密に型指定されたレコード セットです。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-141">INOUTRECS is a strongly-typed record set that represents an OUT REF CURSOR parameter.</span></span>  
  
 <span data-ttu-id="8bc7c-142">厳密に型指定された OUT パラメーター、OUTRECS は、汎用のレコード セットとして表されます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-142">The weakly-typed OUT parameter, OUTRECS, is represented as a generic record set.</span></span> <span data-ttu-id="8bc7c-143">厳密に型指定されたパラメーター、INRECS には、文字列として表されます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-143">The weakly-typed IN parameter, INRECS, is represented as a string.</span></span>  
  
### <a name="strongly-typed-out-ref-cursor-parameters"></a><span data-ttu-id="8bc7c-144">厳密に型指定された出力 REF CURSOR パラメーター</span><span class="sxs-lookup"><span data-stu-id="8bc7c-144">Strongly-Typed OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="8bc7c-145">厳密に型指定された出力 (または IN OUT) スキーマ、パッケージ、およびプロシージャまたはそれらを使用する関数の名前に基づく一意の名前空間での REF CURSOR パラメーターが生成されます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-145">Strongly-typed OUT (or IN OUT) REF CURSOR parameters are generated in a unique namespace based on the SCHEMA, PACKAGE, and name of the procedure or function in which they are used.</span></span> <span data-ttu-id="8bc7c-146">この名前空間は、手順については、/SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY`microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY`です。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-146">For the /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY procedure, this namespace is `microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY`.</span></span> <span data-ttu-id="8bc7c-147">クラス名が「レコード」を持つパラメーターの名前を追加することによって作成され、Oracle フィールドを表すプロパティは、クラスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-147">The class name is formed by appending the name of the parameter with "RECORD" and the class is composed of properties that represent the Oracle fields.</span></span> <span data-ttu-id="8bc7c-148">INOUTRECS REF CURSOR パラメーターに対して生成される厳密に型指定されたレコードを表すクラスの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-148">The following shows a part of the class that represents the strongly-typed records generated for the INOUTRECS REF CURSOR parameter.</span></span>  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class INOUTRECSRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        ...  
  
        private System.Nullable<decimal> TIDField;  
  
        ...  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public System.Nullable<decimal> TID {  
            get {  
                return this.TIDField;  
            }  
            set {  
                this.TIDField = value;  
            }  
        }  
  
        ...  
  
    }  
}  
```  
  
### <a name="weakly-typed-out-ref-cursor-parameters"></a><span data-ttu-id="8bc7c-149">REF CURSOR パラメーターを弱い型指定</span><span class="sxs-lookup"><span data-stu-id="8bc7c-149">Weakly-Typed OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="8bc7c-150">弱い型指定 IN OUT は OUT (または) の REF CURSOR パラメーターはジェネリック レコード クラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-150">Weakly-typed OUT (or IN OUT) REF CURSOR parameters are represented by the generic record class.</span></span> <span data-ttu-id="8bc7c-151">ジェネリック レコード セットが、同じ名前空間の名前を使用して、同じクラス関数またはプロシージャに関係なく常に生成されます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-151">The generic record set is always generated in the same namespace and with the same class name regardless of the function or procedure.</span></span> <span data-ttu-id="8bc7c-152">次のコードは、ジェネリック レコード クラスには、 **microsoft.lobservices.oracledb._2007._03.GenRecordRow**、OUTRECS アウト SYS_REFCURSOR パラメーター (厳密に型指定された) のレコードを表します。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-152">The following code shows the generic record class, **microsoft.lobservices.oracledb._2007._03.GenRecordRow**, which represents the records for the OUTRECS OUT SYS_REFCURSOR parameter (weakly-typed).</span></span>  
  
```  
namespace microsoft.lobservices.oracledb._2007._03 {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class GenRecordRow : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
        private microsoft.lobservices.oracledb._2007._03.GenRecordColumn[] GenRecordColumnField;  
  
        public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
            get {  
                return this.extensionDataField;  
            }  
            set {  
                this.extensionDataField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public microsoft.lobservices.oracledb._2007._03.GenRecordColumn[] GenRecordColumn {  
            get {  
                return this.GenRecordColumnField;  
            }  
            set {  
                this.GenRecordColumnField = value;  
            }  
        }  
    }  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class GenRecordColumn : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
        private string ColumnNameField;  
  
        private string ColumnValueField;  
  
        private string ColumnTypeField;  
  
        public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
            get {  
                return this.extensionDataField;  
            }  
            set {  
                this.extensionDataField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true, EmitDefaultValue=false)]  
        public string ColumnName {  
            get {  
                return this.ColumnNameField;  
            }  
            set {  
                this.ColumnNameField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true)]  
        public string ColumnValue {  
            get {  
                return this.ColumnValueField;  
            }  
            set {  
                this.ColumnValueField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true, EmitDefaultValue=false, Order=2)]  
        public string ColumnType {  
            get {  
                return this.ColumnTypeField;  
            }  
            set {  
                this.ColumnTypeField = value;  
            }  
        }  
    }  
}  
```  
  
## <a name="using-ref-cursor-parameters-with-a-wcf-client"></a><span data-ttu-id="8bc7c-153">WCF クライアントで REF カーソル パラメーターの使用</span><span class="sxs-lookup"><span data-stu-id="8bc7c-153">Using REF CURSOR Parameters with a WCF Client</span></span>  
 <span data-ttu-id="8bc7c-154">WCF クライアントを使用して、プロシージャまたは REF CURSOR パラメーターを持つ関数を呼び出しするには、以下が行います。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-154">To invoke a procedure or function with REF CURSOR parameters by using a WCF client, you do the following:</span></span>  
  
1.  <span data-ttu-id="8bc7c-155">それぞれの文字列を渡すまたは REF カーソルをオープンする PL/SQL を含む IN OUT REF CURSOR パラメーターをブロックします。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-155">Pass a string for each IN or IN OUT REF CURSOR parameter that contains the PL/SQL block to open the REF CURSOR.</span></span> <span data-ttu-id="8bc7c-156">このブロックでは、開いているステートメントを実行することか、関数または OUT パラメーターで開かれている REF CURSOR を返すプロシージャを呼び出すできます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-156">This block can either execute an OPEN FOR SELECT statement or invoke a function or procedure that returns an opened REF CURSOR in an OUT parameter.</span></span>  
  
2.  <span data-ttu-id="8bc7c-157">プロシージャまたは関数が戻るときに、パラメーター、OUT または REF CURSOR を IN に対して返されるレコード セット内のデータを操作します。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-157">When the procedure or function returns, operate on the data in the record sets returned for any OUT or IN OUT REF CURSOR parameters.</span></span> <span data-ttu-id="8bc7c-158">レコード セットは、弱い型指定の REF CURSOR パラメーターのセットの汎用レコードまたは厳密に型指定されたレコードの REF CURSOR パラメーターの厳密に型指定されたセットになります。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-158">The record set will be a generic record set for weakly-typed REF CURSOR parameters or a strongly-typed record set for strongly-typed REF CURSOR parameters.</span></span>  
  
 <span data-ttu-id="8bc7c-159">WCF サービス モデルを使用してプロシージャと関数を呼び出す方法の詳細については、次を参照してください。[関数の呼び出しと、WCF サービス モデルを使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-159">For more information about how to invoke procedures and functions by using the WCF service model, see [Invoke Functions and Procedures in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="8bc7c-160">次の例では、GET_ACTIVITY プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-160">The following example calls the GET_ACTIVITY procedure.</span></span> <span data-ttu-id="8bc7c-161">REF CURSOR パラメーターを指定するのどちらの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-161">It demonstrates both ways of specifying an IN REF CURSOR parameter:</span></span>  
  
-   <span data-ttu-id="8bc7c-162">REF CURSOR パラメーター アカウント 100001 活動で返される、開いている用の SELECT ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-162">For the IN REF CURSOR parameter, an OPEN FOR SELECT statement is specified to return activity for ACCOUNT 100001.</span></span>  
  
-   <span data-ttu-id="8bc7c-163">REF CURSOR を IN パラメーター/SCOTT/Package/ACCOUNT_PKG/GET_ALL_ACTIVITY プロシージャが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-163">For the IN OUT REF CURSOR parameter, the /SCOTT/Package/ACCOUNT_PKG/GET_ALL_ACTIVITY procedure is invoked.</span></span> <span data-ttu-id="8bc7c-164">この手順では、ACCOUNTACTIVITY テーブル内のアクティビティのすべてを含み、OUT パラメーターとして返す REF カーソルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-164">This procedure opens a REF CURSOR that contains all of the activity in the ACCOUNTACTIVITY table and returns it as an OUT parameter.</span></span>  
  
 <span data-ttu-id="8bc7c-165">この例では、レコード厳密に型指定され、弱い型指定の両方の REF CURSOR パラメーターで返されるセットからデータを読み取る方法も示します。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-165">The example also demonstrates how to read data from the record set returned for both strongly-typed and weakly-typed REF CURSOR parameters.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF LOB Adapter SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for WCF LOB Adapter SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// namespaces for strongly-typed and weakly typed REF CURSOR records  
using GET_ACTIVITYns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY;  
using GENERICns = microsoft.lobservices.oracledb._2007._03;  
  
// In this sample, INRECS is opened by using an OPEN FOR statement, and  
// INOUTRECS_IN is opened by calling the GET_ALL_ACTIVITY procedure on Oracle.  
  
namespace OracleRefCursorsSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Create the client  
            SCOTTPackageACCOUNT_PKGClient accountPkgClient =   
                new SCOTTPackageACCOUNT_PKGClient("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG");  
            // Set credentials  
            accountPkgClient.ClientCredentials.UserName.UserName = "SCOTT";  
            accountPkgClient.ClientCredentials.UserName.Password = "TIGER";  
  
            try  
            {  
  
                GET_ACTIVITYns.INOUTRECSRECORD[] strongCursor;  
                GENERICns.GenRecordRow[] weakCursor;  
  
                Console.WriteLine("Opening client");  
                // Open the client  
                accountPkgClient.Open();  
  
                Console.WriteLine("Invoking ACCOUNT_PKG.GET_ACTIVITY");  
                // Get  ACCOUNTACTIVITY records  
                // The IN REF CURSOR is set to all activity for account 100001  
                // The input part of the IN OUT ref cursor calls GET_ALL_ACTIVITY  
                // The weakly-typed OUT REF CURSOR parameter returns a list of activity for account 100001  
                // The strongly-typed IN OUT REF CURSOR parameter returns a list of all activity  
                string inRecsString = "BEGIN OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY WHERE ACCOUNT=100001; END;";  
                string inoutRecsString = "BEGIN ACCOUNT_PKG.GET_ALL_ACTIVITY(?); END;";  
  
                accountPkgClient.GET_ACTIVITY(  
                                inRecsString,  
                                inoutRecsString,  
                                out strongCursor,  
                                out weakCursor);  
  
                // Display strong ref cursor (all activity)  
                Console.WriteLine("\nList of all activity returned (strong ref cursor)");  
                Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
                for (int i = 0; i < strongCursor.Length; i++)  
                {  
                    Console.WriteLine("{0}\t{1}\t{2:C}\t{3}\t{4}",strongCursor[i].TID,  
                        strongCursor[i].ACCOUNT,   
                        strongCursor[i].AMOUNT,   
                        strongCursor[1].TRANSDATE,  
                        strongCursor[i].DESCRIPTION);  
                }  
  
                // Display weak ref cursor (account 100001)  
                Console.WriteLine("\nList of activity for account 100001 returned (weak ref cursor)");  
                Console.WriteLine("Tx Id\tAmount\tDate\t\t\tDescription");  
                for (int i = 0; i < weakCursor.Length; i++)  
                {  
                    Console.WriteLine("{0}\t{1:C}\t{2}\t{3}", weakCursor[i].GenRecordColumn[0].ColumnValue,  
                        weakCursor[i].GenRecordColumn[2].ColumnValue,  
                        weakCursor[i].GenRecordColumn[4].ColumnValue,  
                        weakCursor[i].GenRecordColumn[3].ColumnValue);  
                }  
  
                Console.WriteLine("\nHit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the Oracle Database");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the Oracle Database");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
                throw ex;  
            }  
            finally  
            {  
                // Close the client  
                accountPkgClient.Close();  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8bc7c-166">参照</span><span class="sxs-lookup"><span data-stu-id="8bc7c-166">See Also</span></span>  
 [<span data-ttu-id="8bc7c-167">WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="8bc7c-167">Develop Oracle Database Application Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)