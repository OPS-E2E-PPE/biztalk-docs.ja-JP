---
title: パイプライン コンポーネントの開発、アセンブル |Microsoft ドキュメント
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
ms.openlocfilehash: 8de06a815e1c5a6bf71700ad373ae3f278b3a9a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239618"
---
# <a name="developing-an-assembling-pipeline-component"></a><span data-ttu-id="c734c-102">アセンブラー パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="c734c-102">Developing an Assembling Pipeline Component</span></span>
<span data-ttu-id="c734c-103">アセンブラー パイプライン コンポーネントは、入力時に複数のメッセージを受け取り、出力時に 1 通のメッセージを生成する .NET または COM コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="c734c-103">An assembling pipeline component is a .NET or COM component that receives several messages on input and produces one message on output.</span></span> <span data-ttu-id="c734c-104">アセンブラー コンポーネントは、個別のドキュメントをまとめてメッセージ インターチェンジのバッチを作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c734c-104">Assembling components are used to collect individual documents into the message interchange batch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c734c-105">アセンブリ機能は使用されていないため、BizTalk Server は常に 1 つのドキュメントをコンポーネントの入力として渡します。</span><span class="sxs-lookup"><span data-stu-id="c734c-105">Assembly functionality is not used, so BizTalk Server always passes one document to the component input.</span></span>  
  
 <span data-ttu-id="c734c-106">アセンブラー コンポーネントは次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c734c-106">An assembling component must implement the following interfaces:</span></span>  
  
-   `IBaseComponent`  
  
-   `IAssemblerComponent`
  
-   `IComponentUI`
  
-   <span data-ttu-id="c734c-107">**IPersistPropertyBag です。**</span><span class="sxs-lookup"><span data-stu-id="c734c-107">**IPersistPropertyBag .**</span></span> <span data-ttu-id="c734c-108">(このインターフェイスについては、.NET Framework SDK のドキュメントを参照してください)</span><span class="sxs-lookup"><span data-stu-id="c734c-108">Refer to the .NET Framework SDK documentation for this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c734c-109">カスタム パイプライン コンポーネントでは入力メッセージの追加部分を出力メッセージにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c734c-109">Custom pipeline components should copy any additional parts from the input message to the output message(s).</span></span> <span data-ttu-id="c734c-110">これにより、パイプラインでの後続の処理のために追加部分が保持されます。</span><span class="sxs-lookup"><span data-stu-id="c734c-110">This preserves them for further processing in the pipeline.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c734c-111">参照</span><span class="sxs-lookup"><span data-stu-id="c734c-111">See Also</span></span>  
 <span data-ttu-id="c734c-112">[全般パイプライン コンポーネントの開発](../core/developing-a-general-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c734c-112">[Developing a General Pipeline Component](../core/developing-a-general-pipeline-component.md) </span></span>  
 <span data-ttu-id="c734c-113">[逆アセンブラー パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c734c-113">[Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="c734c-114">[プローブ パイプライン コンポーネントの開発](../core/developing-a-probing-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c734c-114">[Developing a Probing Pipeline Component](../core/developing-a-probing-pipeline-component.md) </span></span>  
 <span data-ttu-id="c734c-115">[パイプライン コンポーネントからエラーの報告](../core/reporting-errors-from-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="c734c-115">[Reporting Errors from Pipeline Components](../core/reporting-errors-from-pipeline-components.md) </span></span>  
 <span data-ttu-id="c734c-116">[ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="c734c-116">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="c734c-117">[パイプライン コンポーネントの展開](../core/deploying-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="c734c-117">[Deploying Pipeline Components](../core/deploying-pipeline-components.md) </span></span>  
 [<span data-ttu-id="c734c-118">CustomComponent (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="c734c-118">CustomComponent (BizTalk Server Sample)</span></span>](../core/customcomponent-biztalk-server-sample.md)