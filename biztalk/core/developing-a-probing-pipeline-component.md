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
ms.openlocfilehash: 54da9d0433b0ca416e5c0da797a4d4c8678aab8a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389455"
---
# <a name="developing-a-probing-pipeline-component"></a><span data-ttu-id="89d46-102">プローブ パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="89d46-102">Developing a Probing Pipeline Component</span></span>
<span data-ttu-id="89d46-103">任意のパイプライン コンポーネント (全般、アセンブル、または逆アセンブル) を実装できる、`IProbeMessage`インターフェイスの場合はメッセージ プローブ機能をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89d46-103">Any pipeline component (general, assembling, or disassembling) can implement the `IProbeMessage` interface if it must support message probing functionality.</span></span> <span data-ttu-id="89d46-104">プローブ コンポーネントがされているパイプライン ステージで使用される**FirstMatch**実行モード。</span><span class="sxs-lookup"><span data-stu-id="89d46-104">A probing component is used in the pipeline stages that have **FirstMatch** execution mode.</span></span> <span data-ttu-id="89d46-105">このモードのステージで、BizTalk メッセージング エンジンには、コンポーネント、コンポーネントのかどうか、メッセージの形式を認識するメッセージの先頭部分が付与されます。</span><span class="sxs-lookup"><span data-stu-id="89d46-105">In such stages, the BizTalk Messaging Engine gives the beginning part of the message to the component to determine if the component recognizes the format of the message.</span></span> <span data-ttu-id="89d46-106">コンポーネントには、形式が認識している場合は、メッセージ全体が処理するためのコンポーネントに付与されます。</span><span class="sxs-lookup"><span data-stu-id="89d46-106">If the component recognizes the format, the entire message is given to the component for processing.</span></span>  
  
 <span data-ttu-id="89d46-107">**IProbeMessage**インターフェイスは 1 つのメソッドを公開**プローブ**、使用して、コンポーネントをメッセージの先頭部分を確認します。</span><span class="sxs-lookup"><span data-stu-id="89d46-107">The **IProbeMessage** interface exposes a single method, **Probe**, which enables the component to check the beginning part of the message.</span></span> <span data-ttu-id="89d46-108">戻り値は、このコンポーネントが実行されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="89d46-108">The return value determines whether this component is run.</span></span> <span data-ttu-id="89d46-109">次の手順では、BizTalk メッセージング エンジンが認識を必要とするステージを実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="89d46-109">The following steps outline how the BizTalk Messaging Engine runs a stage that requires recognition:</span></span>  
  
1. <span data-ttu-id="89d46-110">ステージにコンポーネントが含まれていない場合は、ステージが実行されないと、メッセージが処理するための後続のステージに渡さします。</span><span class="sxs-lookup"><span data-stu-id="89d46-110">If the stage does not contain any components, the stage is not run and the message is given to the subsequent stages for processing.</span></span>  
  
2. <span data-ttu-id="89d46-111">コンポーネントを実装するかどうかの確認、 **IProbeMessage**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="89d46-111">Check if the component implements the **IProbeMessage** interface.</span></span> <span data-ttu-id="89d46-112">それ以外の場合は、メッセージング エンジンは、コンポーネントを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="89d46-112">If not, the Messaging Engine invokes the component.</span></span> <span data-ttu-id="89d46-113">ステージ処理が完了し、メッセージは次のステージに渡さします。</span><span class="sxs-lookup"><span data-stu-id="89d46-113">The stage processing is done and the message is given to the next stage.</span></span>  
  
3. <span data-ttu-id="89d46-114">**プローブ**メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="89d46-114">The **Probe** method is invoked.</span></span> <span data-ttu-id="89d46-115">戻り値が場合**True**コンポーネントを実行します。</span><span class="sxs-lookup"><span data-stu-id="89d46-115">If the return value is **True**, the component is run.</span></span> <span data-ttu-id="89d46-116">ステージ処理が完了し、メッセージは次のステージに渡さします。</span><span class="sxs-lookup"><span data-stu-id="89d46-116">Then the stage processing is done and the message is given to a next stage.</span></span>  
  
4. <span data-ttu-id="89d46-117">メッセージング エンジンは、ステージ内の次のコンポーネントを取得します。</span><span class="sxs-lookup"><span data-stu-id="89d46-117">The Messaging Engine gets the next component in the stage.</span></span> <span data-ttu-id="89d46-118">コンポーネントがないが存在し、コンポーネントのいずれも実行されている場合、エラーを生成します。 パイプライン処理が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="89d46-118">If there are no more components and none of the components have been run, it generates an error that pipeline processing has failed.</span></span> <span data-ttu-id="89d46-119">コンポーネントがないが存在し、少なくとも 1 つのコンポーネントが実行されている場合、処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="89d46-119">If there are no more components and at least one component has been run, the processing is done.</span></span>  
  
   <span data-ttu-id="89d46-120">ステージに認識が必要としない場合 (たとえば、実行モードは**すべて**)、メッセージング エンジンは、最初のクエリを実行することがなく、コンポーネントを呼び出します、 **IProbeMessage**インターフェイスと呼び出し、**プローブ**メソッド。</span><span class="sxs-lookup"><span data-stu-id="89d46-120">If a stage does not require recognition (for example, the execution mode is **All**), the Messaging Engine invokes the component without first querying for the **IProbeMessage** interface and calling the **Probe** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d46-121">参照</span><span class="sxs-lookup"><span data-stu-id="89d46-121">See Also</span></span>  
 <span data-ttu-id="89d46-122">[全般パイプライン コンポーネントの開発](../core/developing-a-general-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="89d46-122">[Developing a General Pipeline Component](../core/developing-a-general-pipeline-component.md) </span></span>  
 <span data-ttu-id="89d46-123">[アセンブラー パイプライン コンポーネントの開発](../core/developing-an-assembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="89d46-123">[Developing an Assembling Pipeline Component](../core/developing-an-assembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="89d46-124">[逆アセンブラー パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="89d46-124">[Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="89d46-125">[パイプライン コンポーネントからエラーの報告](../core/reporting-errors-from-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="89d46-125">[Reporting Errors from Pipeline Components](../core/reporting-errors-from-pipeline-components.md) </span></span>  
 <span data-ttu-id="89d46-126">[ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="89d46-126">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 [<span data-ttu-id="89d46-127">パイプライン コンポーネントの展開</span><span class="sxs-lookup"><span data-stu-id="89d46-127">Deploying Pipeline Components</span></span>](../core/deploying-pipeline-components.md)