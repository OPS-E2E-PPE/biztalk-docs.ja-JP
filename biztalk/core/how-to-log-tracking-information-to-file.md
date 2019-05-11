---
title: ログ ファイルに情報を追跡する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, tracking
- DebugTrackingInterceptor
- Business Rules Framework, code samples
ms.assetid: c832b763-aa08-4a0e-9086-776dccb0a6ef
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: facc8f6bf3e50e6aa267f1df8addc6ee1c2653a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384736"
---
# <a name="how-to-log-tracking-information-to-file"></a>ログ ファイルに情報を追跡する方法
ビジネス ルール エンジンを実行するときは、実行追跡インターセプターに情報を渡します。 エンジンを構成して、追跡メッセージ イベントおよびサービス インスタンス データで使用される BizTalk インターセプターを使用します。 BizTalk オーケストレーション外部でエンジンを呼び出す場合は、ポリシーを実行するときに使用するインターセプターに情報を渡すことができます。 BizTalk インターセプターだけでなく使用することも、 **DebugTrackingInterceptor**ファイルに追跡情報を出力します。 次のコード例は、使用する方法を示します**DebugTrackingInterceptor**します。  
  
```  
DebugTrackingInterceptor tracker = new DebugTrackingInterceptor("TrackingOutput.txt");  
policy.Execute(shortTermFacts,tracker);  
```