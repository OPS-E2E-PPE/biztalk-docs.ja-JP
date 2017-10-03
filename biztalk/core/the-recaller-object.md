---
title: "Recaller オブジェクト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Recaller object
- Invoke method
- process management solution tutorial, Recaller object
- process management solution tutorial, errors
ms.assetid: b30ad1ae-475f-4913-b402-4d3263fcf072
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 731f7703eb9145b1249872902d0b867fe22622ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-recaller-object"></a>Recaller オブジェクト
ビジネス プロセス管理ソリューションでは、失敗したオブジェクト メソッドの呼び出しが、汎用的な方法で再試行できます。 このソリューションは、 **Recaller**内のオブジェクト、 **ExceptionHandler**オーケストレーションです。 **ExceptionHandler**オーケストレーションでは、オブジェクトを使用して、オブジェクト メソッドの呼び出しを再試行してください。 詳細については、次を参照してください。 [ExceptionHandler Orchestration](../core/the-exceptionhandler-orchestration.md)です。  
  
## <a name="the-invoke-method"></a>Invoke メソッド  
 **Recaller**オブジェクトが 1 つの静的メソッド**Invoke**です。 インスタンスを作成する必要が静的であるためありません、 **Recaller**オブジェクト。 使用することができます、 **Invoke**メソッドを次の 3 つの方法で: メソッドを呼び出す、静的オブジェクト、またはオブジェクトの非静的メソッドを呼び出す、オブジェクトを構築します。  
  
> [!NOTE]
>  **Invoke**メソッドのラッパーとして機能、 **Type.InvokeMember**メソッドで、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]クラス ライブラリです。  
  
### <a name="arguments-for-the-invoke-method"></a>Invoke メソッドの引数  
 次の表の引数、 **Invoke**メソッド。  
  
|パラメーター|型|Description|  
|---------------|----------|-----------------|  
|*t*|**型**|呼び出されるメソッドがあるオブジェクトのデータ型|  
|*obj*|**オブジェクト**|使用するオブジェクトのインスタンス|  
|*methodName*|**string**|呼び出すメソッドの名前です。|  
|*args*|**配列**|型の配列**オブジェクト**メソッドの引数を格納します。|  
  
 オブジェクトのコンス トラクターを呼び出しするには、空の文字列 ("") または**null**の*methodName*です。  
  
 静的メソッドを呼び出すには、次のように使用します。 **null**の*obj*です。  
  
 非静的メソッドを呼び出すには、すべての引数に値を指定します。  
  
> [!NOTE]
>  使用して**null**型引数の値として*t*、により**Invoke**をスローする、 **ArgumentNullException**例外。 引数*t* null は使用できませんので、 **Invoke**メソッドを使用、 **Type.InvokeMember** [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]メソッドです。  
  
## <a name="calling-invoke"></a>Invoke の呼び出し  
 ソリューションでは、のみ、 **ExceptionHandler**オーケストレーションは、 **Recaller**オブジェクト。 **ExceptionHandler** 、さらに、他のオーケストレーションで使用します。 渡される値、 **Invoke**メソッドでは、他のオーケストレーションをこれらからに取得します。 たとえば、次のコードが、 **Activate**でオーケストレーション、 **InitialException**式図形。  
  
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
  
 コードが使用して、配列を作成する方法に注意してください。 **System.Array.CreateInstance**を使用して、 **SetValue**メソッド内で使用される値を格納します。  
  
 式図形後、Activate オーケストレーションを呼び出して、 **ExceptionHandler**オーケストレーションです。 次のコードはオーケストレーション デザイナが呼び出し図形をどのように変換するかを示します。  
  
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
  
 引数名は Activate オーケストレーションからの呼び出しで使用されているものに一致しますが、オーケストレーションを呼び出すとき、引数の照合は名前ではなく順序によって行われることに注意してください。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [ExceptionHandler オーケストレーション](../core/the-exceptionhandler-orchestration.md)