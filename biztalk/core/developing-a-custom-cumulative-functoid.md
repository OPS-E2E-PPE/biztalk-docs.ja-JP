---
title: カスタムの累積 Functoid の開発 |Microsoft Docs
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
ms.openlocfilehash: 05152065b93fabe103125718334a61da878fd309
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389469"
---
# <a name="developing-a-custom-cumulative-functoid"></a><span data-ttu-id="b69b2-102">カスタムの累積 Functoid の開発</span><span class="sxs-lookup"><span data-stu-id="b69b2-102">Developing a Custom Cumulative Functoid</span></span>
<span data-ttu-id="b69b2-103">カスタムの累積 functoid を使用すると、インスタンス メッセージ内で複数回に発生する値の累積処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b69b2-103">Use a custom cumulative functoid to perform accumulation operations for values that occur multiple times within an instance message.</span></span>  
  
 <span data-ttu-id="b69b2-104">累積 functoid を開発する際に、3 つの関数を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b69b2-104">You must implement three functions when developing a cumulative functoid.</span></span> <span data-ttu-id="b69b2-105">3 つの関数は、初期化操作、累積操作に対応し、マップが、累積したものを実行する必要があるアクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="b69b2-105">The three functions correspond to the initialize, cumulate, and get actions that the map needs to perform the accumulation.</span></span> <span data-ttu-id="b69b2-106">これらの関数を説明する前にすることが重要スレッド セーフについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b69b2-106">Before discussing these functions it is important to discuss thread safety.</span></span>  
  
## <a name="writing-a-thread-safe-functoid"></a><span data-ttu-id="b69b2-107">スレッド セーフ Functoid の作成</span><span class="sxs-lookup"><span data-stu-id="b69b2-107">Writing a Thread-Safe Functoid</span></span>  
 <span data-ttu-id="b69b2-108">Functoid のコードは、ストレス条件下で、マップの複数のインスタンスを同時に実行される可能性がありますので、スレッド セーフにすることがあります。</span><span class="sxs-lookup"><span data-stu-id="b69b2-108">The functoid code must be thread-safe because under stress conditions multiple instances of a map may be running concurrently.</span></span> <span data-ttu-id="b69b2-109">注意事項をいくつか挙げます。</span><span class="sxs-lookup"><span data-stu-id="b69b2-109">Some of the points to remember include:</span></span>  
  
- <span data-ttu-id="b69b2-110">静的状態は、スレッド セーフである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b69b2-110">Static state must be thread-safe.</span></span>  
  
- <span data-ttu-id="b69b2-111">インスタンスの状態は、スレッド セーフであることを常には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b69b2-111">Instance state does not always need to be thread-safe.</span></span>  
  
- <span data-ttu-id="b69b2-112">高いストレス条件下で実行するための考慮事項を使用してデザインします。</span><span class="sxs-lookup"><span data-stu-id="b69b2-112">Design with consideration for running under high-stress conditions.</span></span> <span data-ttu-id="b69b2-113">可能であれば、ロックの取得を回避します。</span><span class="sxs-lookup"><span data-stu-id="b69b2-113">Avoid taking locks whenever possible.</span></span>  
  
