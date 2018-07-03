---
title: パイプライン コンポーネントの開発、プローブ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], probing
- IProbeMessage interface
- pipeline interfaces, IProbeMessage
ms.assetid: c3da467d-5270-4c7f-9c38-ce9989bf1b63
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0be44929609eaba5ec30a6e40c1bdda14192e351
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987363"
---
# <a name="developing-a-probing-pipeline-component"></a><span data-ttu-id="2eb9d-102">プローブ パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="2eb9d-102">Developing a Probing Pipeline Component</span></span>
<span data-ttu-id="2eb9d-103">任意のパイプライン コンポーネント (全般、アセンブル、または逆アセンブル) を実装できる、`IProbeMessage`インターフェイスの場合はメッセージ プローブ機能をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-103">Any pipeline component (general, assembling, or disassembling) can implement the `IProbeMessage` interface if it must support message probing functionality.</span></span> <span data-ttu-id="2eb9d-104">プローブ コンポーネントがされているパイプライン ステージで使用される**FirstMatch**実行モード。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-104">A probing component is used in the pipeline stages that have **FirstMatch** execution mode.</span></span> <span data-ttu-id="2eb9d-105">このモードのステージでは、BizTalk Server メッセージング エンジンからプローブ コンポーネントにメッセージの先頭部分が渡され、コンポーネントで認識できる形式のメッセージかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-105">In such stages, the BizTalk Messaging Engine gives the beginning part of the message to the component to determine if the component recognizes the format of the message.</span></span> <span data-ttu-id="2eb9d-106">コンポーネントで認識できる形式の場合は、メッセージ全体が対応するコンポーネントに渡され、処理されます。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-106">If the component recognizes the format, the entire message is given to the component for processing.</span></span>  
  
 <span data-ttu-id="2eb9d-107">**IProbeMessage**インターフェイスは 1 つのメソッドを公開**プローブ**、使用して、コンポーネントをメッセージの先頭部分を確認します。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-107">The **IProbeMessage** interface exposes a single method, **Probe**, which enables the component to check the beginning part of the message.</span></span> <span data-ttu-id="2eb9d-108">戻り値により、このコンポーネントが実行されているかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-108">The return value determines whether this component is run.</span></span> <span data-ttu-id="2eb9d-109">以下の手順に、BizTalk メッセージング エンジンで、認識が必要なステージを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-109">The following steps outline how the BizTalk Messaging Engine runs a stage that requires recognition:</span></span>  
  
1. <span data-ttu-id="2eb9d-110">ステージにコンポーネントが含まれていない場合、ステージは実行されず、メッセージが後続のステージに渡されて処理されます。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-110">If the stage does not contain any components, the stage is not run and the message is given to the subsequent stages for processing.</span></span>  
  
2. <span data-ttu-id="2eb9d-111">コンポーネントを実装するかどうかの確認、 **IProbeMessage**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-111">Check if the component implements the **IProbeMessage** interface.</span></span> <span data-ttu-id="2eb9d-112">実装されていない場合、メッセージング エンジンはコンポーネントを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-112">If not, the Messaging Engine invokes the component.</span></span> <span data-ttu-id="2eb9d-113">ステージ処理が実行され、メッセージが次のステージに渡されます。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-113">The stage processing is done and the message is given to the next stage.</span></span>  
  
3. <span data-ttu-id="2eb9d-114">**プローブ**メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-114">The **Probe** method is invoked.</span></span> <span data-ttu-id="2eb9d-115">戻り値が場合**True**コンポーネントを実行します。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-115">If the return value is **True**, the component is run.</span></span> <span data-ttu-id="2eb9d-116">この場合、ステージ処理が実行され、メッセージが次のステージに渡されます。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-116">Then the stage processing is done and the message is given to a next stage.</span></span>  
  
4. <span data-ttu-id="2eb9d-117">メッセージング エンジンは、ステージの次のコンポーネントを取得します。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-117">The Messaging Engine gets the next component in the stage.</span></span> <span data-ttu-id="2eb9d-118">追加のコンポーネントが存在せず、どのコンポーネントも実行されていない場合、パイプライン処理が失敗したことを示すエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-118">If there are no more components and none of the components have been run, it generates an error that pipeline processing has failed.</span></span> <span data-ttu-id="2eb9d-119">追加のコンポーネントが存在せず、1 つ以上のコンポーネントが実行されている場合、処理が実行されます。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-119">If there are no more components and at least one component has been run, the processing is done.</span></span>  
  
   <span data-ttu-id="2eb9d-120">ステージに認識が必要としない場合 (たとえば、実行モードは**すべて**)、メッセージング エンジンは、最初のクエリを実行することがなく、コンポーネントを呼び出します、 **IProbeMessage**インターフェイスと呼び出し、**プローブ**メソッド。</span><span class="sxs-lookup"><span data-stu-id="2eb9d-120">If a stage does not require recognition (for example, the execution mode is **All**), the Messaging Engine invokes the component without first querying for the **IProbeMessage** interface and calling the **Probe** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eb9d-121">参照</span><span class="sxs-lookup"><span data-stu-id="2eb9d-121">See Also</span></span>  
 <span data-ttu-id="2eb9d-122">[全般パイプライン コンポーネントの開発](../core/developing-a-general-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="2eb9d-122">[Developing a General Pipeline Component](../core/developing-a-general-pipeline-component.md) </span></span>  
 <span data-ttu-id="2eb9d-123">[アセンブラー パイプライン コンポーネントの開発](../core/developing-an-assembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="2eb9d-123">[Developing an Assembling Pipeline Component](../core/developing-an-assembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="2eb9d-124">[逆アセンブラー パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="2eb9d-124">[Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="2eb9d-125">[パイプライン コンポーネントからエラーの報告](../core/reporting-errors-from-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="2eb9d-125">[Reporting Errors from Pipeline Components](../core/reporting-errors-from-pipeline-components.md) </span></span>  
 <span data-ttu-id="2eb9d-126">[ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="2eb9d-126">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 [<span data-ttu-id="2eb9d-127">パイプライン コンポーネントの展開</span><span class="sxs-lookup"><span data-stu-id="2eb9d-127">Deploying Pipeline Components</span></span>](../core/deploying-pipeline-components.md)