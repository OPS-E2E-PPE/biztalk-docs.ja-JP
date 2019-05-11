---
title: Data Provider for SAP に関する問題のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, troubleshooting
- troubleshooting, Data Provider for SAP
ms.assetid: 6fe9baed-0404-4f15-b76e-88cc11c5ff46
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e0d5406ceb728d28906665fff262edab1623e3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372434"
---
# <a name="troubleshoot-issues-with-the-data-provider-for-sap"></a><span data-ttu-id="28a73-102">Data Provider for SAP に関する問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="28a73-102">Troubleshoot Issues with the Data Provider for SAP</span></span>
<span data-ttu-id="28a73-103">このセクションを使用する場合に発生する可能性のある操作のエラーを解決するのには、トラブルシューティングの手法を使用して説明します[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="28a73-103">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span>  
  
##  <a name="BKMK_SAPUnknownParam"></a> <span data-ttu-id="28a73-104">SAP 用データ プロバイダーを使用して、不明なパラメーター エラー</span><span class="sxs-lookup"><span data-stu-id="28a73-104">Unknown Parameter error using the Data Provider for SAP</span></span>  
 <span data-ttu-id="28a73-105">**問題**</span><span class="sxs-lookup"><span data-stu-id="28a73-105">**Problem**</span></span>  
  
 <span data-ttu-id="28a73-106">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="28a73-106">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] gives the following error:</span></span>  
  
```  
Microsoft.Data.SAPClient.SAPException: Failed to retrieve data from SAP server --- > Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Unknown Parameter OUT_ZDATATABLE.  
```  
  
 <span data-ttu-id="28a73-107">**原因**</span><span class="sxs-lookup"><span data-stu-id="28a73-107">**Cause**</span></span>  
  
 <span data-ttu-id="28a73-108">カスタム RFC、SAP システムにインストールされている Z_EXTRACT_DATA_OO が最新ではありません。</span><span class="sxs-lookup"><span data-stu-id="28a73-108">The custom RFC, Z_EXTRACT_DATA_OO, installed in your SAP system is not the latest.</span></span> <span data-ttu-id="28a73-109">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] Z_EXTRACT_DATA_OO、カスタムの RFC を使用して SAP テーブルに対する SELECT 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="28a73-109">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses a custom RFC, Z_EXTRACT_DATA_OO, to perform SELECT operations on the SAP table.</span></span>  
  
 <span data-ttu-id="28a73-110">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="28a73-110">**Resolution**</span></span>  
  
 <span data-ttu-id="28a73-111">カスタム RFC を最新のバージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28a73-111">You must update the custom RFC to the latest available version.</span></span> <span data-ttu-id="28a73-112">この RFC、Z_EXTRACT_DATA_OO は、adapterpacknoversion 利用できます。</span><span class="sxs-lookup"><span data-stu-id="28a73-112">This RFC, Z_EXTRACT_DATA_OO, is available with the adapterpacknoversion.</span></span> <span data-ttu-id="28a73-113">インストールおよびカスタム RFC をアンインストールする方法の詳細については、次を参照してください。 [Data Provider for SAP のインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="28a73-113">For more information about how to install and uninstall the custom RFC, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>
  
##  <a name="BKMK_SAPOOM"></a> <span data-ttu-id="28a73-114">メモリ不足例外が SAP テーブルからデータを選択するときに</span><span class="sxs-lookup"><span data-stu-id="28a73-114">Out of memory exceptions when selecting data from an SAP table</span></span>  
 <span data-ttu-id="28a73-115">**問題**</span><span class="sxs-lookup"><span data-stu-id="28a73-115">**Problem**</span></span>  
  
 <span data-ttu-id="28a73-116">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムからデータを選択するときに、メモリ不足の例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="28a73-116">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] throws an out of memory exception when selecting data from an SAP system.</span></span>  
  
 <span data-ttu-id="28a73-117">**原因**</span><span class="sxs-lookup"><span data-stu-id="28a73-117">**Cause**</span></span>  
  
 <span data-ttu-id="28a73-118">既定で、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]一度に 10,000 行を取得します。</span><span class="sxs-lookup"><span data-stu-id="28a73-118">By default, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] retrieves 10,000 rows at a time.</span></span> <span data-ttu-id="28a73-119">また、SAP システムから取得される行の各バッチは、メモリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="28a73-119">Also, each batch of rows retrieved from the SAP system is stored in the memory.</span></span> <span data-ttu-id="28a73-120">だから</span><span class="sxs-lookup"><span data-stu-id="28a73-120">So,</span></span>  
  
