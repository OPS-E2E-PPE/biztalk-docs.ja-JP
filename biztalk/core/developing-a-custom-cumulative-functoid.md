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
# <a name="developing-a-custom-cumulative-functoid"></a>カスタムの累積 Functoid の開発
カスタムの累積 functoid を使用すると、インスタンス メッセージ内で複数回に発生する値の累積処理を実行できます。  
  
 累積 functoid を開発する際に、3 つの関数を実装する必要があります。 3 つの関数は、初期化操作、累積操作に対応し、マップが、累積したものを実行する必要があるアクションを取得します。 これらの関数を説明する前にすることが重要スレッド セーフについて説明します。  
  
## <a name="writing-a-thread-safe-functoid"></a>スレッド セーフ Functoid の作成  
 Functoid のコードは、ストレス条件下で、マップの複数のインスタンスを同時に実行される可能性がありますので、スレッド セーフにすることがあります。 注意事項をいくつか挙げます。  
  
- 静的状態は、スレッド セーフである必要があります。  
  
- インスタンスの状態は、スレッド セーフであることを常には必要ありません。  
  
- 高いストレス条件下で実行するための考慮事項を使用してデザインします。 可能であれば、ロックの取得を回避します。  
  
- 同期の必要性をできる限り避けます。  
  
  BizTalk Server では、スレッド セーフの累積 functoid の作成の複雑さを軽減する単純なメカニズムを提供します。 3 つの関数では、同じ最初のパラメーターを整数インデックス値があります。 BizTalk Server は、初期化関数を呼び出すときに、インデックス値に一意の番号を割り当てます。 この値は、次のコードに示すように、累積値を格納する配列インデックスとして使用できます。  
  
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
  
 この例では、ArrayList の代わりに、ハッシュ テーブルを使用します。 これは、初期化関数を順番にインデックス値を持つ呼び出されない場合があります。  
  
## <a name="implementing-the-three-cumulative-functions"></a>次の 3 つの累積的な関数の実装  
 各カスタムの累積 functoid を開発するための 3 つの関数を実装する必要があります。 関数とそれらを設定するコンス トラクターで呼び出す必要があるメソッドは、次の表にまとめたものです。 すべての関数は、文字列値を返します。  
  
> [!NOTE]
>  各関数の場合、わかりやすい名前を決定するが、各関数は、指定された引数の種類と数をいる必要があります。  
  
|関数の目的|引数|参照を設定するには|インライン スクリプトを設定するには|  
|----------------------|---------------|------------------------|--------------------------|  
|初期化|**int インデックス**|**SetExternalFunctionName**|**SetScriptBuffer**で`functionNumber`= 0|  
|累計|**int インデックス、val、文字列の範囲の文字列**|**SetExternalFunctionName2**|**SetScriptBuffer**で`functionNumber`= 1|  
|取得|**int インデックス**|**SetExternalFunctionName3**|**SetScriptBuffer**で`functionNumber`= 2|  
  
### <a name="initialization"></a>初期化  
 初期化では、累積の実行に使用するメカニズムを準備することができます。 配列を初期化、1 つまたは複数の値をリセット、または必要に応じてその他のリソースを読み込むことができます。 文字列の戻り値は使用されません。  
  
### <a name="cumulation"></a>累計  
 これは、functoid の累積操作を実行します。 BizTalk Server は、次の 3 つのパラメーターで渡されます。  
  
- **インデックス。** マップのインスタンスを表す整数値。 同時に実行されている複数のマップのインスタンスである可能性があります。  
  
- **Val します。** 累積する値を含む文字列。 文字列の累積 functoid を記述する場合を除き、数値の値になります。  
  
- **スコープ。** 要素または属性値を示す数値を含む文字列を累積する必要があります。 実際の値は、実装によって決まります。  
  
  累積する値を指定し、どの値を無視するかを決定します。 たとえば、0 未満ではない値を無視できます。 ただし、値が数値ではありませんが、例外をスローします。 **BaseFunctoid**関数を 2 つ提供:**IsDate**と**IsNumeric**-検証をサポートします。  
  
> [!NOTE]
>  使用する場合**IsDate**または**IsNumeric**をインライン スクリプトで設定することを確認する**RequiredGlobalHelperFunctions**関数、スクリプトで利用できるようにします。  
  
 文字列の戻り値は使用されません。  
  
### <a name="get"></a>取得  
 BizTalk Server では、マップの functoid の設定によって決定される値のすべての反復が完了すると、累積値を要求します。 Get 関数が 1 つの引数`Index`をマップのインスタンスを表す整数値です。 関数は、インデックス値を使用して、検索して、文字列としての累積値を返す必要があります。  
  
## <a name="example"></a>例  
 次の例では、累積乗算を実行するためのカスタム functoid を作成する方法を示します。 ここでは、3 つの文字列リソースと 16x16 ピクセルのビットマップ リソースが格納されたリソース ファイルがあることを前提としています。  
  
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