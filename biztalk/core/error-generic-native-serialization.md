---
title: エラー - ネイティブ シリアライズの一般的な |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.genericNativeSerialize
ms.assetid: 3728727d-7d99-432d-844e-c956cc4635e4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbe7591c6d48c647d60daf232b591acbad50ae4b
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530751"
---
# <a name="error---generic-native-serialization"></a><span data-ttu-id="86f20-102">エラー - ネイティブ シリアライズの一般的です</span><span class="sxs-lookup"><span data-stu-id="86f20-102">Error - Generic Native Serialization</span></span>
<span data-ttu-id="86f20-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="86f20-103">**Error Code**</span></span>  
  
 <span data-ttu-id="86f20-104">btm1049</span><span class="sxs-lookup"><span data-stu-id="86f20-104">btm1049</span></span>  
  
 <span data-ttu-id="86f20-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="86f20-105">**Explanation**</span></span>  
  
 <span data-ttu-id="86f20-106">マップで指定された変換によって生成される XML 出力インスタンス メッセージを特定できないエラーにより、送信先スキーマで指定されたネイティブな形式に変換されませんでした。</span><span class="sxs-lookup"><span data-stu-id="86f20-106">The XML output instance message produced by the transformation specified by the map could not be converted to the native format specified by the destination schema due to an unspecified error.</span></span>  
  
 <span data-ttu-id="86f20-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="86f20-107">**User Action**</span></span>  
  
 <span data-ttu-id="86f20-108">送信先スキーマを BizTalk エディターで開くしを使用して、**スキーマの検証**、**インスタンスの検証**と**インスタンスの生成**コマンドを使用できるは、右クリックすると、ソリューション エクスプ ローラーで、問題を分離するスキーマです。</span><span class="sxs-lookup"><span data-stu-id="86f20-108">Open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, to isolate the problem.</span></span>