- <span data-ttu-id="b69b2-114">同期の必要性をできる限り避けます。</span><span class="sxs-lookup"><span data-stu-id="b69b2-114">Avoid the need for synchronization if possible.</span></span>  
  
  <span data-ttu-id="b69b2-115">BizTalk Server では、スレッド セーフの累積 functoid の作成の複雑さを軽減する単純なメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="b69b2-115">BizTalk Server provides a simple mechanism to reduce the complexity of writing a thread-safe cumulative functoid.</span></span> <span data-ttu-id="b69b2-116">3 つの関数では、同じ最初のパラメーターを整数インデックス値があります。</span><span class="sxs-lookup"><span data-stu-id="b69b2-116">All three functions have the same first parameter, an integer index value.</span></span> <span data-ttu-id="b69b2-117">BizTalk Server は、初期化関数を呼び出すときに、インデックス値に一意の番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b69b2-117">BizTalk Server assigns a unique number to the index value when it calls your initialization function.</span></span> <span data-ttu-id="b69b2-118">この値は、次のコードに示すように、累積値を格納する配列インデックスとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="b69b2-118">You can use this value as an index into an array that holds accumulating values, as shown in the following code:</span></span>  
  
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
  
 <span data-ttu-id="b69b2-119">この例では、ArrayList の代わりに、ハッシュ テーブルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b69b2-119">This example uses a HashTable instead of an ArrayList.</span></span> <span data-ttu-id="b69b2-120">これは、初期化関数を順番にインデックス値を持つ呼び出されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="b69b2-120">This is because the initialization function might not be called with in-order index values.</span></span>  
  
## <a name="implementing-the-three-cumulative-functions"></a><span data-ttu-id="b69b2-121">次の 3 つの累積的な関数の実装</span><span class="sxs-lookup"><span data-stu-id="b69b2-121">Implementing the Three Cumulative Functions</span></span>  
 <span data-ttu-id="b69b2-122">各カスタムの累積 functoid を開発するための 3 つの関数を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b69b2-122">You will need to implement three functions for each custom cumulative functoid you develop.</span></span> <span data-ttu-id="b69b2-123">関数とそれらを設定するコンス トラクターで呼び出す必要があるメソッドは、次の表にまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="b69b2-123">The functions and the methods you must call in the constructor to set them are summarized in the following table.</span></span> <span data-ttu-id="b69b2-124">すべての関数は、文字列値を返します。</span><span class="sxs-lookup"><span data-stu-id="b69b2-124">All of the functions return string values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b69b2-125">各関数の場合、わかりやすい名前を決定するが、各関数は、指定された引数の種類と数をいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b69b2-125">You determine the best name for each function, but each function must have the number and type of arguments specified.</span></span>  
  
|<span data-ttu-id="b69b2-126">関数の目的</span><span class="sxs-lookup"><span data-stu-id="b69b2-126">Function Purpose</span></span>|<span data-ttu-id="b69b2-127">引数</span><span class="sxs-lookup"><span data-stu-id="b69b2-127">Arguments</span></span>|<span data-ttu-id="b69b2-128">参照を設定するには</span><span class="sxs-lookup"><span data-stu-id="b69b2-128">To set a reference</span></span>|<span data-ttu-id="b69b2-129">インライン スクリプトを設定するには</span><span class="sxs-lookup"><span data-stu-id="b69b2-129">To set inline script</span></span>|  
|----------------------|---------------|------------------------|--------------------------|  
|<span data-ttu-id="b69b2-130">初期化</span><span class="sxs-lookup"><span data-stu-id="b69b2-130">Initialization</span></span>|<span data-ttu-id="b69b2-131">**int インデックス**</span><span class="sxs-lookup"><span data-stu-id="b69b2-131">**int index**</span></span>|<span data-ttu-id="b69b2-132">**SetExternalFunctionName**</span><span class="sxs-lookup"><span data-stu-id="b69b2-132">**SetExternalFunctionName**</span></span>|<span data-ttu-id="b69b2-133">**SetScriptBuffer**で`functionNumber`= 0</span><span class="sxs-lookup"><span data-stu-id="b69b2-133">**SetScriptBuffer** with `functionNumber` = 0</span></span>|  
|<span data-ttu-id="b69b2-134">累計</span><span class="sxs-lookup"><span data-stu-id="b69b2-134">Cumulation</span></span>|<span data-ttu-id="b69b2-135">**int インデックス、val、文字列の範囲の文字列**</span><span class="sxs-lookup"><span data-stu-id="b69b2-135">**int index, string val, string scope**</span></span>|<span data-ttu-id="b69b2-136">**SetExternalFunctionName2**</span><span class="sxs-lookup"><span data-stu-id="b69b2-136">**SetExternalFunctionName2**</span></span>|<span data-ttu-id="b69b2-137">**SetScriptBuffer**で`functionNumber`= 1</span><span class="sxs-lookup"><span data-stu-id="b69b2-137">**SetScriptBuffer** with `functionNumber` = 1</span></span>|  
|<span data-ttu-id="b69b2-138">取得</span><span class="sxs-lookup"><span data-stu-id="b69b2-138">Get</span></span>|<span data-ttu-id="b69b2-139">**int インデックス**</span><span class="sxs-lookup"><span data-stu-id="b69b2-139">**int index**</span></span>|<span data-ttu-id="b69b2-140">**SetExternalFunctionName3**</span><span class="sxs-lookup"><span data-stu-id="b69b2-140">**SetExternalFunctionName3**</span></span>|<span data-ttu-id="b69b2-141">**SetScriptBuffer**で`functionNumber`= 2</span><span class="sxs-lookup"><span data-stu-id="b69b2-141">**SetScriptBuffer** with `functionNumber` = 2</span></span>|  
  
