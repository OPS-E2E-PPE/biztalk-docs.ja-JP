---
title: カスタムの累積 Functoid の開発 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ea2c5fa-ed50-4b76-aee9-0d4adf9e6d8c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f69ae870269948358f117b07f37d481faced160
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242330"
---
# <a name="developing-a-custom-cumulative-functoid"></a><span data-ttu-id="d373c-102">カスタムの累積 Functoid の開発</span><span class="sxs-lookup"><span data-stu-id="d373c-102">Developing a Custom Cumulative Functoid</span></span>
<span data-ttu-id="d373c-103">カスタムの累積 Functoid を使用して、インスタンス メッセージ内で何度も発生する値の累積処理を行います。</span><span class="sxs-lookup"><span data-stu-id="d373c-103">Use a custom cumulative functoid to perform accumulation operations for values that occur multiple times within an instance message.</span></span>  
  
 <span data-ttu-id="d373c-104">累積 Functoid を開発する場合、3 つの関数を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d373c-104">You must implement three functions when developing a cumulative functoid.</span></span> <span data-ttu-id="d373c-105">3 つの関数とは、マップで累積を行う場合に必要となる、初期化操作、累積操作、および取得操作です。</span><span class="sxs-lookup"><span data-stu-id="d373c-105">The three functions correspond to the initialize, cumulate, and get actions that the map needs to perform the accumulation.</span></span> <span data-ttu-id="d373c-106">これらの関数を検討する前に、スレッドの安全性を検討することが重要です。</span><span class="sxs-lookup"><span data-stu-id="d373c-106">Before discussing these functions it is important to discuss thread safety.</span></span>  
  
## <a name="writing-a-thread-safe-functoid"></a><span data-ttu-id="d373c-107">スレッド セーフ Functoid の作成</span><span class="sxs-lookup"><span data-stu-id="d373c-107">Writing a Thread-Safe Functoid</span></span>  
 <span data-ttu-id="d373c-108">この Functoid のコードは、ストレス条件下でマップの複数のインスタンスが同時に実行される場合があるので、スレッド セーフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d373c-108">The functoid code must be thread-safe because under stress conditions multiple instances of a map may be running concurrently.</span></span> <span data-ttu-id="d373c-109">注意事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d373c-109">Some of the points to remember include:</span></span>  
  
-   <span data-ttu-id="d373c-110">静的状態は、スレッド セーフであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="d373c-110">Static state must be thread-safe.</span></span>  
  
-   <span data-ttu-id="d373c-111">インスタンス状態は、必ずしもスレッド セーフである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d373c-111">Instance state does not always need to be thread-safe.</span></span>  
  
-   <span data-ttu-id="d373c-112">高いストレス条件下で実行されることを考慮してデザインします。</span><span class="sxs-lookup"><span data-stu-id="d373c-112">Design with consideration for running under high-stress conditions.</span></span> <span data-ttu-id="d373c-113">可能な場合、ロックの取得は避けます。</span><span class="sxs-lookup"><span data-stu-id="d373c-113">Avoid taking locks whenever possible.</span></span>  
  
-   <span data-ttu-id="d373c-114">可能な場合、同期の必要性を避けるようにします。</span><span class="sxs-lookup"><span data-stu-id="d373c-114">Avoid the need for synchronization if possible.</span></span>  
  
 <span data-ttu-id="d373c-115">BizTalk Server では、単純なメカニズムを使用することによって、スレッド セーフの累積 Functoid を簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="d373c-115">BizTalk Server provides a simple mechanism to reduce the complexity of writing a thread-safe cumulative functoid.</span></span> <span data-ttu-id="d373c-116">3 つのすべての関数は、最初のパラメーターが同じ (整数型のインデックス値) です。</span><span class="sxs-lookup"><span data-stu-id="d373c-116">All three functions have the same first parameter, an integer index value.</span></span> <span data-ttu-id="d373c-117">BizTalk Server は、初期化関数を呼び出すとき、固有の数値をインデックス値に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d373c-117">BizTalk Server assigns a unique number to the index value when it calls your initialization function.</span></span> <span data-ttu-id="d373c-118">この値は、次のコードに示すように、累積値を格納する配列用のインデックスとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="d373c-118">You can use this value as an index into an array that holds accumulating values, as shown in the following code:</span></span>  
  
