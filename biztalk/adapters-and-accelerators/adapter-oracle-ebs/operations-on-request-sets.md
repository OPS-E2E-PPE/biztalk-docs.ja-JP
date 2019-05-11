---
title: 要求セットに対する操作 |Microsoft Docs
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
ms.openlocfilehash: cfc8c773be09a302e740b2eb7d59828e3a1688b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375293"
---
# <a name="operations-on-request-sets"></a><span data-ttu-id="6f1a0-102">要求セットに対する操作</span><span class="sxs-lookup"><span data-stu-id="6f1a0-102">Operations on Request Sets</span></span>
<span data-ttu-id="6f1a0-103">Oracle E-business Suite で設定要求は、一連のレポートとはさまざまな段階に分かれていますが、同時実行プログラムです。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-103">A request set in Oracle E-Business Suite is a set of reports and concurrent programs that are organized into various stages.</span></span> <span data-ttu-id="6f1a0-104">一連のレポートと同時実行プログラムを実行する 1 つの要求を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-104">You can use a single request set to run a set of reports and concurrent programs.</span></span> <span data-ttu-id="6f1a0-105">要求セットは 1 つまたは複数の段階に分けられ、各ステージには、一連レポートと同時実行プログラムにはが含まれています。 します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-105">Request sets are divided into one or more stages, and each stage contains a set of reports and concurrent programs.</span></span> <span data-ttu-id="6f1a0-106">これらのステージは互いにリンクされ、各ステージの実行の順序が定義されています。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-106">These stages are linked with each other, and the order of the execution of each stage is defined.</span></span> <span data-ttu-id="6f1a0-107">要求のセットに関する Oracle 固有の詳細を参照してください[ http://go.microsoft.com/fwlink/p/?LinkId=129539](http://go.microsoft.com/fwlink/p/?LinkId=129539)します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-107">For more Oracle-specific information about request sets, go to [http://go.microsoft.com/fwlink/p/?LinkId=129539](http://go.microsoft.com/fwlink/p/?LinkId=129539).</span></span>  
  
 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] <span data-ttu-id="6f1a0-108">Oracle E-business Suite での要求セットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-108">enables you to execute request sets in Oracle E-Business Suite.</span></span> <span data-ttu-id="6f1a0-109">操作として公開される要求セット、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-109">The request sets are exposed as operations in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="6f1a0-110">要求セットには、同時実行プログラムのセットが格納されている、ため、要求の設定操作の同時実行プログラムは入力パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-110">Since a request set contains a set of concurrent programs, those concurrent programs are the input parameters for a request set operation.</span></span> <span data-ttu-id="6f1a0-111">同時実行のプログラムと共に要求の設定操作は 4 つの複合型パラメーターおよび単純型のパラメーターを入力として取得します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-111">Along with the concurrent programs, the request set operation takes four complex type parameters and a simple type parameter as input.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6f1a0-112">要求のセット、アプリケーションのコンテキストを設定する必要があります[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要求セットの任意の操作を実行する前にします。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-112">You must set the applications context for request sets in [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] before you can perform any operations on request sets.</span></span> <span data-ttu-id="6f1a0-113">アプリケーション コンテキストの設定 (責任、組織、および言語の設定) などのユーザー設定とアーティファクトのアクセス制御を設定して Oracle E-business Suite でセキュリティで保護されたトランザクションを促進するためです。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-113">This is because setting applications context facilitates secure transactions in Oracle E-Business Suite by setting user preferences (such as responsibility, organization, and language settings) and access control for an artifact.</span></span> <span data-ttu-id="6f1a0-114">アプリケーションのコンテキスト、および設定する方法については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-114">For information about applications context, and how to set it, see [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
## <a name="complex-type-parameters"></a><span data-ttu-id="6f1a0-115">複合型のパラメーター</span><span class="sxs-lookup"><span data-stu-id="6f1a0-115">Complex type parameters</span></span>
  
-   <span data-ttu-id="6f1a0-116">**SetRelClassOptions**:要求セットのスケジュールのオプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-116">**SetRelClassOptions**: Enables you to set scheduling options for the request set.</span></span> <span data-ttu-id="6f1a0-117">SetRelClassOptions と SetRepeatOptions の両方が設定されている場合、SetRelClassOptions が優先されます。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-117">If both SetRelClassOptions and SetRepeatOptions are set then SetRelClassOptions will take precedence.</span></span> <span data-ttu-id="6f1a0-118">SetRelClassOptions はパラメーターとして、次のオプションを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-118">SetRelClassOptions takes the following options as parameters:</span></span>  
  
    -   <span data-ttu-id="6f1a0-119">**アプリケーション**:要求セットに関連付けられたアプリケーションの短い名前を示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-119">**Application**: Indicates the short name of the application associated with the request set.</span></span>  
  
    -   <span data-ttu-id="6f1a0-120">**ClassName**:要求セットに関連付けられたクラスの名前を示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-120">**ClassName**: Indicates the name of the class associated with the request set.</span></span>  
  
    -   <span data-ttu-id="6f1a0-121">**CanceOrHold**:キャンセル または 保留のフラグを示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-121">**CanceOrHold**: Indicates the Cancel or Hold flag.</span></span>  
  
    -   <span data-ttu-id="6f1a0-122">**StaleDate**:日時を示す要求セットがまだ実行していない場合、または後にこの要求セットがキャンセルされます。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-122">**StaleDate**: Indicates the date on or after which this request set will be canceled if the request set has not yet run.</span></span>  
  
    -   <span data-ttu-id="6f1a0-123">**ContinueOnFail**:要求セットを送信する必要があります続行または SetRelClassOptions に失敗した場合に例外をスローするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-123">**ContinueOnFail**: Indicates whether the request set submission should continue or throw an exception in case SetRelClassOptions fails.</span></span> <span data-ttu-id="6f1a0-124">"True"を指定することができます (引き続き) または"False"(例外をスローする)。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-124">You can specify “True” (continue) or “False” (throw an exception).</span></span>  
  
-   <span data-ttu-id="6f1a0-125">**SetPrintOptions**:要求セットの印刷オプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-125">**SetPrintOptions**: Enables you to set the print options for the request set.</span></span> <span data-ttu-id="6f1a0-126">SetPrintOptions はパラメーターとして、次のオプションを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-126">SetPrintOptions takes the following options as parameters:</span></span>  
  
    -   <span data-ttu-id="6f1a0-127">**プリンター**:出力を設定する要求を送信するプリンター名を示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-127">**Printer**: Indicates the printer name where the request set output should be sent.</span></span>  
  
    -   <span data-ttu-id="6f1a0-128">**スタイル**:出力設定要求の印刷に使用する印刷スタイルを示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-128">**Style**: Indicates the print style used to print the request set output.</span></span> <span data-ttu-id="6f1a0-129">たとえば、(「Landscape」または「Portrait」) の方向を指定できます。 します</span><span class="sxs-lookup"><span data-stu-id="6f1a0-129">For example, you can specify the orientation (“Landscape” or “Portrait”).</span></span>  
  
    -   <span data-ttu-id="6f1a0-130">**コピー**:出力設定要求の印刷するコピーの数を示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-130">**Copies**: Indicates the number of copies to be printed of the request set output.</span></span>  
  
    -   <span data-ttu-id="6f1a0-131">**SaveOutput**:出力ファイルを保存するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-131">**SaveOutput**: Indicates whether or not to save the output file.</span></span> <span data-ttu-id="6f1a0-132">"True"または"False"を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-132">You can specify “True” or “False”.</span></span>  
  
    -   <span data-ttu-id="6f1a0-133">**PrintTogether**:サブ要求に対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-133">**PrintTogether**: Applicable only for sub-requests.</span></span> <span data-ttu-id="6f1a0-134">サブ要求の出力を印刷する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-134">Indicates how the output of sub-requests is printed.</span></span> <span data-ttu-id="6f1a0-135">"Y"を指定すると、すべてのサブ要求が完了した後にのみ、サブ要求の出力が印刷されます。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-135">If you specify “Y”, the output of sub-requests is printed only after all the sub-requests are complete.</span></span> <span data-ttu-id="6f1a0-136">指定した場合は、これが完了すると、"N"、各サブ要求の出力が出力されます。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-136">If you specify “N”, the output of each sub-request is printed as it completes.</span></span>  
  
    -   <span data-ttu-id="6f1a0-137">**ContinueOnFail**:要求セットを送信する必要があります続行または SetPrintOptions に失敗した場合に例外をスローするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-137">**ContinueOnFail**: Indicates whether the request set submission should continue or throw an exception in case SetPrintOptions fails.</span></span> <span data-ttu-id="6f1a0-138">"True"を指定することができます (引き続き) または"False"(例外をスローする)。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-138">You can specify “True” (continue) or “False” (throw an exception).</span></span>  
  
-   <span data-ttu-id="6f1a0-139">**SetRepeatOptions**:要求セットの繰り返しのオプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-139">**SetRepeatOptions**: Enables you to set the repeat options for the request set.</span></span> <span data-ttu-id="6f1a0-140">SetRepeatOptions はパラメーターとして、次のオプションを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-140">SetRepeatOptions takes the following options as parameters:</span></span>  
  
    -   <span data-ttu-id="6f1a0-141">**RepeatTime**:時間帯を要求のセットを繰り返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-141">**RepeatTime**: Indicates the time of day to repeat the request set.</span></span>  
  
    -   <span data-ttu-id="6f1a0-142">**RepeatInterval**:このパラメーターは場合にのみ適用**RepeatTime**は NULL です。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-142">**RepeatInterval**: This parameter is applicable only when **RepeatTime** is NULL.</span></span> <span data-ttu-id="6f1a0-143">要求の再送信間隔を示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-143">Indicates the interval between resubmissions of the request.</span></span> <span data-ttu-id="6f1a0-144">と共にこのオプションを使用して**RepeatUnit**を再送信間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-144">Use this option along with **RepeatUnit** to specify the time between resubmissions.</span></span>  
  
    -   <span data-ttu-id="6f1a0-145">**RepeatUnit**:このパラメーターは場合にのみ適用**RepeatTime**は NULL です。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-145">**RepeatUnit**: This parameter is applicable only when **RepeatTime** is NULL.</span></span> <span data-ttu-id="6f1a0-146">と一緒に使用すると時間の単位**RepeatInterval**を再送信を要求の間の時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-146">The unit of time used along with **RepeatInterval** to specify the time between resubmissions of the request.</span></span> <span data-ttu-id="6f1a0-147">"Minutes"、"Hours"、"Days"または「月」を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-147">You can specify “Minutes”, “Hours”, “Days” or “Months”.</span></span>  
  
    -   <span data-ttu-id="6f1a0-148">**RepeatType**:このパラメーターは場合にのみ適用**RepeatTime**は NULL です。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-148">**RepeatType**: This parameter is applicable only when **RepeatTime** is NULL.</span></span> <span data-ttu-id="6f1a0-149">前の要求の"start"が実行を設定した後、または前の要求の"end"が実行を設定した後、リピート間隔が適用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-149">Indicates whether the repeat interval is applied after the “start” of a previous request set execution or after the “end” of a previous request set execution.</span></span>  
  
    -   <span data-ttu-id="6f1a0-150">**RepeatEndTime**:要求のセットを再送信を停止する日付と時刻を示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-150">**RepeatEndTime**: Indicates the date and time to stop resubmitting the request set.</span></span>  
  
    -   <span data-ttu-id="6f1a0-151">**ContinueOnFail**:要求セットを送信する必要があります続行または SetRepeatOptions に失敗した場合に例外をスローするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-151">**ContinueOnFail**: Indicates whether the request set submission should continue or throw an exception in case SetRepeatOptions fails.</span></span> <span data-ttu-id="6f1a0-152">"True"を指定することができます (引き続き) または"False"(例外をスローする)。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-152">You can specify “True” (continue) or “False” (throw an exception).</span></span>  
  
-   <span data-ttu-id="6f1a0-153">**SetNlsOptions**:要求セットの NLS オプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-153">**SetNlsOptions**: Enables you to set the NLS options for the request set.</span></span> <span data-ttu-id="6f1a0-154">SetNlsOptions はパラメーターとして、次のオプションを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-154">SetNlsOptions takes the following options as parameters:</span></span>  
  
    -   <span data-ttu-id="6f1a0-155">**言語**:NLS 言語を示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-155">**Language**: Indicates the NLS language.</span></span>  
  
    -   <span data-ttu-id="6f1a0-156">**言語**:言語の販売区域を示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-156">**Language**: Indicates the language territory.</span></span>  
  
    -   <span data-ttu-id="6f1a0-157">**ContinueOnFail**:要求セットを送信する必要があります続行または SetNlsOptions に失敗した場合に例外をスローするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-157">**ContinueOnFail**: Indicates whether the request set submission should continue or throw an exception in case SetNlsOptions fails.</span></span> <span data-ttu-id="6f1a0-158">"True"を指定することができます (引き続き) または"False"(例外をスローする)。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-158">You can specify “True” (continue) or “False” (throw an exception).</span></span>  
  
## <a name="simple-type-parameter"></a><span data-ttu-id="6f1a0-159">単純型のパラメーター</span><span class="sxs-lookup"><span data-stu-id="6f1a0-159">Simple type parameter</span></span>
  
 <span data-ttu-id="6f1a0-160">**startTime**:要求セットの実行開始時刻を示します。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-160">**StartTime**: Indicates the time at which the request set should start running.</span></span>  
  
 <span data-ttu-id="6f1a0-161">場合は、要求の設定が正常に完了、同時実行要求 ID が返されます。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-161">If the request set completes successfully, a concurrent request ID is returned.</span></span> <span data-ttu-id="6f1a0-162">それ以外の場合、「0」が返されます。</span><span class="sxs-lookup"><span data-stu-id="6f1a0-162">Otherwise, “0” is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f1a0-163">参照</span><span class="sxs-lookup"><span data-stu-id="6f1a0-163">See Also</span></span>  
 <span data-ttu-id="6f1a0-164">[どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="6f1a0-164">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>