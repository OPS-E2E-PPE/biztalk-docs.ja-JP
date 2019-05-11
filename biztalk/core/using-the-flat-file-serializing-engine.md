---
title: 使用して、フラット ファイルのシリアル化エンジン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- IFFDocumentSpec interface
- pipeline components [custom], flat file documents
- pipeline components [custom], engines
ms.assetid: 0a519f0f-392b-4fa3-ab08-f09012d033af
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9a854a440dda25c822b923f7ca17ef8e80ccc34
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396030"
---
# <a name="using-the-flat-file-serializing-engine"></a><span data-ttu-id="462bb-102">フラット ファイルをシリアル化エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="462bb-102">Using the Flat File Serializing Engine</span></span>
<span data-ttu-id="462bb-103">呼び出すことによって、フラット ファイル シリアル化エンジンが呼び出される、 **Serialize**のメソッド、 **IFFDocumentSpec**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="462bb-103">The flat file serializing engine is invoked by calling the **Serialize** method of the **IFFDocumentSpec** interface.</span></span> <span data-ttu-id="462bb-104">により、カスタマイズされた**XmlReader**メソッドの引数としては、最後のデータをシリアル化を制御できます。</span><span class="sxs-lookup"><span data-stu-id="462bb-104">By providing a customized **XmlReader** as the argument to the method, you can control the final data that gets serialized.</span></span> <span data-ttu-id="462bb-105">任意の形式でデータ可能性があります。 または単に作成できませんでした、リーダーの xmldocument です。</span><span class="sxs-lookup"><span data-stu-id="462bb-105">Data could be in any format, or could simply be a reader created of off an XmlDocument.</span></span>  
  
## <a name="example"></a><span data-ttu-id="462bb-106">例</span><span class="sxs-lookup"><span data-stu-id="462bb-106">Example</span></span>  
  
```  
Stream stm = docspec.Serialize(new MyXmlReader(originalXmlReader), Encoding.Unicode);  
```  
  
## <a name="see-also"></a><span data-ttu-id="462bb-107">参照</span><span class="sxs-lookup"><span data-stu-id="462bb-107">See Also</span></span>  
 <span data-ttu-id="462bb-108">[Microsoft.BizTalk.Component.Interop.IFFDocumentSpec](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.iffdocumentspec.aspx) </span><span class="sxs-lookup"><span data-stu-id="462bb-108">[Microsoft.BizTalk.Component.Interop.IFFDocumentSpec](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.iffdocumentspec.aspx) </span></span>  
 [<span data-ttu-id="462bb-109">フラット ファイル解析エンジンの使用</span><span class="sxs-lookup"><span data-stu-id="462bb-109">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)