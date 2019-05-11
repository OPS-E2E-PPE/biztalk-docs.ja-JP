---
title: パイプライン コンポーネントの開発、アセンブル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IComponentUI interface, assembling
- IBaseComponent interface, assembling
- pipeline interfaces, IBaseComponent
- pipeline components [custom], interfaces
- pipeline interfaces, IComponentUI
- IAssemblerComponent interface, assembling
- pipeline interfaces, IAssemblerComponent
- pipeline components [custom], assembling
ms.assetid: 2f85421d-2010-4a36-82b5-ea8016f8aa99
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff36bac9dc5f14048e7d448f912f72c243146b8a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389434"
---
# <a name="developing-an-assembling-pipeline-component"></a><span data-ttu-id="9633c-102">アセンブラー パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="9633c-102">Developing an Assembling Pipeline Component</span></span>
<span data-ttu-id="9633c-103">アセンブラー パイプライン コンポーネントは、.NET または COM コンポーネントの入力に複数のメッセージを受信し、出力の 1 つのメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="9633c-103">An assembling pipeline component is a .NET or COM component that receives several messages on input and produces one message on output.</span></span> <span data-ttu-id="9633c-104">アセンブラー コンポーネントは、メッセージのインターチェンジ バッチに個々 のドキュメントを収集するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9633c-104">Assembling components are used to collect individual documents into the message interchange batch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9633c-105">アセンブリの機能は使用されていないため、常に、BizTalk Server は、コンポーネントの入力を 1 つのドキュメントを渡します。</span><span class="sxs-lookup"><span data-stu-id="9633c-105">Assembly functionality is not used, so BizTalk Server always passes one document to the component input.</span></span>  
  
 <span data-ttu-id="9633c-106">アセンブラー コンポーネントは、次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9633c-106">An assembling component must implement the following interfaces:</span></span>  
  
-   `IBaseComponent`  
  
-   `IAssemblerComponent`
  
-   `IComponentUI`
  
-   <span data-ttu-id="9633c-107">**IPersistPropertyBag します。**</span><span class="sxs-lookup"><span data-stu-id="9633c-107">**IPersistPropertyBag .**</span></span> <span data-ttu-id="9633c-108">このインターフェイスは .NET Framework SDK ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9633c-108">Refer to the .NET Framework SDK documentation for this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9633c-109">カスタム パイプライン コンポーネントは、出力メッセージ用に、入力メッセージからその他のパーツをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9633c-109">Custom pipeline components should copy any additional parts from the input message to the output message(s).</span></span> <span data-ttu-id="9633c-110">これはさらに、パイプラインで処理するためを保持します。</span><span class="sxs-lookup"><span data-stu-id="9633c-110">This preserves them for further processing in the pipeline.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9633c-111">参照</span><span class="sxs-lookup"><span data-stu-id="9633c-111">See Also</span></span>  
 <span data-ttu-id="9633c-112">[全般パイプライン コンポーネントの開発](../core/developing-a-general-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="9633c-112">[Developing a General Pipeline Component](../core/developing-a-general-pipeline-component.md) </span></span>  
 <span data-ttu-id="9633c-113">[逆アセンブラー パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="9633c-113">[Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="9633c-114">[プローブ パイプライン コンポーネントの開発](../core/developing-a-probing-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="9633c-114">[Developing a Probing Pipeline Component](../core/developing-a-probing-pipeline-component.md) </span></span>  
 <span data-ttu-id="9633c-115">[パイプライン コンポーネントからエラーの報告](../core/reporting-errors-from-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="9633c-115">[Reporting Errors from Pipeline Components](../core/reporting-errors-from-pipeline-components.md) </span></span>  
 <span data-ttu-id="9633c-116">[ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="9633c-116">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="9633c-117">[パイプライン コンポーネントの展開](../core/deploying-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="9633c-117">[Deploying Pipeline Components](../core/deploying-pipeline-components.md) </span></span>  
 [<span data-ttu-id="9633c-118">CustomComponent (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="9633c-118">CustomComponent (BizTalk Server Sample)</span></span>](../core/customcomponent-biztalk-server-sample.md)