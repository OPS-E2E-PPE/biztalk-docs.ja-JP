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
ms.openlocfilehash: b1590ad1450453602b4dd5f25b2d52a4364787af
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996771"
---
# <a name="map-components"></a><span data-ttu-id="6348c-102">マップの構成要素</span><span class="sxs-lookup"><span data-stu-id="6348c-102">Map Components</span></span>
<span data-ttu-id="6348c-103">マップの構成要素のほとんどは、.btm 拡張子を持つマップ ファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="6348c-103">Map files (having a .btm extension) store most of the components of a map.</span></span> <span data-ttu-id="6348c-104">このファイルに格納される項目を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6348c-104">Items stored in the file include:</span></span>  
  
- <span data-ttu-id="6348c-105">送信元スキーマおよび送信先スキーマへの参照</span><span class="sxs-lookup"><span data-stu-id="6348c-105">References to source and destination schemas</span></span>  
  
- <span data-ttu-id="6348c-106">リンク (リンクのプロパティを含む)</span><span class="sxs-lookup"><span data-stu-id="6348c-106">Links, including the link properties</span></span>  
  
- <span data-ttu-id="6348c-107">Functoid とそのプロパティ (入力パラメーターなど)</span><span class="sxs-lookup"><span data-stu-id="6348c-107">Functoids with their properties such as input parameters</span></span>  
  
- <span data-ttu-id="6348c-108">その他さまざまなプロパティ (グリッドやマップそのものに関連付けられたプロパティなど)</span><span class="sxs-lookup"><span data-stu-id="6348c-108">Other miscellaneous properties such as those associated with the grid and the map itself.</span></span>  
  
  <span data-ttu-id="6348c-109">BizTalk マッパーは、.btm ファイル内のマップを XSLT (Extensible Stylesheet Language Transformations) ファイルとしてコンパイルしますが、XSLT がこのファイルの一部になることはありません。</span><span class="sxs-lookup"><span data-stu-id="6348c-109">Although BizTalk Mapper compiles the map in the .btm file into an Extensible Stylesheet Transformations (XSLT) file, the XSLT is not part of the file.</span></span> <span data-ttu-id="6348c-110">BizTalk マッパーがマップの XSLT を生成するのは、プロジェクトのコンパイル時とマップの検証時だけです。</span><span class="sxs-lookup"><span data-stu-id="6348c-110">BizTalk Mapper produces the XSLT for the map only when you compile the project or when you validate the map.</span></span> <span data-ttu-id="6348c-111">BizTalk マッパーは、XSLT をプロジェクト アセンブリの一部としてパッケージします。</span><span class="sxs-lookup"><span data-stu-id="6348c-111">BizTalk Mapper packages the XSLT as part of the project assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6348c-112">参照</span><span class="sxs-lookup"><span data-stu-id="6348c-112">See Also</span></span>  
 <span data-ttu-id="6348c-113">[マップ](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="6348c-113">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="6348c-114">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="6348c-114">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)