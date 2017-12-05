---
title: "SAP 内の EXECQUERY ステートメントに対して構文 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99bd7fbb-64f2-4327-a8ae-ccb574e56150
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5198335cfa1a7d2036ca05759edc7d04e28cc20b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="syntax-for-an-execquery-statement-in-sap"></a><span data-ttu-id="53604-102">SAP の EXECQUERY ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="53604-102">Syntax for an EXECQUERY Statement in SAP</span></span>
<span data-ttu-id="53604-103">SAP の GUI を使用すると、グラフィカルに表示するクエリ、列および並べ替え順序など、結果セットに含めるテーブルを選択してクエリを作成します。[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] ADO.NET アプリケーションからユーザーは、SAP システムで定義されているクエリの実行に使用できる EXECQUERY 操作を提供することによってこのようなクエリを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="53604-103">You can use the SAP GUI to create queries by graphically selecting the tables you want to query, the columns and sort order you want included in the result set, etc. The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] enables users to execute such queries from an ADO.NET application by providing an EXECQUERY operation that users can use to execute a query defined in the SAP system.</span></span>  
  
 <span data-ttu-id="53604-104">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]カスタム RFC Z_EXECUTE_SAP_QUERY を使用して、SAP システムで定義済みのクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="53604-104">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses a custom RFC Z_EXECUTE_SAP_QUERY to execute the pre-defined queries in the SAP system.</span></span> <span data-ttu-id="53604-105">カスタムの RFC には、これは、標準の SAP システムで定義されている RFC、RSAQ_REMOTE_QUERY_CALL さらに実行します。</span><span class="sxs-lookup"><span data-stu-id="53604-105">The custom RFC in turn executes the RSAQ_REMOTE_QUERY_CALL, which is a standard RFC defined in the SAP system.</span></span> <span data-ttu-id="53604-106">そのため、EXECQUERY 操作を使用することができます、前に、に対するクエリを実行して、SAP システムでカスタム RFC をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="53604-106">Hence, before you can use the EXECQUERY operation, you must install the custom RFC in the SAP system you will be running your queries against.</span></span> <span data-ttu-id="53604-107">カスタムの RFC をインストールする方法の手順については、次を参照してください。 [SAP 用データ プロバイダーのインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="53604-107">For instructions on how to install the custom RFC, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
 <span data-ttu-id="53604-108">このトピックでは、EXECQUERY 操作および EXECQUERY 操作に関連するその他の有用な情報の構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="53604-108">This topic provides information on the syntax of the EXECQUERY operation, and other useful information related to the EXECQUERY operation.</span></span>  
  
## <a name="syntax-for-an-execquery-statement"></a><span data-ttu-id="53604-109">EXECQUERY ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="53604-109">Syntax for an EXECQUERY Statement</span></span>  
 <span data-ttu-id="53604-110">次のセクションでは、に対して EXECQUERY 操作を使用するための文法仕様をについて説明します、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="53604-110">The following section describes the grammar specifications for using the EXECQUERY operation against the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
```  
EXECQUERY <QueryName> @USERGROUP='usergroup' [, @WORKSPACE='X'] [, @VARIANT='variant']   
[, @P1='<value 1>’] [, @P2='<value 2>'] ... [, @Pn = '<value n>'] [, @P1!='<value 3>'] [, @P1 > '<value 4>'] [, @P1 <= '<value 2>']   
[, NOT @P1 = '<value 2>'] [, NOT @P1 != '<value 2>'] [, NOT @P1 > '<value 2>']   
[, @P1 BETWEEN '<value 1>' AND '<value 2>'] [, NOT @P1 BETWEEN '<value 1>' AND '<value2>’]  
[OPTION 'USEORIGINALCOLUMNNAMES']  
  
```  
  
 <span data-ttu-id="53604-111">それぞれの文字の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="53604-111">where:</span></span>  
  
-   <span data-ttu-id="53604-112">**\<QueryName\>**  SAP システムで定義されたクエリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="53604-112">**\<QueryName\>** is the name of the query defined in the SAP system.</span></span>  
  
-   <span data-ttu-id="53604-113">**USERGROUP**クエリが定義されているユーザー グループを参照します。</span><span class="sxs-lookup"><span data-stu-id="53604-113">**USERGROUP** refers to the user group in which the query is defined.</span></span> <span data-ttu-id="53604-114">これは、必須のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="53604-114">This is a mandatory parameter.</span></span>  
  
-   <span data-ttu-id="53604-115">**ワークスペース**クエリが定義されているワークスペースを参照します。</span><span class="sxs-lookup"><span data-stu-id="53604-115">**WORKSPACE** refers to the workspace in which the query is defined.</span></span> <span data-ttu-id="53604-116">、SAP では、2 つのワークスペースは、Standard、およびグローバルです。</span><span class="sxs-lookup"><span data-stu-id="53604-116">In SAP, there are two workspaces—Standard and Global.</span></span> <span data-ttu-id="53604-117">標準のワークスペースを指定する空の領域を提供します。</span><span class="sxs-lookup"><span data-stu-id="53604-117">Provide an empty space to specify the Standard workspace.</span></span> <span data-ttu-id="53604-118">提供`X`グローバル ワークスペースを指定します。</span><span class="sxs-lookup"><span data-stu-id="53604-118">Provide `X` to specify the Global workspace.</span></span> <span data-ttu-id="53604-119">既定値は、空の領域です。</span><span class="sxs-lookup"><span data-stu-id="53604-119">Default is empty space.</span></span>  
  
-   <span data-ttu-id="53604-120">**VARIANT**保存されている SAP クエリの実行中に指定できる選択条件のセットを指します。</span><span class="sxs-lookup"><span data-stu-id="53604-120">**VARIANT** refers to a saved set of selection criteria that you can specify while executing an SAP query.</span></span> <span data-ttu-id="53604-121">たとえば、バリアントを使用すると、クエリの既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="53604-121">For example, you can use variants to specify default values for queries.</span></span>  
  
-   <span data-ttu-id="53604-122">**@Pn**n を指す<sup>th</sup> SAP クエリの定義でフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="53604-122">**@Pn** refers to the n<sup>th</sup> selection field in the SAP query definition.</span></span>  
  
-   <span data-ttu-id="53604-123">**USEORIGINALCOLUMNNAMES** SAP システム内に存在すると、プロバイダーが、データセットで元の列名を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="53604-123">**USEORIGINALCOLUMNNAMES** specifies whether the provider uses the original column names in the DataSet, as they exist in the SAP system.</span></span> <span data-ttu-id="53604-124">既定では、プロバイダーは、SAP クエリで定義されているフレンドリ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="53604-124">By default, the provider uses the friendly names defined in the SAP query.</span></span> <span data-ttu-id="53604-125">ただし、クエリ内でのわかりやすい名前が一意でない場合、ADO.NET クライアントはエラーをスロー、データセットからデータを読み取り中にします。</span><span class="sxs-lookup"><span data-stu-id="53604-125">However, if the friendly names within the query are not unique, the ADO.NET client will throw an error while reading the data from the DataSet.</span></span> <span data-ttu-id="53604-126">このようなシナリオである必要がありますオプションを指定する、USEORIGINALCOLUMNNAMES プロバイダーがデータセットの元の列名を使用することを示すです。</span><span class="sxs-lookup"><span data-stu-id="53604-126">In such scenarios, you must specify the USEORIGINALCOLUMNNAMES option, indicating that the provider uses the original column names in the DataSet.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="53604-127">たとえば、常に 1 つの引用符で囲まれたオプションのキーワードの値を指定する必要があります '*USEORIGINALCOLUMNNAMES*' です。</span><span class="sxs-lookup"><span data-stu-id="53604-127">You must always provide the value for the OPTION keyword within single quotes, for example, '*USEORIGINALCOLUMNNAMES*'.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53604-128">SAP クエリのパラメーターが EXECQUERY 構文に変換する方法については、次を参照してください。 [EXECQUERY コマンドにクエリ パラメーターの変換の SAP](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md)です。</span><span class="sxs-lookup"><span data-stu-id="53604-128">For information about how the parameters of an SAP Query translate into an EXECQUERY syntax, see [Translate SAP query parameters into EXECQUERY command](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).</span></span>  
  
### <a name="framing-an-execquery-syntax"></a><span data-ttu-id="53604-129">EXECQUERY 構文のフレーム化</span><span class="sxs-lookup"><span data-stu-id="53604-129">Framing an EXECQUERY Syntax</span></span>  
 <span data-ttu-id="53604-130">SAP クエリの実行に EXECQUERY 操作の構文のフレームは、SAP で定義されている各パラメーターの値を含む、SAP システムでクエリを定義する方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="53604-130">Framing syntax for an EXECQUERY operation to execute an SAP query depends on how the query is defined in the SAP system, including each parameter value defined in SAP.</span></span> <span data-ttu-id="53604-131">SAP クエリの実行に EXECQUERY 構文のフレームをする方法については、次を参照してください。 [EXECQUERY コマンドにクエリ パラメーターの変換の SAP](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md)です。</span><span class="sxs-lookup"><span data-stu-id="53604-131">For information about how to frame EXECQUERY syntax to execute an SAP query, see [Translate SAP query parameters into EXECQUERY command](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).</span></span>  
  
### <a name="additional-considerations-while-using-the-execquery-operation"></a><span data-ttu-id="53604-132">追加の考慮事項中に操作を使用して、EXECQUERY</span><span class="sxs-lookup"><span data-stu-id="53604-132">Additional Considerations While Using the EXECQUERY operation</span></span>  
 <span data-ttu-id="53604-133">このセクションでは、EXECQUERY ステートメントを使用する場合は、点に注意する必要がありますポイントを一覧表示[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="53604-133">This section lists the points that you must keep in mind when using the EXECQUERY statement with [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
-   <span data-ttu-id="53604-134">として USERGROUP、ワークスペース、およびバリアント型の指定した値を渡すには標準の SAP RFC RSAQ_REMOTE_QUERY_CALL をします。</span><span class="sxs-lookup"><span data-stu-id="53604-134">The values specified for USERGROUP, WORKSPACE, and VARIANT are passed on as-is to the standard SAP RFC, RSAQ_REMOTE_QUERY_CALL.</span></span> <span data-ttu-id="53604-135">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]はこれらのパラメーターの指定した値は検証されません。</span><span class="sxs-lookup"><span data-stu-id="53604-135">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not validate the values specified for these parameters.</span></span>  
  
-   <span data-ttu-id="53604-136">EXECQUERY 操作によって返されるすべての値では、文字列型です。</span><span class="sxs-lookup"><span data-stu-id="53604-136">All values returned by the EXECQUERY operation are of string type.</span></span>  
  
-   <span data-ttu-id="53604-137">クエリ名、ユーザー グループ、ワークスペース、およびバリアントのキーワードは、大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="53604-137">Keywords for query names, user group, workspace, and variants are not case sensitive.</span></span> <span data-ttu-id="53604-138">ただし、パラメーター名は常にある上位 caseP でなど@P1、 @P2, などです。例:</span><span class="sxs-lookup"><span data-stu-id="53604-138">However, the parameter names must always be in upper caseP such as @P1, @P2, etc. For example:</span></span>  
  
    ```  
    EXECQUERY xyz USERGROUP=’mygrp’, NOT @P1= 'somevalue'  
    ```  
  
     <span data-ttu-id="53604-139">同じです。</span><span class="sxs-lookup"><span data-stu-id="53604-139">is the same as</span></span>  
  
    ```  
    EXECQUERY xyz uSERgROUP=’mygrp’, NOT @P1= 'somevalue'  
    ```  
  
-   <span data-ttu-id="53604-140">EXECQUERY でサポートされている演算子は、>、<>、=、< =、! =、NOT、および BETWEEN です。</span><span class="sxs-lookup"><span data-stu-id="53604-140">The operators supported by the EXECQUERY are >, <, >=, <=, !=, NOT, and BETWEEN.</span></span>  
  
-   <span data-ttu-id="53604-141">EXECQUERY 操作によっては、ワイルドカード文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="53604-141">Wildcard characters are not supported by the EXECQUERY operation.</span></span> <span data-ttu-id="53604-142">たとえば、次のステートメントが予想される出力。</span><span class="sxs-lookup"><span data-stu-id="53604-142">For example, the following statement gives the expected output:</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
    ```  
  
     <span data-ttu-id="53604-143">ただし、ワイルドカード文字を使用して実行する際、同じクエリでは、エラーを示します。</span><span class="sxs-lookup"><span data-stu-id="53604-143">However, the same query when executed with a wildcard character gives an error.</span></span> <span data-ttu-id="53604-144">ワイルドカード文字の使用に注意してください **@P2**です。</span><span class="sxs-lookup"><span data-stu-id="53604-144">Notice the use of wildcard characters for **@P2**.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = '*&*'  
    ```  
  
     <span data-ttu-id="53604-145">この例では、データが見つからなかったことを示すエラーを取得可能性があります。</span><span class="sxs-lookup"><span data-stu-id="53604-145">In this example, you might get an error stating that no data was found.</span></span> <span data-ttu-id="53604-146">これは、クエリを検索するため**'\*&\*'**を文字列としてし、ワイルドカード文字としてアスタリスク (*) を考慮しません。</span><span class="sxs-lookup"><span data-stu-id="53604-146">This is because the query searches for **'\*&\*'** as a string and does not consider asterisk (*) as a wildcard character.</span></span>  
  
-   <span data-ttu-id="53604-147">必ず、YYYYMMDD の形式で日付値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53604-147">You must always specify a date values in YYYYMMDD format.</span></span>  
  
-   <span data-ttu-id="53604-148">SAP システムで定義されているバリエーションがあるクエリを実行している場合は、コマンドの一部として、バリアント型の名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="53604-148">If you are executing a query that has a variant defined in the SAP system, you can specify the name of the variant as part of the command.</span></span> <span data-ttu-id="53604-149">例:</span><span class="sxs-lookup"><span data-stu-id="53604-149">For example:</span></span>  
  
    ```  
    EXECQUERY myquery @usergroup='mygroup',@variant = 'variant1'  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="53604-150">SAP システムでクエリの既定のバリエーションが定義されている場合は、バリアントの名前を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="53604-150">You do not need to specify a variant name if a default variant is defined for the query in the SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53604-151">参照</span><span class="sxs-lookup"><span data-stu-id="53604-151">See Also</span></span>  
 [<span data-ttu-id="53604-152">.NET Framework Data Provider for mySAP Business Suite の使用</span><span class="sxs-lookup"><span data-stu-id="53604-152">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)