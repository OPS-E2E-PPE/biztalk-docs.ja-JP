---
title: "Data Provider 用 SAP に関する問題のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, troubleshooting
- troubleshooting, Data Provider for SAP
ms.assetid: 6fe9baed-0404-4f15-b76e-88cc11c5ff46
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba61b75f95fad429c70da42479f22a32fa4e5a65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-issues-with-the-data-provider-for-sap"></a><span data-ttu-id="678e0-102">Data Provider 用 SAP に関する問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="678e0-102">Troubleshoot Issues with the Data Provider for SAP</span></span>
<span data-ttu-id="678e0-103">このセクションで説明を使用する場合に発生する可能性のある操作のエラーを解決するのには、トラブルシューティングの手法を使用して[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="678e0-103">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span>  
  
##  <span data-ttu-id="678e0-104"><a name="BKMK_SAPUnknownParam"></a>SAP 用データ プロバイダーを使用して不明なパラメーター エラー</span><span class="sxs-lookup"><span data-stu-id="678e0-104"><a name="BKMK_SAPUnknownParam"></a> Unknown Parameter error using the Data Provider for SAP</span></span>  
 <span data-ttu-id="678e0-105">**問題**</span><span class="sxs-lookup"><span data-stu-id="678e0-105">**Problem**</span></span>  
  
 <span data-ttu-id="678e0-106">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="678e0-106">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] gives the following error:</span></span>  
  
```  
Microsoft.Data.SAPClient.SAPException: Failed to retrieve data from SAP server --- > Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Unknown Parameter OUT_ZDATATABLE.  
```  
  
 <span data-ttu-id="678e0-107">**原因**</span><span class="sxs-lookup"><span data-stu-id="678e0-107">**Cause**</span></span>  
  
 <span data-ttu-id="678e0-108">カスタム RFC、SAP システムにインストールされている Z_EXTRACT_DATA_OO が最新ではないです。</span><span class="sxs-lookup"><span data-stu-id="678e0-108">The custom RFC, Z_EXTRACT_DATA_OO, installed in your SAP system is not the latest.</span></span> <span data-ttu-id="678e0-109">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] Z_EXTRACT_DATA_OO、カスタムの RFC を使用して SAP テーブルに対する SELECT 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="678e0-109">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses a custom RFC, Z_EXTRACT_DATA_OO, to perform SELECT operations on the SAP table.</span></span>  
  
 <span data-ttu-id="678e0-110">**解決策**</span><span class="sxs-lookup"><span data-stu-id="678e0-110">**Resolution**</span></span>  
  
 <span data-ttu-id="678e0-111">カスタム RFC を最新のバージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="678e0-111">You must update the custom RFC to the latest available version.</span></span> <span data-ttu-id="678e0-112">この RFC、Z_EXTRACT_DATA_OO は、adapterpacknoversion 使用できます。</span><span class="sxs-lookup"><span data-stu-id="678e0-112">This RFC, Z_EXTRACT_DATA_OO, is available with the adapterpacknoversion.</span></span> <span data-ttu-id="678e0-113">インストールおよびカスタムの RFC をアンインストールする方法の詳細については、次を参照してください。 [SAP 用データ プロバイダーのインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="678e0-113">For more information about how to install and uninstall the custom RFC, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>
  
##  <span data-ttu-id="678e0-114"><a name="BKMK_SAPOOM"></a>SAP テーブルからデータを選択すると、メモリ例外外</span><span class="sxs-lookup"><span data-stu-id="678e0-114"><a name="BKMK_SAPOOM"></a> Out of memory exceptions when selecting data from an SAP table</span></span>  
 <span data-ttu-id="678e0-115">**問題**</span><span class="sxs-lookup"><span data-stu-id="678e0-115">**Problem**</span></span>  
  
 <span data-ttu-id="678e0-116">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムからデータを選択するときに、メモリ不足の例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="678e0-116">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] throws an out of memory exception when selecting data from an SAP system.</span></span>  
  
 <span data-ttu-id="678e0-117">**原因**</span><span class="sxs-lookup"><span data-stu-id="678e0-117">**Cause**</span></span>  
  
 <span data-ttu-id="678e0-118">既定では、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]一度に行数は 10,000 行を取得します。</span><span class="sxs-lookup"><span data-stu-id="678e0-118">By default, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] retrieves 10,000 rows at a time.</span></span> <span data-ttu-id="678e0-119">また、SAP システムから取得された行の各バッチは、メモリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="678e0-119">Also, each batch of rows retrieved from the SAP system is stored in the memory.</span></span> <span data-ttu-id="678e0-120">だから</span><span class="sxs-lookup"><span data-stu-id="678e0-120">So,</span></span>  
  
