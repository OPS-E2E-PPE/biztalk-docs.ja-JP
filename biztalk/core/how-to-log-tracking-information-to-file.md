---
title: ログ ファイルに情報を追跡する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 6cdaae8e727cedc784ecaade83178cf50f863f99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254714"
---
# <a name="how-to-log-tracking-information-to-file"></a>追跡情報をファイルにログ記録する方法
ビジネス ルール エンジンを実行するとき、実行追跡情報がインターセプターに渡されます。 ビジネス ルール エンジンは、BizTalk インターセプターを使用してメッセージ イベントとサービス インスタンス データを追跡するように構成されています。 BizTalk オーケストレーション外部でエンジンを呼び出す場合、ポリシーを実行するときに使用されるインターセプターに情報を渡すことができます。 BizTalk インターセプターだけでなく使用することも、 **DebugTrackingInterceptor**追跡情報をファイルに出力します。 次のコード例は、使用する方法を示します**DebugTrackingInterceptor**です。  
  
```  
DebugTrackingInterceptor tracker = new DebugTrackingInterceptor("TrackingOutput.txt");  
policy.Execute(shortTermFacts,tracker);  
```