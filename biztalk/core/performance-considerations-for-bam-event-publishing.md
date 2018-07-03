---
title: BAM イベントの発行のパフォーマンスに関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, BAM
- publishing, BAM
- BAM, publishing
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 5a99e61a-a3d9-47fd-a933-2297f79817a5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c031f9a3325eda9cbcf865eaf72d1d9e100616c7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997539"
---
# <a name="performance-considerations-for-bam-event-publishing"></a>BAM イベントを公開する際のパフォーマンスに関する考慮事項
BAM では、ビジネス イベントの公開形式として、次に示す 2 種類の形式がサポートされています。  
  
- 同期  
  
- 非同期  
  
  次の図に、これら 2 つのモデルを示します。  
  
  ![](../core/media/bam-topologies.gif "bam_topologies")  
  BAM トポロジ  
  
  同期形式は管理とコードからの実行が容易ですが、非同期形式の方がパフォーマンスに優れています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [同期ビジネス イベントの追跡](../core/synchronous-business-event-tracking.md)  
  
-   [非同期ビジネス イベントの追跡](../core/asynchronous-business-event-tracking.md)