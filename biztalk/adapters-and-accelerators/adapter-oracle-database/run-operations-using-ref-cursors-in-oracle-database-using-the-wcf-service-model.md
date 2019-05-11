---
title: WCF サービス モデルを使用して Oracle データベースでの操作を使用して REF CURSOR の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, performing operations using REF CURSORS
- REF CURSORS, performing operations
ms.assetid: b4cb9ede-eae1-44d7-8ba5-7e1261ccfa3b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3c4d4f9eeac5ebc6b821638f1b1da8276ba4822
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376076"
---
# <a name="run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="f6d2b-102">WCF サービス モデルを使用して Oracle データベースでの操作を使用して REF CURSOR の実行します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-102">Run Operations Using REF CURSORS in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="f6d2b-103">REF CURSOR は、結果セットで、Oracle データベースへのポインターを表す PL/SQL の Oracle データ型です。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-103">A REF CURSOR is an Oracle PL/SQL data type that represents a pointer to a result set in the Oracle database.</span></span> <span data-ttu-id="f6d2b-104">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]プロシージャ、関数、およびパッケージの REF CURSOR パラメーターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports REF CURSOR parameters in procedures, functions, and packages.</span></span> <span data-ttu-id="f6d2b-105">REF CURSOR パラメーターには、厳密に型指定またはプロシージャまたは関数の宣言方法に応じて弱い型指定ができます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-105">REF CURSOR parameters can be strongly-typed or weakly-typed depending on how they are declared in the procedure or function.</span></span> <span data-ttu-id="f6d2b-106">REF CURSOR パラメーターを表現する方法の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[の REF CURSOR のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)します。次の表では、WCF サービス モデルでの REF CURSOR パラメーターを表現する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-106">For a detailed explanation of how REF CURSOR parameters are represented by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Message Schemas for REF CURSORS](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md).The following table summarizes how REF CURSOR parameters are represented in the WCF service model.</span></span>  
  
