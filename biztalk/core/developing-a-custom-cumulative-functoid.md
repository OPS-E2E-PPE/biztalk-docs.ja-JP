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
# <a name="developing-a-custom-cumulative-functoid"></a>カスタムの累積 Functoid の開発
カスタムの累積 Functoid を使用して、インスタンス メッセージ内で何度も発生する値の累積処理を行います。  
  
 累積 Functoid を開発する場合、3 つの関数を実装する必要があります。 3 つの関数とは、マップで累積を行う場合に必要となる、初期化操作、累積操作、および取得操作です。 これらの関数を検討する前に、スレッドの安全性を検討することが重要です。  
  
## <a name="writing-a-thread-safe-functoid"></a>スレッド セーフ Functoid の作成  
 この Functoid のコードは、ストレス条件下でマップの複数のインスタンスが同時に実行される場合があるので、スレッド セーフにする必要があります。 注意事項を次に示します。  
  
-   静的状態は、スレッド セーフであることが必要です。  
  
-   インスタンス状態は、必ずしもスレッド セーフである必要はありません。  
  
-   高いストレス条件下で実行されることを考慮してデザインします。 可能な場合、ロックの取得は避けます。  
  
-   可能な場合、同期の必要性を避けるようにします。  
  
 BizTalk Server では、単純なメカニズムを使用することによって、スレッド セーフの累積 Functoid を簡単に作成できます。 3 つのすべての関数は、最初のパラメーターが同じ (整数型のインデックス値) です。 BizTalk Server は、初期化関数を呼び出すとき、固有の数値をインデックス値に割り当てます。 この値は、次のコードに示すように、累積値を格納する配列用のインデックスとして使用できます。  
  
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
  
 この例では、ArrayList の代わりに HashTable が使用されています。 このため、初期化関数は、順番どおりのインデックス値で呼び出されない場合があります。  
  
## <a name="implementing-the-three-cumulative-functions"></a>3 つの累積関数の実装  
 開発するカスタムの累積 Functoid ごとに、3 つの関数を実装する必要があります。 コンストラクターで呼び出して設定する関数とメソッドを次の表に示します。 すべての関数は文字列の値を返します。  
  
> [!NOTE]
>  各関数に対して、わかりやすい名前を設定します。また、関数ごとに引数の数と種類を指定する必要があります。  
  
|関数の目的|引数|参照の設定|インライン スクリプトの設定|  
|----------------------|---------------|------------------------|--------------------------|  
|初期化|**int インデックス**|**SetExternalFunctionName**|**SetScriptBuffer**で`functionNumber`0 を =|  
|累計|**int val、文字列のスコープにインデックスを作成、**|**SetExternalFunctionName2**|**SetScriptBuffer**で`functionNumber`= 1|  
|取得|**int インデックス**|**SetExternalFunctionName3**|**SetScriptBuffer**で`functionNumber`= 2|  
  
### <a name="initialization"></a>初期化  
 初期化を行うと、累積の実行で使用するメカニズムを準備できます。 配列の初期化、1 つ以上の値の再設定、または必要に応じた他のリソースの読み込みを行うことができます。 文字列の戻り値は使用されません。  
  
### <a name="cumulation"></a>累計  
 この操作で、Functoid の累積処理を実行します。 BizTalk Server は次の 3 つのパラメーターを渡します。  
  
-   **インデックス。** マップのインスタンスを表す整数型の値です。 複数のマップのインスタンスが同時に実行される場合があります。  
  
-   **Val です。** 累積する値を含む文字列です。 文字列の累積 Functoid を記述していない場合は、数値が使用されます。  
  
-   **スコープです。** 累積する要素または属性を示す数値を含む文字列です。 実際の値は、実装によって決まります。  
  
 累積する値および無視する値を決めます。 たとえば、0 未満ではない値を無視し、値が数値ではない場合に例外をスローできます。 **BaseFunctoid**関数を 2 つ提供 —**IsDate**と**IsNumeric**— 検証を支援します。  
  
> [!NOTE]
>  使用する場合**IsDate**または**IsNumeric**インライン スクリプトでは設定を必ず**RequiredGlobalHelperFunctions**関数、スクリプトで利用できるようにします。  
  
 文字列の戻り値は使用されません。  
  
### <a name="get"></a>取得  
 マップの Functoid の設定によって定義された、すべての値の繰り返し処理が完了すると、BizTalk Server は、累積された値を要求します。 取得関数は、マップのインスタンスを表す整数型の値である引数 (`Index`) を 1 つ使用します。 関数では、インデックス値を使用して、累積された値を検索してから文字列として返します。  
  
## <a name="example"></a>例  
 乗算の累積を行うカスタム Functoid の作成方法を次に示します。 ここでは、3 つの文字列リソースと 16x16 ピクセルのビットマップ リソースが格納されたリソース ファイルがあることを前提としています。  
  
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
  
## <a name="see-also"></a>参照  
 [BaseFunctoid の使用](../core/using-basefunctoid.md)   
 [インラインのカスタム Functoid の開発](../core/developing-a-custom-inline-functoid.md)   
 [カスタム Functoid (BizTalk Server サンプル)](../core/custom-functoid-biztalk-server-sample.md)