### <a name="initialization"></a><span data-ttu-id="b69b2-142">初期化</span><span class="sxs-lookup"><span data-stu-id="b69b2-142">Initialization</span></span>  
 <span data-ttu-id="b69b2-143">初期化では、累積の実行に使用するメカニズムを準備することができます。</span><span class="sxs-lookup"><span data-stu-id="b69b2-143">Initialization enables you to prepare the mechanisms you will use to perform accumulation.</span></span> <span data-ttu-id="b69b2-144">配列を初期化、1 つまたは複数の値をリセット、または必要に応じてその他のリソースを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="b69b2-144">You can initialize an array, reset one or more values, or load other resources as needed.</span></span> <span data-ttu-id="b69b2-145">文字列の戻り値は使用されません。</span><span class="sxs-lookup"><span data-stu-id="b69b2-145">The string return value is not used.</span></span>  
  
### <a name="cumulation"></a><span data-ttu-id="b69b2-146">累計</span><span class="sxs-lookup"><span data-stu-id="b69b2-146">Cumulation</span></span>  
 <span data-ttu-id="b69b2-147">これは、functoid の累積操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b69b2-147">This is where you perform the accumulation operation appropriate for your functoid.</span></span> <span data-ttu-id="b69b2-148">BizTalk Server は、次の 3 つのパラメーターで渡されます。</span><span class="sxs-lookup"><span data-stu-id="b69b2-148">BizTalk Server passes in the following three parameters:</span></span>  
  
- <span data-ttu-id="b69b2-149">**インデックス。**</span><span class="sxs-lookup"><span data-stu-id="b69b2-149">**Index.**</span></span> <span data-ttu-id="b69b2-150">マップのインスタンスを表す整数値。</span><span class="sxs-lookup"><span data-stu-id="b69b2-150">An integer value representing a map instance.</span></span> <span data-ttu-id="b69b2-151">同時に実行されている複数のマップのインスタンスである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b69b2-151">There may be multiple map instances running concurrently.</span></span>  
  
- <span data-ttu-id="b69b2-152">**Val します。**</span><span class="sxs-lookup"><span data-stu-id="b69b2-152">**Val.**</span></span> <span data-ttu-id="b69b2-153">累積する値を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="b69b2-153">A string containing the value that should be accumulated.</span></span> <span data-ttu-id="b69b2-154">文字列の累積 functoid を記述する場合を除き、数値の値になります。</span><span class="sxs-lookup"><span data-stu-id="b69b2-154">Unless you are writing a string Cumulate functoid it is a numeric value.</span></span>  
  