- <span data-ttu-id="28a73-121">データの取得元となるテーブルに多数の行が含まれている場合、または</span><span class="sxs-lookup"><span data-stu-id="28a73-121">If the table from which data is being retrieved contains a large number of rows, or</span></span>  
  
- <span data-ttu-id="28a73-122">テーブルに大量のメモリを消費するデータ型の列が含まれている場合</span><span class="sxs-lookup"><span data-stu-id="28a73-122">If the table contains columns of data types that consume a significant amount of memory,</span></span>  
  
  <span data-ttu-id="28a73-123">によるメモリ消費量、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]が大幅に増えるし、メモリ不足の例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="28a73-123">The memory consumption by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] increases significantly and may result in an out of memory exception.</span></span>  
  
  <span data-ttu-id="28a73-124">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="28a73-124">**Resolution**</span></span>  
  
  <span data-ttu-id="28a73-125">SAP システムから取得される行の最大数を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="28a73-125">You can change the maximum number of rows retrieved from the SAP system.</span></span> <span data-ttu-id="28a73-126">SELECT ステートメントで 'batchsize' オプションを指定することによって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="28a73-126">You can do so by specifying a 'batchsize' option with the SELECT statement.</span></span> <span data-ttu-id="28a73-127">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="28a73-127">For example:</span></span>  
  
```  
SELECT * FROM <tablename> OPTION 'batchsize 1000'  
```  
  
 <span data-ttu-id="28a73-128">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]ようになりました、一度に 1000 を超える行が取得され、そのため大量のメモリを消費しません。</span><span class="sxs-lookup"><span data-stu-id="28a73-128">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] now retrieves only 1000 rows at a time and hence does not consume large amount of memory.</span></span>  
  
##  <a name="BKMK_SAPQueryExcep"></a> <span data-ttu-id="28a73-129">日付値を持つパラメーターを取得するクエリの実行中に例外</span><span class="sxs-lookup"><span data-stu-id="28a73-129">Exception while executing a query that takes parameters with date values</span></span>  
 <span data-ttu-id="28a73-130">**問題**</span><span class="sxs-lookup"><span data-stu-id="28a73-130">**Problem**</span></span>  
  
 <span data-ttu-id="28a73-131">日付の値をとるパラメーターを持つ EXECQUERY コマンドを使用してクエリを実行するときに、次の例外を取得します。</span><span class="sxs-lookup"><span data-stu-id="28a73-131">You get the following exception when you execute a query using the EXECQUERY command that has a parameter which takes a date value:</span></span>  
  
```  
ErrorCode=RFC_SYS_EXCEPTION. ErrorGroup=RFC_ERROR_SYSTEM_FAILURE.   
SapErrorMessage=Enter date in the format __.__.____.  
```  
  
 <span data-ttu-id="28a73-132">**原因**</span><span class="sxs-lookup"><span data-stu-id="28a73-132">**Cause**</span></span>  
  
 <span data-ttu-id="28a73-133">EXECQUERY コマンドを使用してクエリを実行するときに、YYYYMMDD の形式で日付の値を常に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28a73-133">When executing queries using the EXECQUERY command, you must always specify date values in YYYYMMDD format.</span></span>  
  
 <span data-ttu-id="28a73-134">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="28a73-134">**Resolution**</span></span>  
  
 <span data-ttu-id="28a73-135">YYYYMMDD の形式で日付値を指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="28a73-135">Make sure you specify date values in YYYYMMDD format.</span></span> <span data-ttu-id="28a73-136">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="28a73-136">For example:</span></span>  
  