```  
private HashTable cumulativeArray = new HashTable();  
…  
// Initialization function  
public string InitCumulativeMultiply(int index)  
{  
    cumulativeArray[index] = 1.0;  
    return string.Empty;  
}  
```  
  
 <span data-ttu-id="d373c-119">この例では、ArrayList の代わりに HashTable が使用されています。</span><span class="sxs-lookup"><span data-stu-id="d373c-119">This example uses a HashTable instead of an ArrayList.</span></span> <span data-ttu-id="d373c-120">このため、初期化関数は、順番どおりのインデックス値で呼び出されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d373c-120">This is because the initialization function might not be called with in-order index values.</span></span>  
  
## <a name="implementing-the-three-cumulative-functions"></a><span data-ttu-id="d373c-121">3 つの累積関数の実装</span><span class="sxs-lookup"><span data-stu-id="d373c-121">Implementing the Three Cumulative Functions</span></span>  
 <span data-ttu-id="d373c-122">開発するカスタムの累積 Functoid ごとに、3 つの関数を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d373c-122">You will need to implement three functions for each custom cumulative functoid you develop.</span></span> <span data-ttu-id="d373c-123">コンストラクターで呼び出して設定する関数とメソッドを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="d373c-123">The functions and the methods you must call in the constructor to set them are summarized in the following table.</span></span> <span data-ttu-id="d373c-124">すべての関数は文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="d373c-124">All of the functions return string values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d373c-125">各関数に対して、わかりやすい名前を設定します。また、関数ごとに引数の数と種類を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d373c-125">You determine the best name for each function, but each function must have the number and type of arguments specified.</span></span>  
  
|<span data-ttu-id="d373c-126">関数の目的</span><span class="sxs-lookup"><span data-stu-id="d373c-126">Function Purpose</span></span>|<span data-ttu-id="d373c-127">引数</span><span class="sxs-lookup"><span data-stu-id="d373c-127">Arguments</span></span>|<span data-ttu-id="d373c-128">参照の設定</span><span class="sxs-lookup"><span data-stu-id="d373c-128">To set a reference</span></span>|<span data-ttu-id="d373c-129">インライン スクリプトの設定</span><span class="sxs-lookup"><span data-stu-id="d373c-129">To set inline script</span></span>|  
|----------------------|---------------|------------------------|--------------------------|  
|<span data-ttu-id="d373c-130">初期化</span><span class="sxs-lookup"><span data-stu-id="d373c-130">Initialization</span></span>|<span data-ttu-id="d373c-131">**int インデックス**</span><span class="sxs-lookup"><span data-stu-id="d373c-131">**int index**</span></span>|<span data-ttu-id="d373c-132">**SetExternalFunctionName**</span><span class="sxs-lookup"><span data-stu-id="d373c-132">**SetExternalFunctionName**</span></span>|<span data-ttu-id="d373c-133">**SetScriptBuffer**で`functionNumber`0 を =</span><span class="sxs-lookup"><span data-stu-id="d373c-133">**SetScriptBuffer** with `functionNumber` = 0</span></span>|  
|<span data-ttu-id="d373c-134">累計</span><span class="sxs-lookup"><span data-stu-id="d373c-134">Cumulation</span></span>|<span data-ttu-id="d373c-135">**int val、文字列のスコープにインデックスを作成、**</span><span class="sxs-lookup"><span data-stu-id="d373c-135">**int index, string val, string scope**</span></span>|<span data-ttu-id="d373c-136">**SetExternalFunctionName2**</span><span class="sxs-lookup"><span data-stu-id="d373c-136">**SetExternalFunctionName2**</span></span>|<span data-ttu-id="d373c-137">**SetScriptBuffer**で`functionNumber`= 1</span><span class="sxs-lookup"><span data-stu-id="d373c-137">**SetScriptBuffer** with `functionNumber` = 1</span></span>|  
|<span data-ttu-id="d373c-138">取得</span><span class="sxs-lookup"><span data-stu-id="d373c-138">Get</span></span>|<span data-ttu-id="d373c-139">**int インデックス**</span><span class="sxs-lookup"><span data-stu-id="d373c-139">**int index**</span></span>|<span data-ttu-id="d373c-140">**SetExternalFunctionName3**</span><span class="sxs-lookup"><span data-stu-id="d373c-140">**SetExternalFunctionName3**</span></span>|<span data-ttu-id="d373c-141">**SetScriptBuffer**で`functionNumber`= 2</span><span class="sxs-lookup"><span data-stu-id="d373c-141">**SetScriptBuffer** with `functionNumber` = 2</span></span>|  
  
