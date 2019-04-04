---
title: SAP に EXECQUERY ステートメントの構文 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 99bd7fbb-64f2-4327-a8ae-ccb574e56150
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccf479438a5b0960a66b35ef7946df63d088284b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982019"
---
# <a name="syntax-for-an-execquery-statement-in-sap"></a><span data-ttu-id="f7a44-102">SAP に EXECQUERY ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="f7a44-102">Syntax for an EXECQUERY Statement in SAP</span></span>
<span data-ttu-id="f7a44-103">SAP GUI を使用すると、グラフィカルに表示するクエリ、列および並べ替え順序など、結果セットに含めるテーブルを選択してクエリを作成します。[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] ADO.NET アプリケーションからユーザーが SAP システムで定義されているクエリの実行に使用できる EXECQUERY 操作を提供することでこのようなクエリを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f7a44-103">You can use the SAP GUI to create queries by graphically selecting the tables you want to query, the columns and sort order you want included in the result set, etc. The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] enables users to execute such queries from an ADO.NET application by providing an EXECQUERY operation that users can use to execute a query defined in the SAP system.</span></span>  
  
 <span data-ttu-id="f7a44-104">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]カスタム RFC Z_EXECUTE_SAP_QUERY を使用して、SAP システムで定義済みのクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-104">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses a custom RFC Z_EXECUTE_SAP_QUERY to execute the pre-defined queries in the SAP system.</span></span> <span data-ttu-id="f7a44-105">カスタム RFC には、これは、標準の SAP システムで定義されている RFC、RSAQ_REMOTE_QUERY_CALL さらに実行します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-105">The custom RFC in turn executes the RSAQ_REMOTE_QUERY_CALL, which is a standard RFC defined in the SAP system.</span></span> <span data-ttu-id="f7a44-106">そのため、EXECQUERY 操作を使用する前に、に対するクエリを実行する SAP システムでカスタム RFC をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7a44-106">Hence, before you can use the EXECQUERY operation, you must install the custom RFC in the SAP system you will be running your queries against.</span></span> <span data-ttu-id="f7a44-107">カスタム RFC をインストールする方法の手順については、[Data Provider for SAP のインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7a44-107">For instructions on how to install the custom RFC, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
 <span data-ttu-id="f7a44-108">このトピックでは、EXECQUERY 操作、および EXECQUERY 操作に関連するその他の有用な情報の構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-108">This topic provides information on the syntax of the EXECQUERY operation, and other useful information related to the EXECQUERY operation.</span></span>  
  
## <a name="syntax-for-an-execquery-statement"></a><span data-ttu-id="f7a44-109">EXECQUERY ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="f7a44-109">Syntax for an EXECQUERY Statement</span></span>  
 <span data-ttu-id="f7a44-110">次のセクションの説明に対する EXECQUERY 操作を使用して文法の仕様、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-110">The following section describes the grammar specifications for using the EXECQUERY operation against the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
```  
EXECQUERY <QueryName> @USERGROUP='usergroup' [, @WORKSPACE='X'] [, @VARIANT='variant']   
[, @P1='<value 1>’] [, @P2='<value 2>'] ... [, @Pn = '<value n>'] [, @P1!='<value 3>'] [, @P1 > '<value 4>'] [, @P1 <= '<value 2>']   
[, NOT @P1 = '<value 2>'] [, NOT @P1 != '<value 2>'] [, NOT @P1 > '<value 2>']   
[, @P1 BETWEEN '<value 1>' AND '<value 2>'] [, NOT @P1 BETWEEN '<value 1>' AND '<value2>’]  
[OPTION 'USEORIGINALCOLUMNNAMES']  
  
```  
  
 <span data-ttu-id="f7a44-111">それぞれの文字の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f7a44-111">where:</span></span>  
  
- <span data-ttu-id="f7a44-112">**\<QueryName\>**  SAP システムで定義されているクエリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-112">**\<QueryName\>** is the name of the query defined in the SAP system.</span></span>  
  
- <span data-ttu-id="f7a44-113">**USERGROUP**は、クエリが定義されているユーザー グループを指します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-113">**USERGROUP** refers to the user group in which the query is defined.</span></span> <span data-ttu-id="f7a44-114">これは、必須パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="f7a44-114">This is a mandatory parameter.</span></span>  
  
