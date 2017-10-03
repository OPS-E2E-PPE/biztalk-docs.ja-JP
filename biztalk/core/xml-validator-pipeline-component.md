---
title: "XML 検証パイプライン コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Validator [pipeline component]
- pipeline components, XML Validator
ms.assetid: b383c222-1c8f-451a-a296-72af21a4ef6a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78effccc78846c059626897545a4d916c2d6630f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="xml-validator-pipeline-component"></a><span data-ttu-id="cb657-102">XML 検証パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cb657-102">XML Validator Pipeline Component</span></span>
<span data-ttu-id="cb657-103">XML 検証パイプライン コンポーネントは、逆アセンブル ステージとアセンブル ステージを除く、送信パイプラインおよび受信パイプラインのすべてのステージで使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb657-103">The XML Validator pipeline component can be used in both send and receive pipelines in any stage except for Disassemble or Assemble.</span></span> <span data-ttu-id="cb657-104">XML 検証コンポーネントでは、指定されたスキーマと照合してメッセージが検証されます。メッセージが、指定されたスキーマに準拠していなかった場合、XML 検証コンポーネントによってエラーが生成され、そのメッセージは、メッセージング エンジンにより保留キューに格納されます。</span><span class="sxs-lookup"><span data-stu-id="cb657-104">The XML Validator component validates the message against the specified schema or schemas, and if the message does not conform to these schemas, the component raises an error and Messaging Engine places the message in the suspended queue.</span></span>  
  
 <span data-ttu-id="cb657-105">XML 検証パイプライン コンポーネントの構成については、次を参照してください。 [XML 検証パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-validator-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="cb657-105">For information about configuring the XML Validator pipeline component, see [How to Configure the XML Validator Pipeline Component](../core/how-to-configure-the-xml-validator-pipeline-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb657-106">参照</span><span class="sxs-lookup"><span data-stu-id="cb657-106">See Also</span></span>  
 [<span data-ttu-id="cb657-107">パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cb657-107">Pipeline Components</span></span>](../core/pipeline-components.md)