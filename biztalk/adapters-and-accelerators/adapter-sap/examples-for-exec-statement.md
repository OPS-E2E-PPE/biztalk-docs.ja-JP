---
title: EXEC ステートメントの例は、BizTalk での mySAP アダプターで |Microsoft ドキュメント
description: EXEC 例と、mySAP アダプターの BizTalk アダプター パック (BAP) を使用するサンプル
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad2691f4-34bb-423c-9b3e-4abe2d55ddac
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6eaae930d7d94d24bac9d484957ccf02718af60f
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="examples-for-exec-statement"></a><span data-ttu-id="1b82c-103">EXEC ステートメントの例</span><span class="sxs-lookup"><span data-stu-id="1b82c-103">Examples for EXEC Statement</span></span>
<span data-ttu-id="1b82c-104">このトピックでは、さまざまな EXEC ステートメントの構文例を示します。</span><span class="sxs-lookup"><span data-stu-id="1b82c-104">This topic shows example syntax for various EXEC statements.</span></span>

## <a name="sample-statements"></a><span data-ttu-id="1b82c-105">ステートメントの例</span><span class="sxs-lookup"><span data-stu-id="1b82c-105">Sample statements</span></span> 
  
-   <span data-ttu-id="1b82c-106">入力パラメーターをとらない BAPI を実行するには次の構文を使用します。データがによって返される、 **DataReader**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1b82c-106">To execute a BAPI that takes no input parameters, use the following syntax; data is returned through a **DataReader** object:</span></span>  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST  
    ```  
  
-   <span data-ttu-id="1b82c-107">入力パラメーターを受け取る RFC を実行するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b82c-107">To execute an RFC that takes input parameters, use the following syntax:</span></span>  
  
    ```  
    EXEC RFC_CUSTOMER_GET @NAME1='Contoso'  
    ```  
  
-   <span data-ttu-id="1b82c-108">変数として指定された入力パラメーターを受け取る RFC を実行するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b82c-108">To execute an RFC that takes input parameters specified as a variable, use the following syntax:</span></span>  
  
    ```  
    EXEC RFC_CUSTOMER_GET @var=@var  
    ```  
  
     <span data-ttu-id="1b82c-109">この例では、という名前のパラメーターを作成する必要があります`@var`RFC_CUSTOMER_GET の最初のパラメーターが KUNNR (カスタマー番号) に対応しているために、(たとえばを 1001 に)、値を明示的に設定し、</span><span class="sxs-lookup"><span data-stu-id="1b82c-109">In this example, you must create a parameter named `@var` and set the value explicitly (for example, to 1001), because the first parameter for RFC_CUSTOMER_GET corresponds to KUNNR (Customer Number)</span></span>  
  
-   <span data-ttu-id="1b82c-110">入力パラメーター名の変数を使用する RFC を実行するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b82c-110">To execute an RFC that uses a variable for the input parameter name, use the following syntax:</span></span>  
  
    ```  
    EXEC RFC_CUSTOMER_GET @KUNNR=@var1, @NAME1='Contoso'  
    ```  
  
     <span data-ttu-id="1b82c-111">という名前のパラメーターを作成する必要があります`@var1`の値を指定、および対応するコマンド オブジェクトにバインドします。</span><span class="sxs-lookup"><span data-stu-id="1b82c-111">You must create a parameter named `@var1`, specify the value, and then bind it to the corresponding command object.</span></span> <span data-ttu-id="1b82c-112">新しく作成されたパラメーター オブジェクトの既定の方向は`input`します。</span><span class="sxs-lookup"><span data-stu-id="1b82c-112">The default direction of the newly created parameter object is `input`.</span></span>  
  
-   <span data-ttu-id="1b82c-113">BAPI と戻り値のテーブルをパラメーターとして、実行するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b82c-113">To execute a BAPI and return tables as a parameter, use the following syntax:</span></span>  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST @COMPANYCODE_LIST=@var1 OUTPUT  
    ```  
  
     <span data-ttu-id="1b82c-114">という名前のパラメーターを作成する必要があります`@var1`の値を指定し、対応するコマンド オブジェクトにバインドします。</span><span class="sxs-lookup"><span data-stu-id="1b82c-114">You must create a parameter named `@var1`, specify the value, and bind it to the corresponding command object.</span></span> <span data-ttu-id="1b82c-115">新しく作成されたパラメーター オブジェクトの方向にする必要があります`InputOutput`または`Output`です。</span><span class="sxs-lookup"><span data-stu-id="1b82c-115">The direction of the newly created parameter object should be `InputOutput` or `Output`.</span></span>  
  
