---
title: エラー - ネイティブ シリアライズ |Microsoft ドキュメント
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
ms.openlocfilehash: c0d4a842a3f9a10703fb47bf21edb01ab92bd93c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---native-serialization"></a><span data-ttu-id="f4a6b-102">エラー - ネイティブ シリアライズ</span><span class="sxs-lookup"><span data-stu-id="f4a6b-102">Error - Native Serialization</span></span>
<span data-ttu-id="f4a6b-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="f4a6b-103">**Error Code**</span></span>  
  
 <span data-ttu-id="f4a6b-104">btm1048</span><span class="sxs-lookup"><span data-stu-id="f4a6b-104">btm1048</span></span>  
  
 <span data-ttu-id="f4a6b-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="f4a6b-105">**Explanation**</span></span>  
  
 <span data-ttu-id="f4a6b-106">マップにより作成された XML 出力インスタンス メッセージを、送信先スキーマで指定されているネイティブ形式に変換する際に、シリアライズ エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f4a6b-106">The indicated serialization error was encountered when attempting to convert the XML output instance message produced by the map into the native format specified by the destination schema.</span></span>  
  
 <span data-ttu-id="f4a6b-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="f4a6b-107">**User Action**</span></span>  
  
 <span data-ttu-id="f4a6b-108">シリアライズ エラーを参考にして、マップに指定されている変換または送信先スキーマ、あるいはその両方を適宜修正してください。</span><span class="sxs-lookup"><span data-stu-id="f4a6b-108">Based on the indicated serialization error, make the appropriate corrections to either the transformations specified in the map, or to the destination schema, or to both.</span></span> <span data-ttu-id="f4a6b-109">送信先スキーマの BizTalk エディターで開きを使用すると役立つ場合があります、**スキーマの検証**、**インスタンスの検証**、および**インスタンスの生成**ときに利用可能なコマンドソリューション エクスプ ローラーでスキーマを右クリックするとします。</span><span class="sxs-lookup"><span data-stu-id="f4a6b-109">It may be helpful to open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands available when you right-click a schema in Solution Explorer.</span></span>