- <span data-ttu-id="f7a44-115">**ワークスペース**クエリが定義されているワークスペースを参照します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-115">**WORKSPACE** refers to the workspace in which the query is defined.</span></span> <span data-ttu-id="f7a44-116">Sap では、2 つのワークスペース: Standard、およびグローバルです。</span><span class="sxs-lookup"><span data-stu-id="f7a44-116">In SAP, there are two workspaces—Standard and Global.</span></span> <span data-ttu-id="f7a44-117">Standard ワークスペースを指定する空の領域を提供します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-117">Provide an empty space to specify the Standard workspace.</span></span> <span data-ttu-id="f7a44-118">提供`X`グローバルのワークスペースを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-118">Provide `X` to specify the Global workspace.</span></span> <span data-ttu-id="f7a44-119">既定値は、空の領域です。</span><span class="sxs-lookup"><span data-stu-id="f7a44-119">Default is empty space.</span></span>  
  
- <span data-ttu-id="f7a44-120">**VARIANT**と SAP クエリの実行中に指定できる選択条件の保存されているセットを指します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-120">**VARIANT** refers to a saved set of selection criteria that you can specify while executing an SAP query.</span></span> <span data-ttu-id="f7a44-121">たとえば、バリアントを使用すると、クエリの既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-121">For example, you can use variants to specify default values for queries.</span></span>  
  
- <span data-ttu-id="f7a44-122"><strong>@Pn</strong> n を指す<sup>th</sup> SAP クエリの定義でフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-122"><strong>@Pn</strong> refers to the n<sup>th</sup> selection field in the SAP query definition.</span></span>  
  
