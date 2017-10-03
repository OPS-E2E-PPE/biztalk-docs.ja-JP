---
title: "使用して、フラット ファイルのシリアル化エンジン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- IFFDocumentSpec interface
- pipeline components [custom], flat file documents
- pipeline components [custom], engines
ms.assetid: 0a519f0f-392b-4fa3-ab08-f09012d033af
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb4f39f42c3513932b54a92946e448d821ee362a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-flat-file-serializing-engine"></a><span data-ttu-id="a4af8-102">フラット ファイルのシリアル化エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="a4af8-102">Using the Flat File Serializing Engine</span></span>
<span data-ttu-id="a4af8-103">フラット ファイルのシリアル化エンジンが呼び出すことによって呼び出される、 **Serialize**のメソッド、 **IFFDocumentSpec**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="a4af8-103">The flat file serializing engine is invoked by calling the **Serialize** method of the **IFFDocumentSpec** interface.</span></span> <span data-ttu-id="a4af8-104">により、カスタマイズされた**XmlReader**メソッドの引数、最後のデータをシリアル化を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="a4af8-104">By providing a customized **XmlReader** as the argument to the method, you can control the final data that gets serialized.</span></span> <span data-ttu-id="a4af8-105">データは任意の形式にできます。また、単純に XmlDocument で作成したデータ リーダーにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a4af8-105">Data could be in any format, or could simply be a reader created of off an XmlDocument.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4af8-106">例</span><span class="sxs-lookup"><span data-stu-id="a4af8-106">Example</span></span>  
  
```  
Stream stm = docspec.Serialize(new MyXmlReader(originalXmlReader), Encoding.Unicode);  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4af8-107">参照</span><span class="sxs-lookup"><span data-stu-id="a4af8-107">See Also</span></span>  
 <span data-ttu-id="a4af8-108">[Microsoft.BizTalk.Component.Interop.IFFDocumentSpec](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.iffdocumentspec.aspx) </span><span class="sxs-lookup"><span data-stu-id="a4af8-108">[Microsoft.BizTalk.Component.Interop.IFFDocumentSpec](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.iffdocumentspec.aspx) </span></span>  
 [<span data-ttu-id="a4af8-109">フラット ファイル解析エンジンの使用</span><span class="sxs-lookup"><span data-stu-id="a4af8-109">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)