### <a name="initialization"></a><span data-ttu-id="d373c-142">初期化</span><span class="sxs-lookup"><span data-stu-id="d373c-142">Initialization</span></span>  
 <span data-ttu-id="d373c-143">初期化を行うと、累積の実行で使用するメカニズムを準備できます。</span><span class="sxs-lookup"><span data-stu-id="d373c-143">Initialization enables you to prepare the mechanisms you will use to perform accumulation.</span></span> <span data-ttu-id="d373c-144">配列の初期化、1 つ以上の値の再設定、または必要に応じた他のリソースの読み込みを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d373c-144">You can initialize an array, reset one or more values, or load other resources as needed.</span></span> <span data-ttu-id="d373c-145">文字列の戻り値は使用されません。</span><span class="sxs-lookup"><span data-stu-id="d373c-145">The string return value is not used.</span></span>  
  
### <a name="cumulation"></a><span data-ttu-id="d373c-146">累計</span><span class="sxs-lookup"><span data-stu-id="d373c-146">Cumulation</span></span>  
 <span data-ttu-id="d373c-147">この操作で、Functoid の累積処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="d373c-147">This is where you perform the accumulation operation appropriate for your functoid.</span></span> <span data-ttu-id="d373c-148">BizTalk Server は次の 3 つのパラメーターを渡します。</span><span class="sxs-lookup"><span data-stu-id="d373c-148">BizTalk Server passes in the following three parameters:</span></span>  
  
-   <span data-ttu-id="d373c-149">**インデックス。**</span><span class="sxs-lookup"><span data-stu-id="d373c-149">**Index.**</span></span> <span data-ttu-id="d373c-150">マップのインスタンスを表す整数型の値です。</span><span class="sxs-lookup"><span data-stu-id="d373c-150">An integer value representing a map instance.</span></span> <span data-ttu-id="d373c-151">複数のマップのインスタンスが同時に実行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d373c-151">There may be multiple map instances running concurrently.</span></span>  
  
-   <span data-ttu-id="d373c-152">**Val です。**</span><span class="sxs-lookup"><span data-stu-id="d373c-152">**Val.**</span></span> <span data-ttu-id="d373c-153">累積する値を含む文字列です。</span><span class="sxs-lookup"><span data-stu-id="d373c-153">A string containing the value that should be accumulated.</span></span> <span data-ttu-id="d373c-154">文字列の累積 Functoid を記述していない場合は、数値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d373c-154">Unless you are writing a string Cumulate functoid it is a numeric value.</span></span>  
  
