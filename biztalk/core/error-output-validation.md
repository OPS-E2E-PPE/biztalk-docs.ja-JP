---
title: エラー - 出力検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.outputValidation
ms.assetid: 18a251a9-6bd4-4fd1-a774-2ea1b7870891
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 392ec887e3352940257f268e589280eb361c0d68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347116"
---
# <a name="error---output-validation"></a><span data-ttu-id="c4dc7-102">エラー - 出力検証</span><span class="sxs-lookup"><span data-stu-id="c4dc7-102">Error - Output Validation</span></span>
<span data-ttu-id="c4dc7-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="c4dc7-103">**Error Code**</span></span>  
  
 <span data-ttu-id="c4dc7-104">btm1046</span><span class="sxs-lookup"><span data-stu-id="c4dc7-104">btm1046</span></span>  
  
 <span data-ttu-id="c4dc7-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="c4dc7-105">**Explanation**</span></span>  
  
 <span data-ttu-id="c4dc7-106">表示された理由により、マップのテスト操作によって作成された出力インスタンス メッセージ ファイルを送信先スキーマに対して検証できませんでした。</span><span class="sxs-lookup"><span data-stu-id="c4dc7-106">The output instance message file created by the Test Map operation could not be validated against the destination schema for the indicated reason.</span></span>  
  
 <span data-ttu-id="c4dc7-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="c4dc7-107">**User Action**</span></span>  
  
 <span data-ttu-id="c4dc7-108">マップでは、指定されている、いずれかの変換または送信先スキーマ、または両方に、適切な修正を行う表示された理由に基づいて、します。</span><span class="sxs-lookup"><span data-stu-id="c4dc7-108">Based on the indicated reason, make the appropriate corrections to either the transformations specified in the map, or to the destination schema, or to both.</span></span> <span data-ttu-id="c4dc7-109">BizTalk エディターで送信先スキーマを開きを使用するのに役立ちますがある可能性があります、**スキーマの検証**、**インスタンスの検証**、および**インスタンスの生成**ときに利用可能なコマンドソリューション エクスプ ローラーでスキーマを右クリックするとします。</span><span class="sxs-lookup"><span data-stu-id="c4dc7-109">It may be helpful to open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands available when you right-click a schema in Solution Explorer.</span></span>