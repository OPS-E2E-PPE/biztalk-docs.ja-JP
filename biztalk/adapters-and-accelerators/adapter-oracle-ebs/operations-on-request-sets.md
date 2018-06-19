---
title: 要求のセットに対する操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0537354d-821e-4cf9-a4d1-f4e7d1643df9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8051a94df28df4090f78287070c5143e6f866ed7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217298"
---
# <a name="operations-on-request-sets"></a><span data-ttu-id="2c655-102">要求のセットに対する操作</span><span class="sxs-lookup"><span data-stu-id="2c655-102">Operations on Request Sets</span></span>
<span data-ttu-id="2c655-103">Oracle E-business Suite で設定要求は、一連のレポートとは、さまざまな段階に分類する同時実行プログラムです。</span><span class="sxs-lookup"><span data-stu-id="2c655-103">A request set in Oracle E-Business Suite is a set of reports and concurrent programs that are organized into various stages.</span></span> <span data-ttu-id="2c655-104">設定を一連のレポートと同時実行プログラムを実行する 1 つの要求を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2c655-104">You can use a single request set to run a set of reports and concurrent programs.</span></span> <span data-ttu-id="2c655-105">セットは、1 つまたは複数の段階的に分けられ、各ステージには、一連レポートと同時実行プログラムにはが含まれています。 を要求します。</span><span class="sxs-lookup"><span data-stu-id="2c655-105">Request sets are divided into one or more stages, and each stage contains a set of reports and concurrent programs.</span></span> <span data-ttu-id="2c655-106">これらのステージが、互いにリンクされている、各ステージの実行の順序が定義されます。</span><span class="sxs-lookup"><span data-stu-id="2c655-106">These stages are linked with each other, and the order of the execution of each stage is defined.</span></span> <span data-ttu-id="2c655-107">要求のセットに関する Oracle 固有の詳細についてを参照してください[http://go.microsoft.com/fwlink/p/?LinkId=129539](http://go.microsoft.com/fwlink/p/?LinkId=129539)です。</span><span class="sxs-lookup"><span data-stu-id="2c655-107">For more Oracle-specific information about request sets, go to [http://go.microsoft.com/fwlink/p/?LinkId=129539](http://go.microsoft.com/fwlink/p/?LinkId=129539).</span></span>  
  
 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="2c655-108">Oracle E-business Suite で要求のセットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2c655-108"> enables you to execute request sets in Oracle E-Business Suite.</span></span> <span data-ttu-id="2c655-109">要求セットでの操作として公開される、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="2c655-109">The request sets are exposed as operations in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="2c655-110">要求セットには、同時実行プログラムのセットが含まれている、ので、要求操作のセットの同時実行プログラム、入力パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="2c655-110">Since a request set contains a set of concurrent programs, those concurrent programs are the input parameters for a request set operation.</span></span> <span data-ttu-id="2c655-111">同時実行のプログラムと共に要求セットの操作は 4 つの複合型のパラメーターおよび単純型のパラメーターを入力として取得します。</span><span class="sxs-lookup"><span data-stu-id="2c655-111">Along with the concurrent programs, the request set operation takes four complex type parameters and a simple type parameter as input.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2c655-112">要求のセットは、アプリケーションのコンテキストを設定する必要があります[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要求セットに対するすべての操作を実行する前にします。</span><span class="sxs-lookup"><span data-stu-id="2c655-112">You must set the applications context for request sets in [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] before you can perform any operations on request sets.</span></span> <span data-ttu-id="2c655-113">アプリケーション コンテキストの設定 (責任、組織、および言語の設定) などのユーザー設定、およびアイテムのアクセス制御を設定して Oracle E-business Suite でセキュリティ保護されたトランザクションを容易にするためです。</span><span class="sxs-lookup"><span data-stu-id="2c655-113">This is because setting applications context facilitates secure transactions in Oracle E-Business Suite by setting user preferences (such as responsibility, organization, and language settings) and access control for an artifact.</span></span> <span data-ttu-id="2c655-114">アプリケーションのコンテキスト、およびように設定する方法については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。</span><span class="sxs-lookup"><span data-stu-id="2c655-114">For information about applications context, and how to set it, see [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
## <a name="complex-type-parameters"></a><span data-ttu-id="2c655-115">複合型パラメーター</span><span class="sxs-lookup"><span data-stu-id="2c655-115">Complex type parameters</span></span>
  
-   <span data-ttu-id="2c655-116">**SetRelClassOptions**: 要求セットのスケジュールのオプションを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="2c655-116">**SetRelClassOptions**: Enables you to set scheduling options for the request set.</span></span> <span data-ttu-id="2c655-117">SetRelClassOptions と SetRepeatOptions の両方が設定されている場合、SetRelClassOptions が優先されます。</span><span class="sxs-lookup"><span data-stu-id="2c655-117">If both SetRelClassOptions and SetRepeatOptions are set then SetRelClassOptions will take precedence.</span></span> <span data-ttu-id="2c655-118">SetRelClassOptions は、パラメーターとして、次のオプションを取ります。</span><span class="sxs-lookup"><span data-stu-id="2c655-118">SetRelClassOptions takes the following options as parameters:</span></span>  
  
    -   <span data-ttu-id="2c655-119">**アプリケーション**: 要求セットに関連付けられているアプリケーションの短い名前を示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-119">**Application**: Indicates the short name of the application associated with the request set.</span></span>  
  
    -   <span data-ttu-id="2c655-120">**ClassName**: 要求セットに関連付けられているクラスの名前を示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-120">**ClassName**: Indicates the name of the class associated with the request set.</span></span>  
  
    -   <span data-ttu-id="2c655-121">**CanceOrHold**: キャンセルまたは保留中フラグを示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-121">**CanceOrHold**: Indicates the Cancel or Hold flag.</span></span>  
  
    -   <span data-ttu-id="2c655-122">**StaleDate**: 日付を示す要求セットがまだ実行されていない場合以降にこの要求のセットが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="2c655-122">**StaleDate**: Indicates the date on or after which this request set will be canceled if the request set has not yet run.</span></span>  
  
    -   <span data-ttu-id="2c655-123">**ContinueOnFail**: 要求セットの送信を続行するか SetRelClassOptions に失敗した場合に例外をスローするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-123">**ContinueOnFail**: Indicates whether the request set submission should continue or throw an exception in case SetRelClassOptions fails.</span></span> <span data-ttu-id="2c655-124">"True"を指定できます (続行) または"False"(から例外をスローする)。</span><span class="sxs-lookup"><span data-stu-id="2c655-124">You can specify “True” (continue) or “False” (throw an exception).</span></span>  
  
-   <span data-ttu-id="2c655-125">**SetPrintOptions**: 要求セットの印刷オプションを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="2c655-125">**SetPrintOptions**: Enables you to set the print options for the request set.</span></span> <span data-ttu-id="2c655-126">SetPrintOptions は、パラメーターとして、次のオプションを取ります。</span><span class="sxs-lookup"><span data-stu-id="2c655-126">SetPrintOptions takes the following options as parameters:</span></span>  
  
    -   <span data-ttu-id="2c655-127">**プリンター**: 出力設定要求を送信するプリンター名を示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-127">**Printer**: Indicates the printer name where the request set output should be sent.</span></span>  
  
    -   <span data-ttu-id="2c655-128">**スタイル**: 出力設定要求の印刷に使用される印刷スタイルを示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-128">**Style**: Indicates the print style used to print the request set output.</span></span> <span data-ttu-id="2c655-129">たとえば、向き (横 (「)」または「縦」) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2c655-129">For example, you can specify the orientation (“Landscape” or “Portrait”).</span></span>  
  
    -   <span data-ttu-id="2c655-130">**コピー**: 出力設定要求の印刷するコピーの数を示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-130">**Copies**: Indicates the number of copies to be printed of the request set output.</span></span>  
  
    -   <span data-ttu-id="2c655-131">**SaveOutput**: 出力ファイルを保存するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-131">**SaveOutput**: Indicates whether or not to save the output file.</span></span> <span data-ttu-id="2c655-132">"True"または"False"を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="2c655-132">You can specify “True” or “False”.</span></span>  
  
    -   <span data-ttu-id="2c655-133">**PrintTogether**: サブ要求に対してのみ該当します。</span><span class="sxs-lookup"><span data-stu-id="2c655-133">**PrintTogether**: Applicable only for sub-requests.</span></span> <span data-ttu-id="2c655-134">サブ要求の出力を印刷する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-134">Indicates how the output of sub-requests is printed.</span></span> <span data-ttu-id="2c655-135">"Y"を指定すると、すべてのサブ要求が完了した後にのみ、サブ要求の出力が印刷されます。</span><span class="sxs-lookup"><span data-stu-id="2c655-135">If you specify “Y”, the output of sub-requests is printed only after all the sub-requests are complete.</span></span> <span data-ttu-id="2c655-136">指定した場合を完了したときに"N"、各サブ要求の出力を出力します。</span><span class="sxs-lookup"><span data-stu-id="2c655-136">If you specify “N”, the output of each sub-request is printed as it completes.</span></span>  
  
    -   <span data-ttu-id="2c655-137">**ContinueOnFail**: 要求セットの送信を続行するか SetPrintOptions に失敗した場合に例外をスローするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-137">**ContinueOnFail**: Indicates whether the request set submission should continue or throw an exception in case SetPrintOptions fails.</span></span> <span data-ttu-id="2c655-138">"True"を指定できます (続行) または"False"(から例外をスローする)。</span><span class="sxs-lookup"><span data-stu-id="2c655-138">You can specify “True” (continue) or “False” (throw an exception).</span></span>  
  
-   <span data-ttu-id="2c655-139">**SetRepeatOptions**: 要求セットの繰り返しオプションを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="2c655-139">**SetRepeatOptions**: Enables you to set the repeat options for the request set.</span></span> <span data-ttu-id="2c655-140">SetRepeatOptions は、パラメーターとして、次のオプションを取ります。</span><span class="sxs-lookup"><span data-stu-id="2c655-140">SetRepeatOptions takes the following options as parameters:</span></span>  
  
    -   <span data-ttu-id="2c655-141">**RepeatTime**: 要求のセットを繰り返すには 1 日の時刻を示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-141">**RepeatTime**: Indicates the time of day to repeat the request set.</span></span>  
  
    -   <span data-ttu-id="2c655-142">**RepeatInterval**: このパラメーターは場合にのみ適用**RepeatTime**は NULL です。</span><span class="sxs-lookup"><span data-stu-id="2c655-142">**RepeatInterval**: This parameter is applicable only when **RepeatTime** is NULL.</span></span> <span data-ttu-id="2c655-143">再送信を要求の間の間隔を示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-143">Indicates the interval between resubmissions of the request.</span></span> <span data-ttu-id="2c655-144">このオプションと共に使用して**RepeatUnit**の再送信の間の時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c655-144">Use this option along with **RepeatUnit** to specify the time between resubmissions.</span></span>  
  
    -   <span data-ttu-id="2c655-145">**RepeatUnit**: このパラメーターは場合にのみ適用**RepeatTime**は NULL です。</span><span class="sxs-lookup"><span data-stu-id="2c655-145">**RepeatUnit**: This parameter is applicable only when **RepeatTime** is NULL.</span></span> <span data-ttu-id="2c655-146">と共に使用する時間の単位**RepeatInterval**を再送信を要求の間の時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c655-146">The unit of time used along with **RepeatInterval** to specify the time between resubmissions of the request.</span></span> <span data-ttu-id="2c655-147">"Minutes"、"Hours"、"Days"または"Months"を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="2c655-147">You can specify “Minutes”, “Hours”, “Days” or “Months”.</span></span>  
  
    -   <span data-ttu-id="2c655-148">**RepeatType**: このパラメーターは場合にのみ適用**RepeatTime**は NULL です。</span><span class="sxs-lookup"><span data-stu-id="2c655-148">**RepeatType**: This parameter is applicable only when **RepeatTime** is NULL.</span></span> <span data-ttu-id="2c655-149">セットの実行を前の要求の"start"後または前の要求の"end"セットの実行後に繰り返しの間隔を適用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-149">Indicates whether the repeat interval is applied after the “start” of a previous request set execution or after the “end” of a previous request set execution.</span></span>  
  
    -   <span data-ttu-id="2c655-150">**RepeatEndTime**: 要求のセットを再送信を停止する日付と時刻を示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-150">**RepeatEndTime**: Indicates the date and time to stop resubmitting the request set.</span></span>  
  
    -   <span data-ttu-id="2c655-151">**ContinueOnFail**: 要求セットの送信を続行するか SetRepeatOptions に失敗した場合に例外をスローするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-151">**ContinueOnFail**: Indicates whether the request set submission should continue or throw an exception in case SetRepeatOptions fails.</span></span> <span data-ttu-id="2c655-152">"True"を指定できます (続行) または"False"(から例外をスローする)。</span><span class="sxs-lookup"><span data-stu-id="2c655-152">You can specify “True” (continue) or “False” (throw an exception).</span></span>  
  
-   <span data-ttu-id="2c655-153">**SetNlsOptions**: 要求セットの NLS オプションを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="2c655-153">**SetNlsOptions**: Enables you to set the NLS options for the request set.</span></span> <span data-ttu-id="2c655-154">SetNlsOptions は、パラメーターとして、次のオプションを取ります。</span><span class="sxs-lookup"><span data-stu-id="2c655-154">SetNlsOptions takes the following options as parameters:</span></span>  
  
    -   <span data-ttu-id="2c655-155">**言語**: NLS 言語を示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-155">**Language**: Indicates the NLS language.</span></span>  
  
    -   <span data-ttu-id="2c655-156">**言語**: 言語の販売区域を示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-156">**Language**: Indicates the language territory.</span></span>  
  
    -   <span data-ttu-id="2c655-157">**ContinueOnFail**: 要求セットの送信を続行するか SetNlsOptions に失敗した場合に例外をスローするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-157">**ContinueOnFail**: Indicates whether the request set submission should continue or throw an exception in case SetNlsOptions fails.</span></span> <span data-ttu-id="2c655-158">"True"を指定できます (続行) または"False"(から例外をスローする)。</span><span class="sxs-lookup"><span data-stu-id="2c655-158">You can specify “True” (continue) or “False” (throw an exception).</span></span>  
  
## <a name="simple-type-parameter"></a><span data-ttu-id="2c655-159">単純型のパラメーター</span><span class="sxs-lookup"><span data-stu-id="2c655-159">Simple type parameter</span></span>
  
 <span data-ttu-id="2c655-160">**StartTime**: 要求セットの実行開始時刻を示します。</span><span class="sxs-lookup"><span data-stu-id="2c655-160">**StartTime**: Indicates the time at which the request set should start running.</span></span>  
  
 <span data-ttu-id="2c655-161">場合は、要求設定が正常に完了、同時実行要求 ID が返されます。</span><span class="sxs-lookup"><span data-stu-id="2c655-161">If the request set completes successfully, a concurrent request ID is returned.</span></span> <span data-ttu-id="2c655-162">それ以外の場合、「0」が返されます。</span><span class="sxs-lookup"><span data-stu-id="2c655-162">Otherwise, “0” is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c655-163">参照</span><span class="sxs-lookup"><span data-stu-id="2c655-163">See Also</span></span>  
 <span data-ttu-id="2c655-164">[どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="2c655-164">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>