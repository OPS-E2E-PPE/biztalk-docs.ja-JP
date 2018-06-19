---
title: エラー - 出力検証 |Microsoft ドキュメント
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
ms.openlocfilehash: 7410fba7cebbf5183a02e79aa3c179eb86cd8395
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241194"
---
# <a name="error---output-validation"></a><span data-ttu-id="02f86-102">エラー - 出力検証</span><span class="sxs-lookup"><span data-stu-id="02f86-102">Error - Output Validation</span></span>
<span data-ttu-id="02f86-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="02f86-103">**Error Code**</span></span>  
  
 <span data-ttu-id="02f86-104">btm1046</span><span class="sxs-lookup"><span data-stu-id="02f86-104">btm1046</span></span>  
  
 <span data-ttu-id="02f86-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="02f86-105">**Explanation**</span></span>  
  
 <span data-ttu-id="02f86-106">表示された理由により、マップのテスト操作によって作成された出力インスタンス メッセージ ファイルを、送信先スキーマに対して検証できませんでした。</span><span class="sxs-lookup"><span data-stu-id="02f86-106">The output instance message file created by the Test Map operation could not be validated against the destination schema for the indicated reason.</span></span>  
  
 <span data-ttu-id="02f86-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="02f86-107">**User Action**</span></span>  
  
 <span data-ttu-id="02f86-108">表示された理由を参考にして、マップに指定されている変換または送信先スキーマ、またはその両方を適宜修正してください。</span><span class="sxs-lookup"><span data-stu-id="02f86-108">Based on the indicated reason, make the appropriate corrections to either the transformations specified in the map, or to the destination schema, or to both.</span></span> <span data-ttu-id="02f86-109">送信先スキーマの BizTalk エディターで開きを使用すると役立つ場合があります、**スキーマの検証**、**インスタンスの検証**、および**インスタンスの生成**ときに利用可能なコマンドソリューション エクスプ ローラーでスキーマを右クリックするとします。</span><span class="sxs-lookup"><span data-stu-id="02f86-109">It may be helpful to open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands available when you right-click a schema in Solution Explorer.</span></span>