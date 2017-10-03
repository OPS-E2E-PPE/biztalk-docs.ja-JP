---
title: "カスタム パイプライン コンポーネントの開発 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom]
- pipeline components [custom], about pipeline components
- pipeline components [custom], creating
- customizing, pipeline components
- pipeline interfaces
- IDisassemblerComponent
- pipeline interfaces, about pipeline interfaces
- creating, pipeline components [custom]
- IAssemblerComponent
- IComponent
- pipeline components [custom], customizing
- pipeline interfaces, interface types
- pipeline components [custom], interfaces
- pipeline components [custom], component types
ms.assetid: cce61e0d-f1e3-4ec2-b38c-7c6eaf83ac10
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 723cd04a2a907fdb5d770975c27d47e1752d08ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="developing-custom-pipeline-components"></a><span data-ttu-id="4ceb8-102">カスタム パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="4ceb8-102">Developing Custom Pipeline Components</span></span>
<span data-ttu-id="4ceb8-103">ここでは、パイプライン コンポーネントを開発する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ceb8-103">This section describes how to develop a pipeline component.</span></span> <span data-ttu-id="4ceb8-104">3 種類のパイプライン コンポーネントを作成することができます: 全般、アセンブル、および逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="4ceb8-104">You can create three types of pipeline components: general, assembling, and disassembling.</span></span> <span data-ttu-id="4ceb8-105">これらの各パイプライン コンポーネントでは、プローブ機能を追加実装できます。</span><span class="sxs-lookup"><span data-stu-id="4ceb8-105">Each of the three types can additionally implement probing functionality.</span></span> <span data-ttu-id="4ceb8-106">各パイプライン コンポーネントの種類が関連付けられているインターフェイスを BizTalk メッセージング エンジンに接続するコンポーネントを実装する必要があります。パイプライン インターフェイス コンポーネントの種類を識別するには、 **IComponent**、 **IAssemblerComponent**、および**IDisassemblerComponent**です。</span><span class="sxs-lookup"><span data-stu-id="4ceb8-106">Each type of pipeline component has an associated interface that must be implemented for the component to be plugged into the BizTalk Messaging Engine; the pipeline interfaces that distinguish the types of components are **IComponent**, **IAssemblerComponent**, and **IDisassemblerComponent**.</span></span> <span data-ttu-id="4ceb8-107">プルーブ コンポーネントを実装する必要があります、 **IProbeMessage**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4ceb8-107">For probing components, you must implement the **IProbeMessage** interface.</span></span>  
  
 <span data-ttu-id="4ceb8-108">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にはサンプル パイプライン コンポーネントが含まれており、独自のコンポーネントを作成するときに参照できます。</span><span class="sxs-lookup"><span data-stu-id="4ceb8-108">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] contains a sample pipeline component that you can reference when creating your own component.</span></span> <span data-ttu-id="4ceb8-109">サンプル コンポーネントは、メッセージの末尾や先頭にデータを追加する方法を示すものです。</span><span class="sxs-lookup"><span data-stu-id="4ceb8-109">The sample component demonstrates how to append data to the end of a message and add data at the beginning of the message.</span></span> <span data-ttu-id="4ceb8-110">サンプル パイプライン コンポーネントの詳細については、次を参照してください。 [CustomComponent (BizTalk Server サンプル)](../core/customcomponent-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="4ceb8-110">For more information about the sample pipeline component, see [CustomComponent (BizTalk Server Sample)](../core/customcomponent-biztalk-server-sample.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4ceb8-111">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、パイプラインからカスタム パイプライン コンポーネントを参照すると、コンパイル時エラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="4ceb8-111">If you reference a custom pipeline component from a pipeline in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], a compile-time error may occur.</span></span> <span data-ttu-id="4ceb8-112">このエラーを修正するには、コンパイル前にパイプライン デザイナーをいったん閉じて再度開きます。</span><span class="sxs-lookup"><span data-stu-id="4ceb8-112">To correct the error, close Pipeline Designer and reopen it before compiling.</span></span> <span data-ttu-id="4ceb8-113">または、コンポーネントをいったん削除して追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="4ceb8-113">Alternatively, you can remove the component, and then add it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4ceb8-114">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] にアップグレードするときは、既存のカスタム パイプライン コンポーネント内の文字列変数に "\n" などの改行文字が含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4ceb8-114">When upgrading to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], ensure that any string variables in your existing custom pipeline components do not contain any newline characters such as ‘\n’.</span></span> <span data-ttu-id="4ceb8-115">改行文字が含まれていると、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でこのコンポーネントをコンパイルする際に "定数が 2 行目に続いています" エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4ceb8-115">Otherwise, a “newline in constant” error will occur when compiling this component in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ceb8-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4ceb8-116">In This Section</span></span>  
  
-   [<span data-ttu-id="4ceb8-117">パイプライン インターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4ceb8-117">Using Pipeline Interfaces</span></span>](../core/using-pipeline-interfaces.md)  
  
-   [<span data-ttu-id="4ceb8-118">全般パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="4ceb8-118">Developing a General Pipeline Component</span></span>](../core/developing-a-general-pipeline-component.md)  
  
-   [<span data-ttu-id="4ceb8-119">アセンブラー パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="4ceb8-119">Developing an Assembling Pipeline Component</span></span>](../core/developing-an-assembling-pipeline-component.md)  
  
-   [<span data-ttu-id="4ceb8-120">逆アセンブラー パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="4ceb8-120">Developing a Disassembling Pipeline Component</span></span>](../core/developing-a-disassembling-pipeline-component.md)  
  
-   [<span data-ttu-id="4ceb8-121">プローブ パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="4ceb8-121">Developing a Probing Pipeline Component</span></span>](../core/developing-a-probing-pipeline-component.md)  
  
-   [<span data-ttu-id="4ceb8-122">実装する、マネージ ストリーミング パイプライン コンポーネントでの Seek メソッド</span><span class="sxs-lookup"><span data-stu-id="4ceb8-122">Implementing a Seek Method in a Managed Streaming Pipeline Component</span></span>](../core/implementing-a-seek-method-in-a-managed-streaming-pipeline-component.md)  
  
-   [<span data-ttu-id="4ceb8-123">解析およびシリアル化エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="4ceb8-123">Using the Parsing and Serializing Engines</span></span>](../core/using-the-parsing-and-serializing-engines.md)  
  
-   [<span data-ttu-id="4ceb8-124">パイプライン コンポーネントからエラーの報告</span><span class="sxs-lookup"><span data-stu-id="4ceb8-124">Reporting Errors from Pipeline Components</span></span>](../core/reporting-errors-from-pipeline-components.md)  
  
-   [<span data-ttu-id="4ceb8-125">パイプライン コンポーネントの展開</span><span class="sxs-lookup"><span data-stu-id="4ceb8-125">Deploying Pipeline Components</span></span>](../core/deploying-pipeline-components.md)  
  
-   [<span data-ttu-id="4ceb8-126">カスタム パイプラインのデバッグ</span><span class="sxs-lookup"><span data-stu-id="4ceb8-126">Debugging Custom Pipelines</span></span>](../core/debugging-custom-pipelines.md)