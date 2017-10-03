---
title: "ログ ファイルに情報を追跡する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, tracking
- DebugTrackingInterceptor
- Business Rules Framework, code samples
ms.assetid: c832b763-aa08-4a0e-9086-776dccb0a6ef
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cdaae8e727cedc784ecaade83178cf50f863f99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-log-tracking-information-to-file"></a><span data-ttu-id="e3c0f-102">追跡情報をファイルにログ記録する方法</span><span class="sxs-lookup"><span data-stu-id="e3c0f-102">How to Log Tracking Information to File</span></span>
<span data-ttu-id="e3c0f-103">ビジネス ルール エンジンを実行するとき、実行追跡情報がインターセプターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="e3c0f-103">When the Business Rule Engine executes, it passes execution tracking information to an interceptor.</span></span> <span data-ttu-id="e3c0f-104">ビジネス ルール エンジンは、BizTalk インターセプターを使用してメッセージ イベントとサービス インスタンス データを追跡するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="e3c0f-104">The engine is configured to use the BizTalk interceptor which is used when tracking message events and service instance data.</span></span> <span data-ttu-id="e3c0f-105">BizTalk オーケストレーション外部でエンジンを呼び出す場合、ポリシーを実行するときに使用されるインターセプターに情報を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="e3c0f-105">If you are calling the engine outside of BizTalk orchestration, you can pass the interceptor you want to use when you execute the policy.</span></span> <span data-ttu-id="e3c0f-106">BizTalk インターセプターだけでなく使用することも、 **DebugTrackingInterceptor**追跡情報をファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="e3c0f-106">In addition to the BizTalk interceptor, you can also use the **DebugTrackingInterceptor** to output the tracking information to file.</span></span> <span data-ttu-id="e3c0f-107">次のコード例は、使用する方法を示します**DebugTrackingInterceptor**です。</span><span class="sxs-lookup"><span data-stu-id="e3c0f-107">The following code example demonstrates how to use **DebugTrackingInterceptor**.</span></span>  
  
```  
DebugTrackingInterceptor tracker = new DebugTrackingInterceptor("TrackingOutput.txt");  
policy.Execute(shortTermFacts,tracker);  
```