|<span data-ttu-id="f6d2b-107">パラメーターの方向</span><span class="sxs-lookup"><span data-stu-id="f6d2b-107">Parameter Direction</span></span>|<span data-ttu-id="f6d2b-108">厳密に型指定の REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="f6d2b-108">Strongly-typed REF CURSOR</span></span>|<span data-ttu-id="f6d2b-109">厳密に型指定の REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="f6d2b-109">Weakly-typed REF CURSOR</span></span>|  
|-------------------------|--------------------------------|------------------------------|  
|<span data-ttu-id="f6d2b-110">IN</span><span class="sxs-lookup"><span data-stu-id="f6d2b-110">IN</span></span>|`string [PARAM_NAME]`<br /><br /> <span data-ttu-id="f6d2b-111">PL/SQL ブロックを含む文字列。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-111">String that contains a PL/SQL block.</span></span> <span data-ttu-id="f6d2b-112">PL/SQL ブロックは、「オープンの選択」ステートメントを実行するか、関数またはプロシージャを呼び出すことによって開かれた REF CURSOR を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-112">The PL/SQL block must return an opened REF CURSOR either by executing an "OPEN FOR SELECT" statement or by invoking a function or procedure.</span></span> <span data-ttu-id="f6d2b-113">疑問符 (?) では、REF CURSOR を返す、パラメーターの位置を示します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-113">A question mark (?) indicates the position of the REF CURSOR that returns the parameter.</span></span> <span data-ttu-id="f6d2b-114">たとえば、"オープンを開始しますか。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-114">For example, "BEGIN OPEN ?</span></span> <span data-ttu-id="f6d2b-115">SELECT \* MY_TABLE; から最後に、"または"開始 MY_PROC (PARM1、?、PARM2);終了;"します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-115">FOR SELECT \* FROM MY_TABLE; END", or "BEGIN MY_PROC(PARM1, ?, PARM2); END;".</span></span>|<span data-ttu-id="f6d2b-116">厳密に型指定と同じ</span><span class="sxs-lookup"><span data-stu-id="f6d2b-116">Same as strongly-typed</span></span>|  
|<span data-ttu-id="f6d2b-117">OUT</span><span class="sxs-lookup"><span data-stu-id="f6d2b-117">OUT</span></span>|`out [PROC_NS].[PARAM_NAME]RECORD[] [PARAM_NAME]`<br /><br /> <span data-ttu-id="f6d2b-118">厳密に型指定されたレコード セット。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-118">A strongly-typed record set.</span></span>|`out [GENERIC_NS].GenRecordRow[] [PARAM_NAME]`<br /><br /> <span data-ttu-id="f6d2b-119">厳密に型指定されたジェネリック レコード セット。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-119">A weakly-typed generic record set.</span></span>|  
|<span data-ttu-id="f6d2b-120">OUT IN</span><span class="sxs-lookup"><span data-stu-id="f6d2b-120">IN OUT</span></span>|<span data-ttu-id="f6d2b-121">REF CURSOR アウトでは、パラメーターは IN と OUT パラメーターに分割されます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-121">IN OUT REF CURSOR parameters are split into an IN and an OUT parameter.</span></span> <span data-ttu-id="f6d2b-122">IN パラメーターは、OUT パラメーターと区別するためのメソッド シグネチャで"_IN"が付加されます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-122">The IN parameter is appended with "_IN" in the method signature to distinguish it from the OUT parameter.</span></span> <span data-ttu-id="f6d2b-123">OUT パラメーターは、厳密に型指定されたレコード セットで表されます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-123">The OUT parameter is represented by a strongly-typed record set.</span></span><br /><br /> `string [PARAM_NAME]_IN`<br /><br /> `out [PROC_NS].[PARAM_NAME]RECORD[] [PARAM_NAME]`|<span data-ttu-id="f6d2b-124">REF CURSOR アウトでは、パラメーターは IN と OUT パラメーターに分割されます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-124">IN OUT REF CURSOR parameters are split into an IN and an OUT parameter.</span></span> <span data-ttu-id="f6d2b-125">IN パラメーターは、OUT パラメーターと区別するためには、"_IN"が付加されます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-125">The IN parameter is appended with "_IN" to distinguish it from the OUT parameter.</span></span> <span data-ttu-id="f6d2b-126">OUT パラメーターは、厳密に型指定のレコード セットで表されます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-126">The OUT parameter is represented by a weakly-typed record set.</span></span><br /><br /> `string [PARAM_NAME]_IN`<br /><br /> `out [GENERIC_NS].GenRecordRow[] [PARAM_NAME]`|  
  
 <span data-ttu-id="f6d2b-127">[PARAM_NAME]、Oracle データベースで関数またはプロシージャの定義でパラメーターの名前を =たとえば、MYREFCURSOR です。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-127">[PARAM_NAME] = the name of the parameter in the function or procedure definition on the Oracle database; for example, MYREFCURSOR.</span></span>  
  
 <span data-ttu-id="f6d2b-128">[PROC_NS] パッケージ、プロシージャ、または関数のパラメーターを格納する生成された一意の名前空間を =たとえば、"microsoft.lobservices.oracledb._2007._03.SCOTT します。Package.ACCOUNT_PKG します。GET_ACTIVITY"。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-128">[PROC_NS] = The unique namespace generated to contain parameters of the package, procedure, or function; for example, "microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY".</span></span>  
  
 <span data-ttu-id="f6d2b-129">[GENERIC_NS] 汎用のレコード セットが定義されている名前空間 ="microsoft.lobservices.oracledb._2007._03"。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-129">[GENERIC_NS] = The namespace in which the generic record set is defined, "microsoft.lobservices.oracledb._2007._03".</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="f6d2b-130">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="f6d2b-130">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="f6d2b-131">このトピックの例では、SCOTT/パッケージ/ACCOUNT_PKG Oracle パッケージを使用します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-131">The examples in this topic use the /SCOTT/Package/ACCOUNT_PKG Oracle PACKAGE.</span></span> <span data-ttu-id="f6d2b-132">次の手順は、ACCOUNT_PKG から使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-132">The following procedure is used from ACCOUNT_PKG:</span></span>  
  
```  
PROCEDURE get_activity(inrecs IN SYS_REFCURSOR, status OUT NUMBER, inoutrecs IN OUT activity_ref_type, outrecs OUT SYS_REFCURSOR);  
```  
  
 <span data-ttu-id="f6d2b-133">このパッケージを生成するスクリプトは SDK のサンプルで提供されます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-133">A script to generate this package is supplied with the SDK samples.</span></span> <span data-ttu-id="f6d2b-134">SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-134">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="ref-cursor-parameters-in-the-wcf-service-model"></a><span data-ttu-id="f6d2b-135">WCF サービス モデルの REF CURSOR パラメーター</span><span class="sxs-lookup"><span data-stu-id="f6d2b-135">REF CURSOR Parameters in the WCF Service Model</span></span>  
 <span data-ttu-id="f6d2b-136">次の例では、クラスと/SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY プロシージャの生成された WCF クライアントを示します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-136">The following examples show the classes and WCF client generated for the /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY procedure.</span></span> <span data-ttu-id="f6d2b-137">この手順が厳密に型指定の厳密に型指定の REF CURSOR を IN パラメーターや REF CURSOR をパラメーター。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-137">This procedure has weakly-typed IN and OUT REF CURSOR parameters and a strongly-typed IN OUT REF CURSOR parameter.</span></span>  
  
 <span data-ttu-id="f6d2b-138">GET_ACTIVITY を呼び出すために WCF クライアントで生成されるメソッドのシグネチャを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-138">Here is the signature of the method that is generated in the WCF client to invoke GET_ACTIVITY.</span></span>  
  
