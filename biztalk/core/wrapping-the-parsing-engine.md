---
title: 解析エンジンのラップ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], wrapping
- pipeline components [custom], code samples
ms.assetid: e00994de-bb86-40c0-a891-3f202147b5fe
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99d6960ba2f5f795a37bb336dab227f23eb12353
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288594"
---
# <a name="wrapping-the-parsing-engine"></a><span data-ttu-id="a26a6-102">解析エンジンのラップ</span><span class="sxs-lookup"><span data-stu-id="a26a6-102">Wrapping the Parsing Engine</span></span>
<span data-ttu-id="a26a6-103">独自に作成することができます**XmlReader**するリーダーを埋め込み、によって返される、**解析**メソッドし、カスタマイズを提供します。</span><span class="sxs-lookup"><span data-stu-id="a26a6-103">You can create your own **XmlReader** that embeds the reader returned by the **Parse** method and provides customization.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a26a6-104">例</span><span class="sxs-lookup"><span data-stu-id="a26a6-104">Example</span></span>  
  
```  
class MyXmlReader : XmlReader  
{  
   public MyXmlReader(XmlReader xr)  
   {  
      _xr = xr;  
   }  
  
   // Overrides XmlReader and provides customized functionality of _xr  
   // ...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a26a6-105">参照</span><span class="sxs-lookup"><span data-stu-id="a26a6-105">See Also</span></span>  
 [<span data-ttu-id="a26a6-106">フラット ファイル解析エンジンの使用</span><span class="sxs-lookup"><span data-stu-id="a26a6-106">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)