```  
EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1='20080606'  
```  
  
##  <a name="BKMK_SAPNOVARIANT"></a> <span data-ttu-id="28a73-137">EXECQUERY コマンドを使用してクエリを実行する NO_VARIANT 例外</span><span class="sxs-lookup"><span data-stu-id="28a73-137">NO_VARIANT exception executing queries using the EXECQUERY command</span></span>  
 <span data-ttu-id="28a73-138">**問題**</span><span class="sxs-lookup"><span data-stu-id="28a73-138">**Problem**</span></span>  
  
 <span data-ttu-id="28a73-139">EXECQUERY コマンドを使用してクエリを実行するときに、次の例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="28a73-139">You get the following exception when you execute a query using the EXECQUERY command:</span></span>  
  
```  
Exception: Details: ErrorCode=RFC_EXCEPTION. ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage=NO_VARIANT.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: <RFC name>  
```  
  
 <span data-ttu-id="28a73-140">**原因**</span><span class="sxs-lookup"><span data-stu-id="28a73-140">**Cause**</span></span>  
  
 <span data-ttu-id="28a73-141">この例外の 2 つの考えられる原因があります。</span><span class="sxs-lookup"><span data-stu-id="28a73-141">There can be two probable causes for this exception:</span></span>  
  
1. <span data-ttu-id="28a73-142">実行しようとしているクエリでは、SAP システムで定義されているバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="28a73-142">The query you are trying to execute has variants defined in the SAP system.</span></span> <span data-ttu-id="28a73-143">バリアントは、保存された一連の SAP クエリの実行中に指定できる選択条件を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28a73-143">Variants refer to a saved set of selection criteria that you can specify while executing an SAP query.</span></span> <span data-ttu-id="28a73-144">たとえば、バリアントを使用すると、クエリの既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="28a73-144">For example, you can use variants to specify default values for queries.</span></span>  
  
2. <span data-ttu-id="28a73-145">どちらを実行しようとしているクエリが定義されているバリアントも渡されるパラメーターの値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="28a73-145">The query you are trying to execute neither has a variant defined nor it expects a parameter value to be passed.</span></span>  
  
   <span data-ttu-id="28a73-146">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="28a73-146">**Resolution**</span></span>  
  
3. <span data-ttu-id="28a73-147">1 の理由でクエリに関連付けられているバリアントの名前を指定していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="28a73-147">For reason 1, make sure you specify the name of the variant associated with the query.</span></span> <span data-ttu-id="28a73-148">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="28a73-148">For example:</span></span>  
  
   ```  
   EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant =  ‘variant1’  
   ```  
  
4. <span data-ttu-id="28a73-149">2 の理由で、クエリ コマンドを指定するときに、ダミーのパラメーターの名前と値を指定するを確認します。</span><span class="sxs-lookup"><span data-stu-id="28a73-149">For reason 2, make sure you provide a dummy parameter name and value while specifying the query command.</span></span> <span data-ttu-id="28a73-150">たとえば、"myquery"クエリに実行する任意のパラメーターが必要としない場合、EXECQUERY コマンドとして指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28a73-150">For example, if “myquery” query does not require any parameter to execute, the EXECQUERY command must be specified as:</span></span>  
  
   ```  
   EXECQUERY myquery @usergroup='mygroup',@P1 = 'dummy_value'  
   ```  
  
## <a name="see-also"></a><span data-ttu-id="28a73-151">参照</span><span class="sxs-lookup"><span data-stu-id="28a73-151">See Also</span></span>  
[<span data-ttu-id="28a73-152">SAP アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="28a73-152">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)