```  
public System.Nullable<decimal> GET_ACTIVITY(string INRECS, string INOUTRECS_IN, out microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY.INOUTRECSRECORD[] INOUTRECS, out microsoft.lobservices.oracledb._2007._03.GenRecordRow[] OUTRECS);  
```  
  
 <span data-ttu-id="f6d2b-139">**GET_ACTIVITY**メソッド、INOUTRECS 分割は、2 つのパラメーターの OUT パラメーター。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-139">In the **GET_ACTIVITY** method, the IN OUT parameter INOUTRECS is split into two parameters:</span></span>  
  
- <span data-ttu-id="f6d2b-140">INOUTRECS_IN の REF CURSOR パラメーターを表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-140">INOUTRECS_IN is a string that represents an IN REF CURSOR parameter.</span></span>  
  
- <span data-ttu-id="f6d2b-141">INOUTRECS は、REF CURSOR 出力パラメーターを表す厳密に型指定されたレコード セットです。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-141">INOUTRECS is a strongly-typed record set that represents an OUT REF CURSOR parameter.</span></span>  
  
  <span data-ttu-id="f6d2b-142">厳密に型指定された OUT パラメーター、OUTRECS は、汎用のレコード セットとして表されます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-142">The weakly-typed OUT parameter, OUTRECS, is represented as a generic record set.</span></span> <span data-ttu-id="f6d2b-143">厳密に型指定されたパラメーター、INRECS には、文字列として表されます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-143">The weakly-typed IN parameter, INRECS, is represented as a string.</span></span>  
  
### <a name="strongly-typed-out-ref-cursor-parameters"></a><span data-ttu-id="f6d2b-144">厳密に型指定された OUT、REF CURSOR パラメーター</span><span class="sxs-lookup"><span data-stu-id="f6d2b-144">Strongly-Typed OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="f6d2b-145">厳密に型指定された OUT IN は OUT (または) の REF CURSOR パラメーターは、スキーマ、パッケージ、およびプロシージャまたは関数では、使用の名前に基づく一意の名前空間に生成されます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-145">Strongly-typed OUT (or IN OUT) REF CURSOR parameters are generated in a unique namespace based on the SCHEMA, PACKAGE, and name of the procedure or function in which they are used.</span></span> <span data-ttu-id="f6d2b-146">/SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY プロシージャでこの名前空間は`microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY`します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-146">For the /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY procedure, this namespace is `microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY`.</span></span> <span data-ttu-id="f6d2b-147">クラス名は「レコード」を含むパラメーターの名前が追加された形式し、Oracle のフィールドを表すプロパティは、クラスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-147">The class name is formed by appending the name of the parameter with "RECORD" and the class is composed of properties that represent the Oracle fields.</span></span> <span data-ttu-id="f6d2b-148">INOUTRECS REF CURSOR パラメーターに対して生成される厳密に型指定されたレコードを表すクラスの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-148">The following shows a part of the class that represents the strongly-typed records generated for the INOUTRECS REF CURSOR parameter.</span></span>  
  
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
  
### <a name="weakly-typed-out-ref-cursor-parameters"></a><span data-ttu-id="f6d2b-149">REF CURSOR パラメーターを弱い型指定</span><span class="sxs-lookup"><span data-stu-id="f6d2b-149">Weakly-Typed OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="f6d2b-150">厳密に型指定のアウトは OUT (または) の REF CURSOR パラメーターは、汎用レコード クラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-150">Weakly-typed OUT (or IN OUT) REF CURSOR parameters are represented by the generic record class.</span></span> <span data-ttu-id="f6d2b-151">関数またはプロシージャに関係なく、同じクラス名を使用して、同じ名前空間で汎用のレコード セットが常に生成されます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-151">The generic record set is always generated in the same namespace and with the same class name regardless of the function or procedure.</span></span> <span data-ttu-id="f6d2b-152">次のコードは、汎用レコード クラス**microsoft.lobservices.oracledb._2007._03.GenRecordRow**、OUTRECS アウト SYS_REFCURSOR パラメーター (弱い型指定) のレコードを表します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-152">The following code shows the generic record class, **microsoft.lobservices.oracledb._2007._03.GenRecordRow**, which represents the records for the OUTRECS OUT SYS_REFCURSOR parameter (weakly-typed).</span></span>  
  
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
  
