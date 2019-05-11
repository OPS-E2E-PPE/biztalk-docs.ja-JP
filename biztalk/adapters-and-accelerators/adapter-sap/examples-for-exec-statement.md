---
title: BizTalk での mySAP アダプターの EXEC ステートメントの例 |Microsoft Docs
description: EXEC 例と、mySAP アダプターを BizTalk アダプター パック (BAP) を使用したサンプル
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad2691f4-34bb-423c-9b3e-4abe2d55ddac
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75345610fe1585fa5af14f7202d7f87613629198
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373469"
---
# <a name="examples-for-exec-statement"></a><span data-ttu-id="d7108-103">EXEC ステートメントの例</span><span class="sxs-lookup"><span data-stu-id="d7108-103">Examples for EXEC Statement</span></span>
<span data-ttu-id="d7108-104">このトピックでは、さまざまな EXEC ステートメントの構文の例を示します。</span><span class="sxs-lookup"><span data-stu-id="d7108-104">This topic shows example syntax for various EXEC statements.</span></span>

## <a name="sample-statements"></a><span data-ttu-id="d7108-105">サンプル ステートメント</span><span class="sxs-lookup"><span data-stu-id="d7108-105">Sample statements</span></span> 
  
-   <span data-ttu-id="d7108-106">入力パラメーターをとらない BAPI を実行するには、次の構文を使用して、データがによって返される、 **DataReader**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d7108-106">To execute a BAPI that takes no input parameters, use the following syntax; data is returned through a **DataReader** object:</span></span>  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST  
    ```  
  
-   <span data-ttu-id="d7108-107">入力パラメーターを受け取る RFC を実行するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7108-107">To execute an RFC that takes input parameters, use the following syntax:</span></span>  
  
    ```  
    EXEC RFC_CUSTOMER_GET @NAME1='Contoso'  
    ```  
  
-   <span data-ttu-id="d7108-108">変数として指定された入力パラメーターを受け取る RFC を実行するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7108-108">To execute an RFC that takes input parameters specified as a variable, use the following syntax:</span></span>  
  
    ```  
    EXEC RFC_CUSTOMER_GET @var=@var  
    ```  
  
     <span data-ttu-id="d7108-109">この例では、という名前のパラメーターを作成する必要があります`@var`し RFC_CUSTOMER_GET の最初のパラメーターが KUNNR (カスタマー番号) に対応しているため (たとえば、1001) を明示的に値を設定</span><span class="sxs-lookup"><span data-stu-id="d7108-109">In this example, you must create a parameter named `@var` and set the value explicitly (for example, to 1001), because the first parameter for RFC_CUSTOMER_GET corresponds to KUNNR (Customer Number)</span></span>  
  
-   <span data-ttu-id="d7108-110">入力パラメーター名の変数を使用する RFC を実行するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7108-110">To execute an RFC that uses a variable for the input parameter name, use the following syntax:</span></span>  
  
    ```  
    EXEC RFC_CUSTOMER_GET @KUNNR=@var1, @NAME1='Contoso'  
    ```  
  
     <span data-ttu-id="d7108-111">という名前のパラメーターを作成する必要があります`@var1`の値を指定し、対応するコマンド オブジェクトにバインドします。</span><span class="sxs-lookup"><span data-stu-id="d7108-111">You must create a parameter named `@var1`, specify the value, and then bind it to the corresponding command object.</span></span> <span data-ttu-id="d7108-112">新しく作成されたパラメーター オブジェクトの既定の方向は`input`します。</span><span class="sxs-lookup"><span data-stu-id="d7108-112">The default direction of the newly created parameter object is `input`.</span></span>  
  
-   <span data-ttu-id="d7108-113">BAPI と戻り値のテーブルをパラメーターとしてを実行するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7108-113">To execute a BAPI and return tables as a parameter, use the following syntax:</span></span>  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST @COMPANYCODE_LIST=@var1 OUTPUT  
    ```  
  
     <span data-ttu-id="d7108-114">という名前のパラメーターを作成する必要があります`@var1`で、値を指定して、対応するコマンド オブジェクトにバインドします。</span><span class="sxs-lookup"><span data-stu-id="d7108-114">You must create a parameter named `@var1`, specify the value, and bind it to the corresponding command object.</span></span> <span data-ttu-id="d7108-115">新しく作成されたパラメーター オブジェクトの方向にする必要があります`InputOutput`または`Output`します。</span><span class="sxs-lookup"><span data-stu-id="d7108-115">The direction of the newly created parameter object should be `InputOutput` or `Output`.</span></span>  
  