-   <span data-ttu-id="1b82c-116">次の EXEC 例では、テーブルの複合型パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1b82c-116">The following EXEC example uses a table complex type parameter.</span></span> <span data-ttu-id="1b82c-117">例では、@fieldsテーブル パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="1b82c-117">In the example, @fields is a TABLE parameter.</span></span>  
  
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
  
-   <span data-ttu-id="1b82c-118">EXEC の次の例では、構造体の複合型を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b82c-118">The following EXEC example uses a STRUCT complex type.</span></span> <span data-ttu-id="1b82c-119">例では、@equimaster構造体のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="1b82c-119">In the example, @equimaster is a STRUCT parameter.</span></span>  
  
    ```  
    exec BAPI_EQMT_MODIFY @equipment='000000000000000637', @equimaster='<EQUIMASTER>           
                <EQUIPMENT xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">equip</EQUIPMENT>  
                <EQUICATGRY xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">E</EQUICATGRY>  
                <MATERIAL xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">mat</MATERIAL>  
              </EQUIMASTER >', @equimaster=@em output  
    ```  
  
## <a name="support-for-complex-parameter-types"></a><span data-ttu-id="1b82c-120">複雑なパラメーターの型のサポート</span><span class="sxs-lookup"><span data-stu-id="1b82c-120">Support for Complex Parameter Types</span></span>  
 <span data-ttu-id="1b82c-121">複合の RFC パラメーター (テーブルと構造体) をサポートするために 2 つの方法を使用する場合、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1b82c-121">There are two ways to support complex RFC parameters (tables and structures) when you use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span></span>  
  
-   <span data-ttu-id="1b82c-122">複合型のインライン XML 値を提供します。</span><span class="sxs-lookup"><span data-stu-id="1b82c-122">Provide an inline XML value for the complex type.</span></span> <span data-ttu-id="1b82c-123">この例は、複雑なパラメーターの型に XML を渡す方法を示しています。*フィールド*です。</span><span class="sxs-lookup"><span data-stu-id="1b82c-123">This example shows how to pass XML to the complex parameter type *fields*.</span></span> <span data-ttu-id="1b82c-124">次の例では、 *@fields*テーブル パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="1b82c-124">In the following example, *@fields* is a table parameter.</span></span>  
  
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
  
-   <span data-ttu-id="1b82c-125">作成、 **DataTable**複合型および SAP パラメーターの値をセット内のフィールドの列を含むパラメーター **DataTable**です。</span><span class="sxs-lookup"><span data-stu-id="1b82c-125">Create a **DataTable** parameter with columns for the fields in the complex type and set the SAP parameter value to **DataTable**.</span></span> <span data-ttu-id="1b82c-126">この例は、設定する方法を示します、@fields複合型を使用して、 **DataTable**です。</span><span class="sxs-lookup"><span data-stu-id="1b82c-126">This example shows how to set the @fields complex type by using a **DataTable**.</span></span>  
  
    ```  
    cmd.CommandText = "exec rfc_read_table @query_table='BNKA', @fields = @p_fields";  
    DataTable dt = new DataTable();  
    dt.Columns.Add("FIELDNAME");  
    SAPParameter p = new SAPParameter("@p_fields");  
    p.Value = dt;  
    ```  
  
## <a name="limitations"></a><span data-ttu-id="1b82c-127">制限事項</span><span class="sxs-lookup"><span data-stu-id="1b82c-127">Limitations</span></span>  
 <span data-ttu-id="1b82c-128">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]複合型の次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="1b82c-128">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] has the following limitations for complex types.</span></span>  
  
-   <span data-ttu-id="1b82c-129">渡す場合、複合型のパラメーターを使用して、 **DataTable**での複合型のすべてのフィールド (列) を含める必要があります、 **DataTable**です。</span><span class="sxs-lookup"><span data-stu-id="1b82c-129">When you pass a complex type in a parameter by using a **DataTable**, you must include all fields (columns) of the complex type in the **DataTable**.</span></span>  
  
-   <span data-ttu-id="1b82c-130">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]はサポートしていません**DbNull**です。</span><span class="sxs-lookup"><span data-stu-id="1b82c-130">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] does not support **DbNull**.</span></span> <span data-ttu-id="1b82c-131">設定することはできません**DbNull**のパラメーターの値として。</span><span class="sxs-lookup"><span data-stu-id="1b82c-131">You cannot set **DbNull** as a value for parameters.</span></span>  
  