## <a name="using-ref-cursor-parameters-with-a-wcf-client"></a><span data-ttu-id="f6d2b-153">WCF クライアントで REF CURSOR パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-153">Using REF CURSOR Parameters with a WCF Client</span></span>  
 <span data-ttu-id="f6d2b-154">WCF クライアントを使用して REF CURSOR パラメーターを持つ関数またはプロシージャを呼び出す、次を行います。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-154">To invoke a procedure or function with REF CURSOR parameters by using a WCF client, you do the following:</span></span>  
  
1. <span data-ttu-id="f6d2b-155">それぞれの文字列を渡すか、PL/SQL を含む REF CURSOR を IN パラメーターが REF カーソルをオープンするブロックします。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-155">Pass a string for each IN or IN OUT REF CURSOR parameter that contains the PL/SQL block to open the REF CURSOR.</span></span> <span data-ttu-id="f6d2b-156">このブロックでは、OPEN ステートメントを実行することまたは、関数または OUT パラメーターに開かれている REF CURSOR を返すプロシージャを呼び出すできます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-156">This block can either execute an OPEN FOR SELECT statement or invoke a function or procedure that returns an opened REF CURSOR in an OUT parameter.</span></span>  
  
2. <span data-ttu-id="f6d2b-157">プロシージャまたは関数が戻るとき、OUT または REF CURSOR を内のパラメーターに返されるレコード セットでデータを操作します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-157">When the procedure or function returns, operate on the data in the record sets returned for any OUT or IN OUT REF CURSOR parameters.</span></span> <span data-ttu-id="f6d2b-158">レコード セットは、厳密に型指定の REF CURSOR パラメーターを設定する汎用レコードまたは厳密に型指定の REF CURSOR パラメーターを設定する、厳密に型指定されたレコードになります。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-158">The record set will be a generic record set for weakly-typed REF CURSOR parameters or a strongly-typed record set for strongly-typed REF CURSOR parameters.</span></span>  
  
   <span data-ttu-id="f6d2b-159">WCF サービス モデルを使用してプロシージャと関数を呼び出す方法の詳細については、次を参照してください。[関数を呼び出すと、WCF サービス モデルを使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-159">For more information about how to invoke procedures and functions by using the WCF service model, see [Invoke Functions and Procedures in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
   <span data-ttu-id="f6d2b-160">次の例では、GET_ACTIVITY プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-160">The following example calls the GET_ACTIVITY procedure.</span></span> <span data-ttu-id="f6d2b-161">これには、両方の REF CURSOR パラメーターを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-161">It demonstrates both ways of specifying an IN REF CURSOR parameter:</span></span>  
  
- <span data-ttu-id="f6d2b-162">REF CURSOR パラメーター アカウント 100001 のアクティビティを取得するため、開くための SELECT ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-162">For the IN REF CURSOR parameter, an OPEN FOR SELECT statement is specified to return activity for ACCOUNT 100001.</span></span>  
  
- <span data-ttu-id="f6d2b-163">REF CURSOR を IN パラメーターには、/SCOTT/Package/ACCOUNT_PKG/GET_ALL_ACTIVITY プロシージャが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-163">For the IN OUT REF CURSOR parameter, the /SCOTT/Package/ACCOUNT_PKG/GET_ALL_ACTIVITY procedure is invoked.</span></span> <span data-ttu-id="f6d2b-164">この手順では、ACCOUNTACTIVITY テーブル内のアクティビティのすべてを含み、OUT パラメーターとして返します REF カーソルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-164">This procedure opens a REF CURSOR that contains all of the activity in the ACCOUNTACTIVITY table and returns it as an OUT parameter.</span></span>  
  
  <span data-ttu-id="f6d2b-165">この例では、厳密に型指定され、厳密に型指定の両方の REF CURSOR パラメーターに対して返されるレコードからデータを読み取る方法も示します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-165">The example also demonstrates how to read data from the record set returned for both strongly-typed and weakly-typed REF CURSOR parameters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f6d2b-166">参照</span><span class="sxs-lookup"><span data-stu-id="f6d2b-166">See Also</span></span>  
 [<span data-ttu-id="f6d2b-167">WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="f6d2b-167">Develop Oracle Database Application Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)