---
title: 動的アダプターの DisplayUI メソッド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9183d2ee-4265-4fee-9d1d-7e2462d8ff37
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f64b6ca1a4f14f050a0d59344fe3233b55e88d74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389278"
---
# <a name="dynamic-adapter-displayui-method"></a>動的アダプターの DisplayUI メソッド
このメソッドで、 **IDynamicAdapterConfig**インターフェイスには、カスタム アダプターのカスタム ユーザー インターフェイスが表示されます。 これにより、ユーザーに表示して選択し、それを BizTalk プロジェクトに、選択したサービスに基づいて関連サポート ファイルをインポートできます。  
  
 ファイル アダプター内でコードを変更、 **displayUI**を受け入れるようにスキーマの種類を選択するためのカスタム ユーザー インターフェイス (UI) を作成する、AdapterManagement.cs ファイルのメソッド。 スキーマを選択した後は、適切な WSDL ファイルを選択します。  
  
 次のコードは、 **displayUI** AdapterManagement.cs ファイルのメソッド。  
  
```  
/// <summary>  
        /// Acquire wsdl(s) from which to build the user interface  
        /// </summary>  
        /// <param name="endPointConfiguration"></param>  
        /// <param name="owner"></param>  
        /// <param name="WSDLList">Array of custom UI's WSDL (returned)</param>  
        /// <returns></returns>  
        public Result DisplayUI(IPropertyBag endPointConfiguration,   
            IWin32Window owner,  
            out string [] WSDLList)   
      {  
            WSDLList = new string[1];  
            WSDLList[0] = GetResource("AdapterManagement.service1.wsdl");  
            return Result.Continue;  
        }  
```