---
title: パイプライン コンポーネントのプロパティを読み取る方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, properties
ms.assetid: 10b1c59c-7ba4-453f-9aaa-1ce9ecf31fac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19a6ccbcbe7588a0a75b4dbe6bf821a19fab965c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-read-pipeline-component-properties"></a><span data-ttu-id="6efc4-102">パイプライン コンポーネントのプロパティを読み取る方法</span><span class="sxs-lookup"><span data-stu-id="6efc4-102">How to Read Pipeline Component Properties</span></span>
<span data-ttu-id="6efc4-103">[プロパティ] ウィンドウには、コンポーネントの 2 つのセクションが含まれています: [全般] プロパティとコンポーネントのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="6efc4-103">The Properties window contains two sections for components: general properties and component properties.</span></span> <span data-ttu-id="6efc4-104">全般プロパティはすべてのコンポーネントで共通のプロパティですが、値はコンポーネントごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="6efc4-104">General properties are common to all components, though their values change between components.</span></span>  
  
### <a name="to-read-the-general-properties-for-a-pipeline-component"></a><span data-ttu-id="6efc4-105">パイプライン コンポーネントの全般プロパティを読み取るには</span><span class="sxs-lookup"><span data-stu-id="6efc4-105">To read the general properties for a pipeline component</span></span>  
  
1.  <span data-ttu-id="6efc4-106">パイプライン コンポーネントをパイプラインのステージにドラッグします。コンポーネントが既にパイプラインに存在する場合は、コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="6efc4-106">Drag the pipeline component into a stage of the pipeline, or select a component if it already exists in the pipeline.</span></span>  
  
2.  <span data-ttu-id="6efc4-107">[プロパティ] ウィンドウでの**全般**セクションで、次の操作です。</span><span class="sxs-lookup"><span data-stu-id="6efc4-107">In the Properties window, in the **General** section, do the following.</span></span>  
  
    |<span data-ttu-id="6efc4-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6efc4-108">Use this</span></span>|<span data-ttu-id="6efc4-109">目的</span><span class="sxs-lookup"><span data-stu-id="6efc4-109">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6efc4-110">**名前**</span><span class="sxs-lookup"><span data-stu-id="6efc4-110">**Name**</span></span>|<span data-ttu-id="6efc4-111">コンポーネントの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6efc4-111">Indicates the component name.</span></span>|  
    |<span data-ttu-id="6efc4-112">**アセンブリ**</span><span class="sxs-lookup"><span data-stu-id="6efc4-112">**Assembly**</span></span>|<span data-ttu-id="6efc4-113">アセンブリと、コンポーネントに関連付けられた .NET 情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6efc4-113">Indicates the assembly and associated .NET information for the component.</span></span>|  
    |<span data-ttu-id="6efc4-114">**Description**</span><span class="sxs-lookup"><span data-stu-id="6efc4-114">**Description**</span></span>|<span data-ttu-id="6efc4-115">パイプライン コンポーネントのフレンドリ名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6efc4-115">Indicates the friendly name of the pipeline component.</span></span>|  
    |<span data-ttu-id="6efc4-116">**管理されています。**</span><span class="sxs-lookup"><span data-stu-id="6efc4-116">**Managed**</span></span>|<span data-ttu-id="6efc4-117">パイプライン コンポーネントがマネージ型かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6efc4-117">Indicates whether the pipeline component is managed.</span></span> <span data-ttu-id="6efc4-118">**[はい]**コンポーネントが .NET マネージ コンポーネント以外の場合**いいえ**パイプライン コンポーネントが COM コンポーネントである場合。</span><span class="sxs-lookup"><span data-stu-id="6efc4-118">**Yes** if the component is a .NET managed component; **No** if the pipeline component is a COM component.</span></span>|  
    |<span data-ttu-id="6efc4-119">**[パス]**</span><span class="sxs-lookup"><span data-stu-id="6efc4-119">**Path**</span></span>|<span data-ttu-id="6efc4-120">.NET コンポーネントの完全修飾パスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6efc4-120">Indicates the fully qualified path to the .NET component.</span></span>|  
    |<span data-ttu-id="6efc4-121">**型**</span><span class="sxs-lookup"><span data-stu-id="6efc4-121">**Type**</span></span>|<span data-ttu-id="6efc4-122">コンポーネントの種類、アセンブリ、およびコンポーネントに関連付けられた .NET 情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6efc4-122">Indicates the component type, the assembly, and the associated .NET information for the component.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6efc4-123">参照</span><span class="sxs-lookup"><span data-stu-id="6efc4-123">See Also</span></span>  
 <span data-ttu-id="6efc4-124">[ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="6efc4-124">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 [<span data-ttu-id="6efc4-125">パイプライン デザイナーでパイプラインの作成</span><span class="sxs-lookup"><span data-stu-id="6efc4-125">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)