---
title: エラー - ネイティブ シリアライズ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.nativeSerialize
ms.assetid: 48f8d460-83a0-44ce-af9b-086fcad36cb8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80d6d9df379b93a11d4d736161029684ec175cb1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347268"
---
# <a name="error---native-serialization"></a><span data-ttu-id="0a328-102">エラー - ネイティブ シリアライズ</span><span class="sxs-lookup"><span data-stu-id="0a328-102">Error - Native Serialization</span></span>
<span data-ttu-id="0a328-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="0a328-103">**Error Code**</span></span>  
  
 <span data-ttu-id="0a328-104">btm1048</span><span class="sxs-lookup"><span data-stu-id="0a328-104">btm1048</span></span>  
  
 <span data-ttu-id="0a328-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="0a328-105">**Explanation**</span></span>  
  
 <span data-ttu-id="0a328-106">送信先スキーマで指定されたネイティブ形式にマップで生成される XML 出力インスタンス メッセージの変換中にシリアライズ エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0a328-106">The indicated serialization error was encountered when attempting to convert the XML output instance message produced by the map into the native format specified by the destination schema.</span></span>  
  
 <span data-ttu-id="0a328-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="0a328-107">**User Action**</span></span>  
  
 <span data-ttu-id="0a328-108">マップでは、指定されている、いずれかの変換または送信先スキーマ、または両方に、適切な修正を行うシリアライズ エラーに基づき、します。</span><span class="sxs-lookup"><span data-stu-id="0a328-108">Based on the indicated serialization error, make the appropriate corrections to either the transformations specified in the map, or to the destination schema, or to both.</span></span> <span data-ttu-id="0a328-109">BizTalk エディターで送信先スキーマを開きを使用するのに役立ちますがある可能性があります、**スキーマの検証**、**インスタンスの検証**、および**インスタンスの生成**ときに利用可能なコマンドソリューション エクスプ ローラーでスキーマを右クリックするとします。</span><span class="sxs-lookup"><span data-stu-id="0a328-109">It may be helpful to open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands available when you right-click a schema in Solution Explorer.</span></span>