-   <span data-ttu-id="d373c-155">**スコープです。**</span><span class="sxs-lookup"><span data-stu-id="d373c-155">**Scope.**</span></span> <span data-ttu-id="d373c-156">累積する要素または属性を示す数値を含む文字列です。</span><span class="sxs-lookup"><span data-stu-id="d373c-156">A string containing a number indicating which element or attribute value should be accumulated.</span></span> <span data-ttu-id="d373c-157">実際の値は、実装によって決まります。</span><span class="sxs-lookup"><span data-stu-id="d373c-157">Actual values are determined by an implementation.</span></span>  
  
 <span data-ttu-id="d373c-158">累積する値および無視する値を決めます。</span><span class="sxs-lookup"><span data-stu-id="d373c-158">You decide which values to accumulate and which values to ignore.</span></span> <span data-ttu-id="d373c-159">たとえば、0 未満ではない値を無視し、値が数値ではない場合に例外をスローできます。</span><span class="sxs-lookup"><span data-stu-id="d373c-159">For example, you may ignore values that are not below 0 but throw an exception when a value is not numeric.</span></span> <span data-ttu-id="d373c-160">**BaseFunctoid**関数を 2 つ提供 —**IsDate**と**IsNumeric**— 検証を支援します。</span><span class="sxs-lookup"><span data-stu-id="d373c-160">**BaseFunctoid** supplies two functions—**IsDate** and **IsNumeric**—to assist with validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d373c-161">使用する場合**IsDate**または**IsNumeric**インライン スクリプトでは設定を必ず**RequiredGlobalHelperFunctions**関数、スクリプトで利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d373c-161">If you use **IsDate** or **IsNumeric** in an inline script, be sure to set **RequiredGlobalHelperFunctions** so that the functions are made available to your script.</span></span>  
  
 <span data-ttu-id="d373c-162">文字列の戻り値は使用されません。</span><span class="sxs-lookup"><span data-stu-id="d373c-162">The string return value is not used.</span></span>  
  
### <a name="get"></a><span data-ttu-id="d373c-163">取得</span><span class="sxs-lookup"><span data-stu-id="d373c-163">Get</span></span>  
 <span data-ttu-id="d373c-164">マップの Functoid の設定によって定義された、すべての値の繰り返し処理が完了すると、BizTalk Server は、累積された値を要求します。</span><span class="sxs-lookup"><span data-stu-id="d373c-164">When BizTalk Server finishes iterating through all of the values determined by the functoid settings in the map, it requests the accumulated value.</span></span> <span data-ttu-id="d373c-165">取得関数は、マップのインスタンスを表す整数型の値である引数 (`Index`) を 1 つ使用します。</span><span class="sxs-lookup"><span data-stu-id="d373c-165">The get function has one argument, `Index`, which is an integer value representing a map instance.</span></span> <span data-ttu-id="d373c-166">関数では、インデックス値を使用して、累積された値を検索してから文字列として返します。</span><span class="sxs-lookup"><span data-stu-id="d373c-166">Your function should use the index value to find and return the accumulated value as a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d373c-167">例</span><span class="sxs-lookup"><span data-stu-id="d373c-167">Example</span></span>  
 <span data-ttu-id="d373c-168">乗算の累積を行うカスタム Functoid の作成方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d373c-168">The following example illustrates how to create a custom functoid for performing cumulative multiplication.</span></span> <span data-ttu-id="d373c-169">ここでは、3 つの文字列リソースと 16x16 ピクセルのビットマップ リソースが格納されたリソース ファイルがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="d373c-169">It relies on a resource file containing three string resources and a 16x16-pixel bitmap resource.</span></span>  
  