- <span data-ttu-id="b69b2-155">**スコープ。**</span><span class="sxs-lookup"><span data-stu-id="b69b2-155">**Scope.**</span></span> <span data-ttu-id="b69b2-156">要素または属性値を示す数値を含む文字列を累積する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b69b2-156">A string containing a number indicating which element or attribute value should be accumulated.</span></span> <span data-ttu-id="b69b2-157">実際の値は、実装によって決まります。</span><span class="sxs-lookup"><span data-stu-id="b69b2-157">Actual values are determined by an implementation.</span></span>  
  
  <span data-ttu-id="b69b2-158">累積する値を指定し、どの値を無視するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="b69b2-158">You decide which values to accumulate and which values to ignore.</span></span> <span data-ttu-id="b69b2-159">たとえば、0 未満ではない値を無視できます。 ただし、値が数値ではありませんが、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="b69b2-159">For example, you may ignore values that are not below 0 but throw an exception when a value is not numeric.</span></span> <span data-ttu-id="b69b2-160">**BaseFunctoid**関数を 2 つ提供:**IsDate**と**IsNumeric**-検証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b69b2-160">**BaseFunctoid** supplies two functions—**IsDate** and **IsNumeric**—to assist with validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b69b2-161">使用する場合**IsDate**または**IsNumeric**をインライン スクリプトで設定することを確認する**RequiredGlobalHelperFunctions**関数、スクリプトで利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b69b2-161">If you use **IsDate** or **IsNumeric** in an inline script, be sure to set **RequiredGlobalHelperFunctions** so that the functions are made available to your script.</span></span>  
  
 <span data-ttu-id="b69b2-162">文字列の戻り値は使用されません。</span><span class="sxs-lookup"><span data-stu-id="b69b2-162">The string return value is not used.</span></span>  
  
### <a name="get"></a><span data-ttu-id="b69b2-163">取得</span><span class="sxs-lookup"><span data-stu-id="b69b2-163">Get</span></span>  
 <span data-ttu-id="b69b2-164">BizTalk Server では、マップの functoid の設定によって決定される値のすべての反復が完了すると、累積値を要求します。</span><span class="sxs-lookup"><span data-stu-id="b69b2-164">When BizTalk Server finishes iterating through all of the values determined by the functoid settings in the map, it requests the accumulated value.</span></span> <span data-ttu-id="b69b2-165">Get 関数が 1 つの引数`Index`をマップのインスタンスを表す整数値です。</span><span class="sxs-lookup"><span data-stu-id="b69b2-165">The get function has one argument, `Index`, which is an integer value representing a map instance.</span></span> <span data-ttu-id="b69b2-166">関数は、インデックス値を使用して、検索して、文字列としての累積値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b69b2-166">Your function should use the index value to find and return the accumulated value as a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b69b2-167">例</span><span class="sxs-lookup"><span data-stu-id="b69b2-167">Example</span></span>  
 <span data-ttu-id="b69b2-168">次の例では、累積乗算を実行するためのカスタム functoid を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b69b2-168">The following example illustrates how to create a custom functoid for performing cumulative multiplication.</span></span> <span data-ttu-id="b69b2-169">ここでは、3 つの文字列リソースと 16x16 ピクセルのビットマップ リソースが格納されたリソース ファイルがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b69b2-169">It relies on a resource file containing three string resources and a 16x16-pixel bitmap resource.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b69b2-170">参照</span><span class="sxs-lookup"><span data-stu-id="b69b2-170">See Also</span></span>  
 <span data-ttu-id="b69b2-171">[BaseFunctoid の使用](../core/using-basefunctoid.md) </span><span class="sxs-lookup"><span data-stu-id="b69b2-171">[Using BaseFunctoid](../core/using-basefunctoid.md) </span></span>  
 <span data-ttu-id="b69b2-172">[インラインのカスタム Functoid の開発](../core/developing-a-custom-inline-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="b69b2-172">[Developing a Custom Inline Functoid](../core/developing-a-custom-inline-functoid.md) </span></span>  
 [<span data-ttu-id="b69b2-173">カスタム Functoid (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="b69b2-173">Custom Functoid (BizTalk Server Sample)</span></span>](../core/custom-functoid-biztalk-server-sample.md)