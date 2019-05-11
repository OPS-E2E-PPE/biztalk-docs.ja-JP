---
title: コンポーネントのマップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- file types, maps
- BizTalk Mapper, output
- maps, file type
- maps, file contents
- BizTalk Mapper, file type
- maps, components
ms.assetid: be438d21-80a8-49d8-bd08-d85618ab23de
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d22f0431e59f2cae0aecf3e3dc8284a41c16069a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380135"
---
# <a name="map-components"></a><span data-ttu-id="a84ad-102">コンポーネントをマップします。</span><span class="sxs-lookup"><span data-stu-id="a84ad-102">Map Components</span></span>
<span data-ttu-id="a84ad-103">マップの構成要素のほとんどは、.btm 拡張子を持つマップ ファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="a84ad-103">Map files (having a .btm extension) store most of the components of a map.</span></span> <span data-ttu-id="a84ad-104">このファイルに格納される項目を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a84ad-104">Items stored in the file include:</span></span>  
  
- <span data-ttu-id="a84ad-105">送信元スキーマおよび送信先スキーマへの参照</span><span class="sxs-lookup"><span data-stu-id="a84ad-105">References to source and destination schemas</span></span>  
  
- <span data-ttu-id="a84ad-106">リンク (リンクのプロパティを含む)</span><span class="sxs-lookup"><span data-stu-id="a84ad-106">Links, including the link properties</span></span>  
  
- <span data-ttu-id="a84ad-107">Functoid とそのプロパティ (入力パラメーターなど)</span><span class="sxs-lookup"><span data-stu-id="a84ad-107">Functoids with their properties such as input parameters</span></span>  
  
- <span data-ttu-id="a84ad-108">その他さまざまなプロパティ (グリッドやマップそのものに関連付けられたプロパティなど)</span><span class="sxs-lookup"><span data-stu-id="a84ad-108">Other miscellaneous properties such as those associated with the grid and the map itself.</span></span>  
  
  <span data-ttu-id="a84ad-109">BizTalk マッパーは、.btm ファイル内のマップを XSLT (Extensible Stylesheet Language Transformations) ファイルとしてコンパイルしますが、XSLT がこのファイルの一部になることはありません。</span><span class="sxs-lookup"><span data-stu-id="a84ad-109">Although BizTalk Mapper compiles the map in the .btm file into an Extensible Stylesheet Transformations (XSLT) file, the XSLT is not part of the file.</span></span> <span data-ttu-id="a84ad-110">BizTalk マッパーがマップの XSLT を生成するのは、プロジェクトのコンパイル時とマップの検証時だけです。</span><span class="sxs-lookup"><span data-stu-id="a84ad-110">BizTalk Mapper produces the XSLT for the map only when you compile the project or when you validate the map.</span></span> <span data-ttu-id="a84ad-111">BizTalk マッパーは、XSLT をプロジェクト アセンブリの一部としてパッケージします。</span><span class="sxs-lookup"><span data-stu-id="a84ad-111">BizTalk Mapper packages the XSLT as part of the project assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a84ad-112">参照</span><span class="sxs-lookup"><span data-stu-id="a84ad-112">See Also</span></span>  
 <span data-ttu-id="a84ad-113">[マップ](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="a84ad-113">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="a84ad-114">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="a84ad-114">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)