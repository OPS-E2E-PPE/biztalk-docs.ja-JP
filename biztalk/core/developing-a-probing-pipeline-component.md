---
title: "パイプライン コンポーネントの開発、プローブ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], probing
- IProbeMessage interface
- pipeline interfaces, IProbeMessage
ms.assetid: c3da467d-5270-4c7f-9c38-ce9989bf1b63
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8081c31fc781cd2d1cbc291587f358376a033d66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="developing-a-probing-pipeline-component"></a><span data-ttu-id="d5d13-102">プローブ パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="d5d13-102">Developing a Probing Pipeline Component</span></span>
<span data-ttu-id="d5d13-103">任意のパイプライン コンポーネント (全般、アセンブル、または逆アセンブル) を実装できる、`IProbeMessage`インターフェイスの場合はメッセージ プローブ機能をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5d13-103">Any pipeline component (general, assembling, or disassembling) can implement the `IProbeMessage` interface if it must support message probing functionality.</span></span> <span data-ttu-id="d5d13-104">プローブ コンポーネントはされているパイプライン ステージで使用**FirstMatch**実行モードです。</span><span class="sxs-lookup"><span data-stu-id="d5d13-104">A probing component is used in the pipeline stages that have **FirstMatch** execution mode.</span></span> <span data-ttu-id="d5d13-105">このモードのステージでは、BizTalk Server メッセージング エンジンからプローブ コンポーネントにメッセージの先頭部分が渡され、コンポーネントで認識できる形式のメッセージかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="d5d13-105">In such stages, the BizTalk Messaging Engine gives the beginning part of the message to the component to determine if the component recognizes the format of the message.</span></span> <span data-ttu-id="d5d13-106">コンポーネントで認識できる形式の場合は、メッセージ全体が対応するコンポーネントに渡され、処理されます。</span><span class="sxs-lookup"><span data-stu-id="d5d13-106">If the component recognizes the format, the entire message is given to the component for processing.</span></span>  
  
 <span data-ttu-id="d5d13-107">**IProbeMessage**インターフェイスが 1 つのメソッドを公開**プローブ**メッセージの先頭部分を確認する対象のコンポーネントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d5d13-107">The **IProbeMessage** interface exposes a single method, **Probe**, which enables the component to check the beginning part of the message.</span></span> <span data-ttu-id="d5d13-108">戻り値により、このコンポーネントが実行されているかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="d5d13-108">The return value determines whether this component is run.</span></span> <span data-ttu-id="d5d13-109">以下の手順に、BizTalk メッセージング エンジンで、認識が必要なステージを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d5d13-109">The following steps outline how the BizTalk Messaging Engine runs a stage that requires recognition:</span></span>  
  
1.  <span data-ttu-id="d5d13-110">ステージにコンポーネントが含まれていない場合、ステージは実行されず、メッセージが後続のステージに渡されて処理されます。</span><span class="sxs-lookup"><span data-stu-id="d5d13-110">If the stage does not contain any components, the stage is not run and the message is given to the subsequent stages for processing.</span></span>  
  
2.  <span data-ttu-id="d5d13-111">コンポーネントを実装するかどうかを確認して、 **IProbeMessage**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="d5d13-111">Check if the component implements the **IProbeMessage** interface.</span></span> <span data-ttu-id="d5d13-112">実装されていない場合、メッセージング エンジンはコンポーネントを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d5d13-112">If not, the Messaging Engine invokes the component.</span></span> <span data-ttu-id="d5d13-113">ステージ処理が実行され、メッセージが次のステージに渡されます。</span><span class="sxs-lookup"><span data-stu-id="d5d13-113">The stage processing is done and the message is given to the next stage.</span></span>  
  
3.  <span data-ttu-id="d5d13-114">**プローブ**メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d5d13-114">The **Probe** method is invoked.</span></span> <span data-ttu-id="d5d13-115">場合は、戻り値は**True**コンポーネントを実行します。</span><span class="sxs-lookup"><span data-stu-id="d5d13-115">If the return value is **True**, the component is run.</span></span> <span data-ttu-id="d5d13-116">この場合、ステージ処理が実行され、メッセージが次のステージに渡されます。</span><span class="sxs-lookup"><span data-stu-id="d5d13-116">Then the stage processing is done and the message is given to a next stage.</span></span>  
  
4.  <span data-ttu-id="d5d13-117">メッセージング エンジンは、ステージの次のコンポーネントを取得します。</span><span class="sxs-lookup"><span data-stu-id="d5d13-117">The Messaging Engine gets the next component in the stage.</span></span> <span data-ttu-id="d5d13-118">追加のコンポーネントが存在せず、どのコンポーネントも実行されていない場合、パイプライン処理が失敗したことを示すエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d5d13-118">If there are no more components and none of the components have been run, it generates an error that pipeline processing has failed.</span></span> <span data-ttu-id="d5d13-119">追加のコンポーネントが存在せず、1 つ以上のコンポーネントが実行されている場合、処理が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d5d13-119">If there are no more components and at least one component has been run, the processing is done.</span></span>  
  
 <span data-ttu-id="d5d13-120">ステージに認識が必要としない場合 (実行モードは、たとえば、**すべて**)、メッセージング エンジンが最初のクエリを実行することがなく、コンポーネントを呼び出して、 **IProbeMessage**インターフェイスと呼び出し、**プローブ**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="d5d13-120">If a stage does not require recognition (for example, the execution mode is **All**), the Messaging Engine invokes the component without first querying for the **IProbeMessage** interface and calling the **Probe** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d13-121">参照</span><span class="sxs-lookup"><span data-stu-id="d5d13-121">See Also</span></span>  
 <span data-ttu-id="d5d13-122">[全般パイプライン コンポーネントの開発](../core/developing-a-general-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="d5d13-122">[Developing a General Pipeline Component](../core/developing-a-general-pipeline-component.md) </span></span>  
 <span data-ttu-id="d5d13-123">[アセンブラー パイプライン コンポーネントの開発](../core/developing-an-assembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="d5d13-123">[Developing an Assembling Pipeline Component](../core/developing-an-assembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="d5d13-124">[逆アセンブラー パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="d5d13-124">[Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="d5d13-125">[パイプライン コンポーネントからエラーの報告](../core/reporting-errors-from-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="d5d13-125">[Reporting Errors from Pipeline Components](../core/reporting-errors-from-pipeline-components.md) </span></span>  
 <span data-ttu-id="d5d13-126">[ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="d5d13-126">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 [<span data-ttu-id="d5d13-127">パイプライン コンポーネントの展開</span><span class="sxs-lookup"><span data-stu-id="d5d13-127">Deploying Pipeline Components</span></span>](../core/deploying-pipeline-components.md)