-   <span data-ttu-id="d7108-116">次の EXEC の例では、テーブルの複合型パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7108-116">The following EXEC example uses a table complex type parameter.</span></span> <span data-ttu-id="d7108-117">例では、@fieldsテーブル パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="d7108-117">In the example, @fields is a TABLE parameter.</span></span>  
  
    ```  
    exec rfc_read_table @query_table='BNKA', @fields='<FIELDS xmlns='http://Microsoft.LobServices.Sap/2007/03/Rfc/'>  
                <RFC_DB_FLD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                  <FIELDNAME>BANKL</FIELDNAME>  
                </RFC_DB_FLD>  
                <RFC_DB_FLD  xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                    <FIELDNAME>BANKS</FIELDNAME>  
                </RFC_DB_FLD>  
              </FIELDS>', @fields=@flds output  
    ```  
  
-   <span data-ttu-id="d7108-118">次の EXEC の例では、構造体の複合型を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7108-118">The following EXEC example uses a STRUCT complex type.</span></span> <span data-ttu-id="d7108-119">例では、@equimaster構造体のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="d7108-119">In the example, @equimaster is a STRUCT parameter.</span></span>  
  
    ```  
    exec BAPI_EQMT_MODIFY @equipment='000000000000000637', @equimaster='<EQUIMASTER>           
                <EQUIPMENT xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">equip</EQUIPMENT>  
                <EQUICATGRY xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">E</EQUICATGRY>  
                <MATERIAL xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">mat</MATERIAL>  
              </EQUIMASTER >', @equimaster=@em output  
    ```  
  
## <a name="support-for-complex-parameter-types"></a><span data-ttu-id="d7108-120">複雑なパラメーターの型のサポート</span><span class="sxs-lookup"><span data-stu-id="d7108-120">Support for Complex Parameter Types</span></span>  
 <span data-ttu-id="d7108-121">複雑な RFC パラメーター (テーブルと構造体) をサポートするために 2 つの方法を使用すると、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d7108-121">There are two ways to support complex RFC parameters (tables and structures) when you use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span></span>  
  
- <span data-ttu-id="d7108-122">複合型のインライン XML 値を提供します。</span><span class="sxs-lookup"><span data-stu-id="d7108-122">Provide an inline XML value for the complex type.</span></span> <span data-ttu-id="d7108-123">この例では、複雑なパラメーターの型に XML を渡す*フィールド*します。</span><span class="sxs-lookup"><span data-stu-id="d7108-123">This example shows how to pass XML to the complex parameter type *fields*.</span></span> <span data-ttu-id="d7108-124">次の例では、 <em>@fields</em>テーブル パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="d7108-124">In the following example, <em>@fields</em> is a table parameter.</span></span>  
  
  ```  
  exec rfc_read_table @query_table='BNKA', @fields='<FIELDS xmlns='http://Microsoft.LobServices.Sap/2007/03/Rfc/'>  
              <RFC_DB_FLD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                <FIELDNAME>BANKL</FIELDNAME>  
              </RFC_DB_FLD>  
              <RFC_DB_FLD  xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                  <FIELDNAME>BANKS</FIELDNAME>  
              </RFC_DB_FLD>  
            </FIELDS>', @fields=@flds output  
  ```  
  
- <span data-ttu-id="d7108-125">作成、 **DataTable**複合型および SAP パラメーターの値をセット内のフィールドの列を持つパラメーター **DataTable**します。</span><span class="sxs-lookup"><span data-stu-id="d7108-125">Create a **DataTable** parameter with columns for the fields in the complex type and set the SAP parameter value to **DataTable**.</span></span> <span data-ttu-id="d7108-126">この例では、設定、@fields複合型を使用して、 **DataTable**します。</span><span class="sxs-lookup"><span data-stu-id="d7108-126">This example shows how to set the @fields complex type by using a **DataTable**.</span></span>  
  
  ```  
  cmd.CommandText = "exec rfc_read_table @query_table='BNKA', @fields = @p_fields";  
  DataTable dt = new DataTable();  
  dt.Columns.Add("FIELDNAME");  
  SAPParameter p = new SAPParameter("@p_fields");  
  p.Value = dt;  
  ```  
  
## <a name="limitations"></a><span data-ttu-id="d7108-127">制限事項</span><span class="sxs-lookup"><span data-stu-id="d7108-127">Limitations</span></span>  
 <span data-ttu-id="d7108-128">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]複合型の場合、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="d7108-128">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] has the following limitations for complex types.</span></span>  
  
- <span data-ttu-id="d7108-129">渡すと、複合型パラメーターを使用して、 **DataTable**、複合型のすべてのフィールド (列) を含める必要があります、 **DataTable**します。</span><span class="sxs-lookup"><span data-stu-id="d7108-129">When you pass a complex type in a parameter by using a **DataTable**, you must include all fields (columns) of the complex type in the **DataTable**.</span></span>  
  
- <span data-ttu-id="d7108-130">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]はサポートしていません**DbNull**します。</span><span class="sxs-lookup"><span data-stu-id="d7108-130">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] does not support **DbNull**.</span></span> <span data-ttu-id="d7108-131">設定することはできません**DbNull**パラメーターの値として。</span><span class="sxs-lookup"><span data-stu-id="d7108-131">You cannot set **DbNull** as a value for parameters.</span></span>  
  
