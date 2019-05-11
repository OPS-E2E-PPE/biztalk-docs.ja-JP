---
title: 参照 Functoid、カスタムの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e26d726-240c-4dfc-baa2-77451b8dc6c5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9942af739bd0708f9b3cd4017eded7b3033770f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389438"
---
# <a name="developing-a-custom-referenced-functoid"></a><span data-ttu-id="1776f-102">参照 Functoid、カスタムの開発</span><span class="sxs-lookup"><span data-stu-id="1776f-102">Developing a Custom Referenced Functoid</span></span>
<span data-ttu-id="1776f-103">参照先のカスタム functoid は、マップにインラインの実装コードをコピーしないでください。</span><span class="sxs-lookup"><span data-stu-id="1776f-103">Custom referenced functoids do not copy implementation code inline into the map.</span></span> <span data-ttu-id="1776f-104">代わりに、アセンブリ、クラス、およびメソッドへの参照は、拡張オブジェクト ファイルが生成されたスタイル シートに関連付けられているし、実行時に呼び出さに配置されます。</span><span class="sxs-lookup"><span data-stu-id="1776f-104">Instead, a reference to the assembly, class, and method is placed in the extension object file associated with the generated style sheet and called at run time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1776f-105">例</span><span class="sxs-lookup"><span data-stu-id="1776f-105">Example</span></span>  
 <span data-ttu-id="1776f-106">次の例では、2 つの文字列を連結する場合のカスタム参照されている functoid を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1776f-106">The following example illustrates how to create a custom referenced functoid for concatenating two strings.</span></span> <span data-ttu-id="1776f-107">ここでは、3 つの文字列リソースと 16x16 ピクセルのビットマップ リソースが格納されたリソース ファイルがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="1776f-107">It relies on a resource file containing three string resources and a 16x16-pixel bitmap resource.</span></span>  
  
```  
using System;  
using Microsoft.BizTalk.BaseFunctoids;  
using System.Reflection;  
  
namespace Microsoft.Samples.BizTalk.CustomFunctoid  
{  
    /// <summary>  
    /// Performs a string concatenation through assembly referenced function. Assembly must be deployed with the BizTalk solution.  
    /// </summary>  
    public class CustomStringConcatFunctoid : BaseFunctoid  
    {  
        public CustomStringConcatFunctoid()  
            : base()  
        {  
            //ID for this functoid  
            this.ID = 6001;  
  
            // Resource assembly must be ProjectName.ResourceName if building with VS.Net  
            SetupResourceAssembly("Microsoft.Samples.BizTalk.CustomFunctoid.CustomFunctoidResources", Assembly.GetExecutingAssembly());  
  
            // Pass the resource ID names for functoid name, tooltip  
            // description and the 16x16 bitmap for the Map palette  
            SetName("IDS_CUSTOMSTRINGCONCATFUNCTOID_NAME");  
            SetTooltip("IDS_CUSTOMSTRINGCONCATFUNCTOID_TOOLTIP");  
            SetDescription("IDS_CUSTOMSTRINGCONCATFUNCTOID_DESCRIPTION");  
            SetBitmap("IDB_CUSTOMSTRINGCONCATFUNCTOID_BITMAP");  
  
            // Put this string handling function under the String   
            // Functoid tab in the Visual Studio toolbox for functoids  
            this.Category = FunctoidCategory.String;  
  
            // 2 required parameters, no optional parameters  
            this.SetMinParams(2);  
            this.SetMaxParams(2);  
  
            // Functoid accepts two inputs  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
  
            // Set the output connection type  
            this.OutputConnectionType = ConnectionType.AllExceptRecord;  
  
            // Set the function name that needs to be called  
            // when this functoid is invoked.  The resulting assembly  
            // must be present in the Global Assembly Cache  
            // to ensure its availability.  
            SetExternalFunctionName(GetType().Assembly.FullName, "Microsoft.Samples.BizTalk.CustomFunctoid.CustomStringConcatFunctoid", "ConCatStrings");  
        }  
  
        // This function is executed by BizTalk to do the concatenation  
        public string ConCatStrings(string val1, string val2)  
        {  
            return val2 + val1;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1776f-108">参照</span><span class="sxs-lookup"><span data-stu-id="1776f-108">See Also</span></span>  
 <span data-ttu-id="1776f-109">[BaseFunctoid の使用](../core/using-basefunctoid.md) </span><span class="sxs-lookup"><span data-stu-id="1776f-109">[Using BaseFunctoid](../core/using-basefunctoid.md) </span></span>  
 <span data-ttu-id="1776f-110">[インラインのカスタム Functoid の開発](../core/developing-a-custom-inline-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="1776f-110">[Developing a Custom Inline Functoid](../core/developing-a-custom-inline-functoid.md) </span></span>  
 <span data-ttu-id="1776f-111">[カスタムの累積 Functoid の開発](../core/developing-a-custom-cumulative-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="1776f-111">[Developing a Custom Cumulative Functoid](../core/developing-a-custom-cumulative-functoid.md) </span></span>  
 [<span data-ttu-id="1776f-112">カスタム Functoid (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="1776f-112">Custom Functoid (BizTalk Server Sample)</span></span>](../core/custom-functoid-biztalk-server-sample.md)