```  
using System;  
using Microsoft.BizTalk.BaseFunctoids;  
using System.Reflection;  
using System.Text;  
using System.Collections;  
using System.Globalization;  
  
namespace Microsoft.Samples.BizTalk.CustomFunctoid  
{  
    public class CumulativeMultiplyFunctoid : BaseFunctoid  
    {  
        private ArrayList myCumulativeArray = new ArrayList();  
  
        public CumulativeMultiplyFunctoid() : base()  
        {  
            //ID for this functoid  
            ID = 6001;  
  
            // Resource assembly must be ProjectName.ResourceName if building with VS.Net  
            SetupResourceAssembly("Microsoft.Samples.BizTalk.CustomFunctoid.CustomFunctoidResources", Assembly.GetExecutingAssembly());  
  
            // Pass the resource ID names for functoid name, tooltip  
            // description and the 16x16 bitmap for the Map palette  
            SetName("IDS_CUMULATIVEMULTIPLYFUNCTOID_NAME");  
            SetTooltip("IDS_CUMULATIVEMULTIPLYFUNCTOID_TOOLTIP");  
            SetDescription("IDS_CUMULATIVEMULTIPLYFUNCTOID_DESCRIPTION");  
            SetBitmap("IDB_CUMULATIVEMULTIPLYFUNCTOID_BITMAP");  
  
            // Put this string handling function under the Cumulative  
            // Functoid tab in the Visual Studio toolbox for functoids  
            Category = FunctoidCategory.Cumulative;  
  
            // 2 required parameters, no optional parameters  
            SetMinParams(1);  
            SetMaxParams(2);  
  
            // Functoid accepts three inputs  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
            AddInputConnectionType((~ConnectionType.FunctoidCount) & (~ConnectionType.FunctoidIndex) & (~ConnectionType.FunctoidIteration) & (~ConnectionType.FunctoidCumulative) & (~ConnectionType.FunctoidLooping) & (~ConnectionType.Record));  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
  
            // Set the output connection type  
            OutputConnectionType = ConnectionType.AllExceptRecord;  
  
            // Set the Initialize, Cumulative and Get functions  
            SetExternalFunctionName(GetType().Assembly.FullName, "Microsoft.Samples.BizTalk.CustomFunctoid.CumulativeMultiplyFunctoid", "InitCumulativeMultiply");  
            SetExternalFunctionName2("AddToCumulativeMultiply");  
            SetExternalFunctionName3("GetCumulativeMultiply");  
        }  
  
        // Initialization function  
        public string InitCumulativeMultiply(int index)  
        {  
            if (index >= 0)  
            {  
                if (index >= myCumulativeArray.Count)  
                {  
                    myCumulativeArray.Add(1.0);  
                }  
                else  
                {  
                    myCumulativeArray[index] = 1.0;  
                }  
            }  
  
            return "";  
        }  
  
        // Cumulative function  
        public string AddToCumulativeMultiply(int index, string val, string reserved)  
        {  
            if (index < 0 || index >= myCumulativeArray.Count)  
            {  
                return "";  
            }  
  
            if (IsNumeric(val))  
            {  
                double dval = Convert.ToDouble(val, CultureInfo.InvariantCulture);  
                myCumulativeArray[index] = (double)(myCumulativeArray[index]) * dval;  
            }  
            return myCumulativeArray[index].ToString();  
        }  
  
        // Get Function  
        public string GetCumulativeMultiply(int index)  
        {  
            if (index < 0 || index >= myCumulativeArray.Count)  
            {  
                return "";  
            }  
  
            return myCumulativeArray[index].ToString();  
        }  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="d373c-170">参照</span><span class="sxs-lookup"><span data-stu-id="d373c-170">See Also</span></span>  
 <span data-ttu-id="d373c-171">[BaseFunctoid の使用](../core/using-basefunctoid.md) </span><span class="sxs-lookup"><span data-stu-id="d373c-171">[Using BaseFunctoid](../core/using-basefunctoid.md) </span></span>  
 <span data-ttu-id="d373c-172">[インラインのカスタム Functoid の開発](../core/developing-a-custom-inline-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="d373c-172">[Developing a Custom Inline Functoid](../core/developing-a-custom-inline-functoid.md) </span></span>  
 [<span data-ttu-id="d373c-173">カスタム Functoid (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="d373c-173">Custom Functoid (BizTalk Server Sample)</span></span>](../core/custom-functoid-biztalk-server-sample.md)