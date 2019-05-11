---
title: 実装する、マネージ ストリーミング パイプライン コンポーネントでの Seek メソッド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline interfaces, IStream interface
- pipeline components [custom], code samples
- IStream interface
- Seek method
ms.assetid: 2e546c41-822d-4e22-a8f6-8959072ef3d2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9986f2c19a1966d50e267ad8f10181d081be58dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382639"
---
# <a name="implementing-a-seek-method-in-a-managed-streaming-pipeline-component"></a><span data-ttu-id="838e0-102">実装する、マネージ ストリーミング パイプライン コンポーネントでの Seek メソッド</span><span class="sxs-lookup"><span data-stu-id="838e0-102">Implementing a Seek Method in a Managed Streaming Pipeline Component</span></span>
<span data-ttu-id="838e0-103">ネイティブ**IStream**インターフェイスは、メッセージング エンジンは、次のように、現在のストリームの位置をチェックするメソッドを提供していない**シーク**メソッド。</span><span class="sxs-lookup"><span data-stu-id="838e0-103">The native **IStream** interface does not provide a method to check the current stream position, so the messaging engine uses the following **Seek** method.</span></span>  
  
```  
pStream->Seek(0, STREAM_SEEK_CUR, &pNewPosition);  
```  
  
 <span data-ttu-id="838e0-104">このメソッドはストリーム ポインターを移動しません代わりに、現在の位置を照会します。</span><span class="sxs-lookup"><span data-stu-id="838e0-104">This method does not move the stream pointer; instead it queries the current position.</span></span> <span data-ttu-id="838e0-105">使用できる場合は、シークできないストリームで動作するパイプライン コンポーネントを実装するように、 **Stream.Seek**次の例のようにメソッド。</span><span class="sxs-lookup"><span data-stu-id="838e0-105">So if you implement a pipeline component that works with a nonseekable stream, you can use the **Stream.Seek** method as in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="838e0-106">例</span><span class="sxs-lookup"><span data-stu-id="838e0-106">Example</span></span>  
  
```csharp  
override public long Seek(long offset, SeekOrigin origin)  
{  
   long pos = -1;  
  
   switch(origin)  
   {  
      case SeekOrigin.Begin :  
         pos = offset;  
         break;  
      case SeekOrigin.Current :  
         pos = Position + offset;  
         break;  
      case SeekOrigin.End :  
         break;  
   }  
  
   // We generally disallow seeking of the stream  
   // However, in unmanaged code, many people use Seek(0,CURR) to retrieve    // the current position  
   // Special case (that is, if Seek does not change position, do not   
   // throw an exception)  
   if (pos==Position)  
   {  
      return pos;  
   }  
   else  
   {  
      throw new NotSupportedException("ForwardOnlyEventingReadStream does not support Seek()");  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="838e0-107">参照</span><span class="sxs-lookup"><span data-stu-id="838e0-107">See Also</span></span>  
 [<span data-ttu-id="838e0-108">カスタム パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="838e0-108">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)