---
title: パイプライン コンポーネントのプロパティを読み取る方法 |Microsoft Docs
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
ms.openlocfilehash: 1f9a91edb33167ca97ea73949c8419d1df1521ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335685"
---
# <a name="how-to-read-pipeline-component-properties"></a><span data-ttu-id="e1344-102">パイプライン コンポーネントのプロパティを読み取る方法</span><span class="sxs-lookup"><span data-stu-id="e1344-102">How to Read Pipeline Component Properties</span></span>
<span data-ttu-id="e1344-103">[プロパティ] ウィンドウには、コンポーネントの 2 つのセクションが含まれています: [全般] プロパティとコンポーネントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="e1344-103">The Properties window contains two sections for components: general properties and component properties.</span></span> <span data-ttu-id="e1344-104">[全般] プロパティは、コンポーネント間の値を変更する場合に、すべてのコンポーネントに共通です。</span><span class="sxs-lookup"><span data-stu-id="e1344-104">General properties are common to all components, though their values change between components.</span></span>  
  
### <a name="to-read-the-general-properties-for-a-pipeline-component"></a><span data-ttu-id="e1344-105">パイプライン コンポーネントの [全般] プロパティを読み取る</span><span class="sxs-lookup"><span data-stu-id="e1344-105">To read the general properties for a pipeline component</span></span>  
  
1.  <span data-ttu-id="e1344-106">パイプライン コンポーネントをパイプラインのステージにドラッグするか、パイプライン内に既に存在する場合にコンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1344-106">Drag the pipeline component into a stage of the pipeline, or select a component if it already exists in the pipeline.</span></span>  
  
2.  <span data-ttu-id="e1344-107">[プロパティ] ウィンドウでの**全般**セクションで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e1344-107">In the Properties window, in the **General** section, do the following.</span></span>  
  
    |<span data-ttu-id="e1344-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e1344-108">Use this</span></span>|<span data-ttu-id="e1344-109">目的</span><span class="sxs-lookup"><span data-stu-id="e1344-109">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e1344-110">**名前**</span><span class="sxs-lookup"><span data-stu-id="e1344-110">**Name**</span></span>|<span data-ttu-id="e1344-111">コンポーネント名を示します。</span><span class="sxs-lookup"><span data-stu-id="e1344-111">Indicates the component name.</span></span>|  
    |<span data-ttu-id="e1344-112">**アセンブリ**</span><span class="sxs-lookup"><span data-stu-id="e1344-112">**Assembly**</span></span>|<span data-ttu-id="e1344-113">アセンブリと、コンポーネントに関連付けられた .NET 情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e1344-113">Indicates the assembly and associated .NET information for the component.</span></span>|  
    |<span data-ttu-id="e1344-114">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="e1344-114">**Description**</span></span>|<span data-ttu-id="e1344-115">パイプライン コンポーネントのフレンドリ名を示します。</span><span class="sxs-lookup"><span data-stu-id="e1344-115">Indicates the friendly name of the pipeline component.</span></span>|  
    |<span data-ttu-id="e1344-116">**管理されています。**</span><span class="sxs-lookup"><span data-stu-id="e1344-116">**Managed**</span></span>|<span data-ttu-id="e1344-117">パイプライン コンポーネントが管理されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e1344-117">Indicates whether the pipeline component is managed.</span></span> <span data-ttu-id="e1344-118">**[はい]** コンポーネントが .NET のマネージ コンポーネント以外の場合**いいえ**パイプライン コンポーネントが COM コンポーネントである場合。</span><span class="sxs-lookup"><span data-stu-id="e1344-118">**Yes** if the component is a .NET managed component; **No** if the pipeline component is a COM component.</span></span>|  
    |<span data-ttu-id="e1344-119">**[パス]**</span><span class="sxs-lookup"><span data-stu-id="e1344-119">**Path**</span></span>|<span data-ttu-id="e1344-120">.NET コンポーネントに完全修飾パスを示します。</span><span class="sxs-lookup"><span data-stu-id="e1344-120">Indicates the fully qualified path to the .NET component.</span></span>|  
    |<span data-ttu-id="e1344-121">**型**</span><span class="sxs-lookup"><span data-stu-id="e1344-121">**Type**</span></span>|<span data-ttu-id="e1344-122">コンポーネントの種類、アセンブリ、およびコンポーネントに関連付けられた .NET 情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e1344-122">Indicates the component type, the assembly, and the associated .NET information for the component.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1344-123">参照</span><span class="sxs-lookup"><span data-stu-id="e1344-123">See Also</span></span>  
 <span data-ttu-id="e1344-124">[ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="e1344-124">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 [<span data-ttu-id="e1344-125">パイプライン デザイナーでのパイプラインの作成</span><span class="sxs-lookup"><span data-stu-id="e1344-125">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)