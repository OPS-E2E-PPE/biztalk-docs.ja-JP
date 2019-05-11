---
title: Recaller オブジェクト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Recaller object
- Invoke method
- process management solution tutorial, Recaller object
- process management solution tutorial, errors
ms.assetid: b30ad1ae-475f-4913-b402-4d3263fcf072
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15ad2868892f0190cb9ebf8c63dfd6e3df200505
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394062"
---
# <a name="the-recaller-object"></a>Recaller オブジェクト
再試行するには、ビジネス プロセス管理ソリューションを提供します、一般的ないくつかが失敗オブジェクト メソッドの呼び出し。 ソリューションはこれを**Recaller**オブジェクト、 **ExceptionHandler**オーケストレーションします。 **ExceptionHandler**オーケストレーションでは、オブジェクトを使用して、オブジェクト メソッドの呼び出しを再試行してください。 詳細については、次を参照してください。 [、ExceptionHandler オーケストレーション](../core/the-exceptionhandler-orchestration.md)します。  
  
## <a name="the-invoke-method"></a>メソッドを呼び出す  
 **Recaller**オブジェクトが 1 つの静的メソッドでは、 **Invoke**します。 決してのインスタンスを作成する必要がありますには、静的であるため、 **Recaller**オブジェクト。 使用することができます、 **Invoke**メソッドで 3 つの方法: オブジェクトは、静的メソッドを呼び出す、またはオブジェクトの非静的メソッドを呼び出す、オブジェクトを構築します。  
  
> [!NOTE]
>  **Invoke**メソッドのラッパーとして機能、 **Type.InvokeMember**メソッドで、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]クラス ライブラリ。  
  
### <a name="arguments-for-the-invoke-method"></a>引数、メソッドを呼び出す  
 次の表に、引数、 **Invoke**メソッド。  
  
|パラメーター|型|説明|  
|---------------|----------|-----------------|  
|*t*|**型**|メソッドを呼び出す対象となるオブジェクトの型。|  
|*obj*|**Object**|使用するオブジェクトのインスタンス。|  
|*methodName*|**string**|呼び出すメソッドの名前。|  
|*引数*|**配列**|型の配列**オブジェクト**メソッドの引数を格納しています。|  
  
 オブジェクトのコンス トラクターを呼び出す、空の文字列を使用して、("") または**null**の*methodName*します。  
  
 静的メソッドを呼び出すには、次のように使用します。 **null**の*obj*します。  
  
 非静的メソッドを呼び出すには、すべての引数を指定します。  
  
> [!NOTE]
>  使用して**null**型引数の値として*t*、により**Invoke**をスローする、 **ArgumentNullException**例外。 引数*t*は null にできませんので、 **Invoke**メソッドは、 **Type.InvokeMember** [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]メソッド。  
  
## <a name="calling-invoke"></a>Invoke の呼び出し  
 のみのソリューションで、 **ExceptionHandler**オーケストレーションは、 **Recaller**オブジェクト。 **ExceptionHandler** 、さらに、他のオーケストレーションで使用します。 渡される値、 **Invoke**メソッドでは、他のオーケストレーションをこれらからに取得します。 たとえば、次のコードが、 **Activate**でオーケストレーション、 **InitialException**式図形。  
  
```  
Ex = CodeEx;  
ObjectType = orderHandler.GetType();  
CalledObject = orderHandler;  
Reason = "Standard Activate Failed";  
MethodName = "Activate";  
ParameterArray = System.Array.CreateInstance(typeof(System.Object),  
                                              3 );  
ParameterArray.SetValue(ServiceType, 0);  
ParameterArray.SetValue(OrderMsg.CustNum, 1);  
ParameterArray.SetValue(OrderMsg.OrderNum, 2);  
ReturnValue = null; // no return value expected  
  
```  
  
 コードを使用して、配列を作成する方法に注意してください。 **System.Array.CreateInstance**を使用して、 **SetValue** 、で使用する値を格納する方法。  
  
 式図形の後、Activate オーケストレーションを呼び出して、 **ExceptionHandler**オーケストレーションします。 次のコードは、オーケストレーション デザイナーでの呼び出し図形を変換する方法を示しています。  
  
```  
call Microsoft.Samples.  
    BizTalk.SouthridgeVideo.  
        OrderManager.ExceptionHandlerOrch  
            (  
                Reason,  
                Ex,  
                CalledObject,  
                MethodName,   
                ParameterArray,   
                OrderCorrelation,   
                OrderMsg,   
                out ReturnValue,   
                ObjectType  
            );  
  
```  
  
 **ExceptionHandler**オーケストレーションでは、次のコードが、 **Call Original Code**式図形。  
  
```  
ReturnValue =   
    Microsoft.Samples.  
        BizTalk.SouthridgeVideo.  
            Utilities.Recaller.  
                Invoke(  
                    ObjectType,  
                    CalledObject,  
                    MethodName,  
                    ParameterArray  
                );  
```  
  
 、Activate オーケストレーションからの呼び出しで引数名に合わせて、は引数が一致することによって順序と名前ではなくオーケストレーションを呼び出すときに注意してください。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [ExceptionHandler オーケストレーション](../core/the-exceptionhandler-orchestration.md)