-   <span data-ttu-id="678e0-121">データの取得元となるテーブルに多数の行が含まれている場合、または</span><span class="sxs-lookup"><span data-stu-id="678e0-121">If the table from which data is being retrieved contains a large number of rows, or</span></span>  
  
-   <span data-ttu-id="678e0-122">テーブルに大量のメモリを消費するデータ型の列が含まれている場合</span><span class="sxs-lookup"><span data-stu-id="678e0-122">If the table contains columns of data types that consume a significant amount of memory,</span></span>  
  
 <span data-ttu-id="678e0-123">によるメモリ消費、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]が大幅に増加し、メモリ不足の例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="678e0-123">The memory consumption by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] increases significantly and may result in an out of memory exception.</span></span>  
  
 <span data-ttu-id="678e0-124">**解決策**</span><span class="sxs-lookup"><span data-stu-id="678e0-124">**Resolution**</span></span>  
  
 <span data-ttu-id="678e0-125">SAP システムから取得された行の最大数を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="678e0-125">You can change the maximum number of rows retrieved from the SAP system.</span></span> <span data-ttu-id="678e0-126">SELECT ステートメントで 'batchsize' オプションを指定することによって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="678e0-126">You can do so by specifying a 'batchsize' option with the SELECT statement.</span></span> <span data-ttu-id="678e0-127">例:</span><span class="sxs-lookup"><span data-stu-id="678e0-127">For example:</span></span>  
  
```  
SELECT * FROM <tablename> OPTION 'batchsize 1000'  
```  
  
 <span data-ttu-id="678e0-128">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]今すぐ、一度に 1000 を超える行が取得され、したがって大量のメモリを消費しません。</span><span class="sxs-lookup"><span data-stu-id="678e0-128">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] now retrieves only 1000 rows at a time and hence does not consume large amount of memory.</span></span>  
  
##  <span data-ttu-id="678e0-129"><a name="BKMK_SAPQueryExcep"></a>パラメーターと日付の値を取得するクエリの実行中に例外</span><span class="sxs-lookup"><span data-stu-id="678e0-129"><a name="BKMK_SAPQueryExcep"></a> Exception while executing a query that takes parameters with date values</span></span>  
 <span data-ttu-id="678e0-130">**問題**</span><span class="sxs-lookup"><span data-stu-id="678e0-130">**Problem**</span></span>  
  
 <span data-ttu-id="678e0-131">EXECQUERY がのコマンドを日付の値をとるパラメーターを使用してクエリを実行するときに、次の例外を取得します。</span><span class="sxs-lookup"><span data-stu-id="678e0-131">You get the following exception when you execute a query using the EXECQUERY command that has a parameter which takes a date value:</span></span>  
  
```  
ErrorCode=RFC_SYS_EXCEPTION. ErrorGroup=RFC_ERROR_SYSTEM_FAILURE.   
SapErrorMessage=Enter date in the format __.__.____.  
```  
  
 <span data-ttu-id="678e0-132">**原因**</span><span class="sxs-lookup"><span data-stu-id="678e0-132">**Cause**</span></span>  
  
 <span data-ttu-id="678e0-133">EXECQUERY コマンドを使用してクエリを実行するときに、YYYYMMDD の形式で日付の値を必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="678e0-133">When executing queries using the EXECQUERY command, you must always specify date values in YYYYMMDD format.</span></span>  
  
 <span data-ttu-id="678e0-134">**解決策**</span><span class="sxs-lookup"><span data-stu-id="678e0-134">**Resolution**</span></span>  
  
 <span data-ttu-id="678e0-135">YYYYMMDD 形式で日付の値を指定することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="678e0-135">Make sure you specify date values in YYYYMMDD format.</span></span> <span data-ttu-id="678e0-136">例:</span><span class="sxs-lookup"><span data-stu-id="678e0-136">For example:</span></span>  
  