- <span data-ttu-id="f7a44-123">**USEORIGINALCOLUMNNAMES** SAP システム内に存在するプロバイダーは、データセットの元の列名を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-123">**USEORIGINALCOLUMNNAMES** specifies whether the provider uses the original column names in the DataSet, as they exist in the SAP system.</span></span> <span data-ttu-id="f7a44-124">既定では、プロバイダーは、SAP クエリで定義されているフレンドリ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-124">By default, the provider uses the friendly names defined in the SAP query.</span></span> <span data-ttu-id="f7a44-125">ただし、そのクエリ内での表示名が一意でない場合、ADO.NET クライアントは、データセットからデータを読み取り中にエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="f7a44-125">However, if the friendly names within the query are not unique, the ADO.NET client will throw an error while reading the data from the DataSet.</span></span> <span data-ttu-id="f7a44-126">このようなシナリオでする必要がありますオプションを指定する USEORIGINALCOLUMNNAMES、プロバイダーがデータセットの元の列名を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-126">In such scenarios, you must specify the USEORIGINALCOLUMNNAMES option, indicating that the provider uses the original column names in the DataSet.</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="f7a44-127">たとえば、常に単一引用符で囲まれたオプションのキーワードの値を指定する必要があります '*USEORIGINALCOLUMNNAMES*'。</span><span class="sxs-lookup"><span data-stu-id="f7a44-127">You must always provide the value for the OPTION keyword within single quotes, for example, '*USEORIGINALCOLUMNNAMES*'.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7a44-128">SAP クエリのパラメーターを EXECQUERY 構文に変換する方法については、[変換 SAP クエリのパラメーターを EXECQUERY コマンドに](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7a44-128">For information about how the parameters of an SAP Query translate into an EXECQUERY syntax, see [Translate SAP query parameters into EXECQUERY command](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).</span></span>  
  
### <a name="framing-an-execquery-syntax"></a><span data-ttu-id="f7a44-129">フレーム、EXECQUERY 構文</span><span class="sxs-lookup"><span data-stu-id="f7a44-129">Framing an EXECQUERY Syntax</span></span>  
 <span data-ttu-id="f7a44-130">SAP クエリを実行するための EXECQUERY 操作の構文のフレーム化は、SAP で定義されている各パラメーターの値を含む、SAP システムでクエリを定義する方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f7a44-130">Framing syntax for an EXECQUERY operation to execute an SAP query depends on how the query is defined in the SAP system, including each parameter value defined in SAP.</span></span> <span data-ttu-id="f7a44-131">フレームの EXECQUERY の構文を SAP クエリを実行する方法については、[変換 SAP クエリのパラメーターを EXECQUERY コマンドに](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7a44-131">For information about how to frame EXECQUERY syntax to execute an SAP query, see [Translate SAP query parameters into EXECQUERY command](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).</span></span>  
  
### <a name="additional-considerations-while-using-the-execquery-operation"></a><span data-ttu-id="f7a44-132">追加の考慮事項、操作を使用して、EXECQUERY</span><span class="sxs-lookup"><span data-stu-id="f7a44-132">Additional Considerations While Using the EXECQUERY operation</span></span>  
 <span data-ttu-id="f7a44-133">このセクションに一覧表示されたポイントを指定して EXECQUERY ステートメントを使用する場合、点に注意する必要があります[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-133">This section lists the points that you must keep in mind when using the EXECQUERY statement with [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
- <span data-ttu-id="f7a44-134">としてユーザー グループ、ワークスペース、およびバリアントの値を渡すには標準の SAP RFC RSAQ_REMOTE_QUERY_CALL をします。</span><span class="sxs-lookup"><span data-stu-id="f7a44-134">The values specified for USERGROUP, WORKSPACE, and VARIANT are passed on as-is to the standard SAP RFC, RSAQ_REMOTE_QUERY_CALL.</span></span> <span data-ttu-id="f7a44-135">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]はこれらのパラメーターに指定された値は検証されません。</span><span class="sxs-lookup"><span data-stu-id="f7a44-135">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not validate the values specified for these parameters.</span></span>  
  
- <span data-ttu-id="f7a44-136">EXECQUERY 操作によって返されるすべての値では、文字列型です。</span><span class="sxs-lookup"><span data-stu-id="f7a44-136">All values returned by the EXECQUERY operation are of string type.</span></span>  
  
- <span data-ttu-id="f7a44-137">クエリ名、ユーザー グループ、ワークスペース、およびバリアントのキーワードは大文字小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="f7a44-137">Keywords for query names, user group, workspace, and variants are not case sensitive.</span></span> <span data-ttu-id="f7a44-138">ただし、パラメーター名は常上限 caseP など@P1、@P2など。以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-138">However, the parameter names must always be in upper caseP such as @P1, @P2, etc. For example:</span></span>  
  
  ```  
  EXECQUERY xyz USERGROUP=’mygrp’, NOT @P1= 'somevalue'  
  ```  
  
   <span data-ttu-id="f7a44-139">同じです。</span><span class="sxs-lookup"><span data-stu-id="f7a44-139">is the same as</span></span>  
  
  ```  
  EXECQUERY xyz uSERgROUP=’mygrp’, NOT @P1= 'somevalue'  
  ```  
  
- <span data-ttu-id="f7a44-140">EXECQUERY でサポートされている演算子は、>、<>、=、< =、! =、NOT、BETWEEN とします。</span><span class="sxs-lookup"><span data-stu-id="f7a44-140">The operators supported by the EXECQUERY are >, <, >=, <=, !=, NOT, and BETWEEN.</span></span>  
  
- <span data-ttu-id="f7a44-141">ワイルドカード文字は EXECQUERY 操作ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f7a44-141">Wildcard characters are not supported by the EXECQUERY operation.</span></span> <span data-ttu-id="f7a44-142">たとえば、次のステートメント、予想される出力されます。</span><span class="sxs-lookup"><span data-stu-id="f7a44-142">For example, the following statement gives the expected output:</span></span>  
  
  ```  
  EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
  ```  
  
   <span data-ttu-id="f7a44-143">ただし、ワイルドカード文字で実行されると、同じクエリでは、エラーを示します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-143">However, the same query when executed with a wildcard character gives an error.</span></span> <span data-ttu-id="f7a44-144">用のワイルドカード文字の使用に注意してください <strong>@P2</strong>します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-144">Notice the use of wildcard characters for <strong>@P2</strong>.</span></span>  
  
  ```  
  EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = '*&*'  
  ```  
  
   <span data-ttu-id="f7a44-145">この例では、データが見つからなかったことを示すエラーを取得可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f7a44-145">In this example, you might get an error stating that no data was found.</span></span> <span data-ttu-id="f7a44-146">これは、クエリを検索するため **'\*&\*'** を文字列としてされ、ワイルドカード文字としてアスタリスク (\*) は考慮されません。</span><span class="sxs-lookup"><span data-stu-id="f7a44-146">This is because the query searches for **'\*&\*'** as a string and does not consider asterisk (\*) as a wildcard character.</span></span>  
  
- <span data-ttu-id="f7a44-147">常に、YYYYMMDD の形式で日付値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7a44-147">You must always specify a date values in YYYYMMDD format.</span></span>  
  
- <span data-ttu-id="f7a44-148">SAP システムで定義されたバリアントがあるクエリを実行している場合は、コマンドの一部としてバリアントの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f7a44-148">If you are executing a query that has a variant defined in the SAP system, you can specify the name of the variant as part of the command.</span></span> <span data-ttu-id="f7a44-149">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-149">For example:</span></span>  
  
  ```  
  EXECQUERY myquery @usergroup='mygroup',@variant = 'variant1'  
  ```  
  
  > [!NOTE]
  >  <span data-ttu-id="f7a44-150">SAP システムでクエリの既定のバリエーションが定義されている場合は、バリアントの名前を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f7a44-150">You do not need to specify a variant name if a default variant is defined for the query in the SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a44-151">参照</span><span class="sxs-lookup"><span data-stu-id="f7a44-151">See Also</span></span>  
 [<span data-ttu-id="f7a44-152">.NET Framework Data Provider for mySAP Business Suite の使用</span><span class="sxs-lookup"><span data-stu-id="f7a44-152">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)