```  
EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1='20080606'  
```  
  
##  <span data-ttu-id="678e0-137"><a name="BKMK_SAPNOVARIANT"></a>EXECQUERY コマンドを使用してクエリを実行する NO_VARIANT 例外</span><span class="sxs-lookup"><span data-stu-id="678e0-137"><a name="BKMK_SAPNOVARIANT"></a> NO_VARIANT exception executing queries using the EXECQUERY command</span></span>  
 <span data-ttu-id="678e0-138">**問題**</span><span class="sxs-lookup"><span data-stu-id="678e0-138">**Problem**</span></span>  
  
 <span data-ttu-id="678e0-139">EXECQUERY コマンドを使用してクエリを実行するときに、次の例外を取得します。</span><span class="sxs-lookup"><span data-stu-id="678e0-139">You get the following exception when you execute a query using the EXECQUERY command:</span></span>  
  
```  
Exception: Details: ErrorCode=RFC_EXCEPTION. ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage=NO_VARIANT.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: <RFC name>  
```  
  
 <span data-ttu-id="678e0-140">**原因**</span><span class="sxs-lookup"><span data-stu-id="678e0-140">**Cause**</span></span>  
  
 <span data-ttu-id="678e0-141">この例外の 2 つの可能性のある原因ことができます。</span><span class="sxs-lookup"><span data-stu-id="678e0-141">There can be two probable causes for this exception:</span></span>  
  
1.  <span data-ttu-id="678e0-142">実行しようとしているクエリは、SAP システムで定義されているバリエーションにあります。</span><span class="sxs-lookup"><span data-stu-id="678e0-142">The query you are trying to execute has variants defined in the SAP system.</span></span> <span data-ttu-id="678e0-143">バリアントは、保存されている SAP クエリの実行中に指定できる選択条件のセットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="678e0-143">Variants refer to a saved set of selection criteria that you can specify while executing an SAP query.</span></span> <span data-ttu-id="678e0-144">たとえば、バリアントを使用すると、クエリの既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="678e0-144">For example, you can use variants to specify default values for queries.</span></span>  
  
2.  <span data-ttu-id="678e0-145">どちらを実行しようとしているクエリ バリアント型が定義されていることも、パラメーター値を渡すことが求められます。</span><span class="sxs-lookup"><span data-stu-id="678e0-145">The query you are trying to execute neither has a variant defined nor it expects a parameter value to be passed.</span></span>  
  
 <span data-ttu-id="678e0-146">**解決策**</span><span class="sxs-lookup"><span data-stu-id="678e0-146">**Resolution**</span></span>  
  
1.  <span data-ttu-id="678e0-147">1 の理由で、クエリに関連付けられているバリアントの名前を指定するになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="678e0-147">For reason 1, make sure you specify the name of the variant associated with the query.</span></span> <span data-ttu-id="678e0-148">例:</span><span class="sxs-lookup"><span data-stu-id="678e0-148">For example:</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant =  ‘variant1’  
    ```  
  
2.  <span data-ttu-id="678e0-149">2 の理由で、クエリ コマンドを指定する際に、ダミーのパラメーターの名前と値を指定するになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="678e0-149">For reason 2, make sure you provide a dummy parameter name and value while specifying the query command.</span></span> <span data-ttu-id="678e0-150">たとえば、"myquery"クエリに実行する任意のパラメーターが必要としない場合、として EXECQUERY コマンドを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="678e0-150">For example, if “myquery” query does not require any parameter to execute, the EXECQUERY command must be specified as:</span></span>  
  
    ```  
    EXECQUERY myquery @usergroup='mygroup',@P1 = 'dummy_value'  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="678e0-151">参照</span><span class="sxs-lookup"><span data-stu-id="678e0-151">See Also</span></span>  
[<span data-ttu-id="678e0-152">SAP アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="678e0-152">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)