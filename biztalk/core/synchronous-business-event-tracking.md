---
title: 同期ビジネス イベントの追跡 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, BAM
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 302c7918-bc62-46f1-a949-fbf94a7073e3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a97cfac1eb2b4fa13e0f3d94867d2a4993c6ba5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321827"
---
# <a name="synchronous-business-event-tracking"></a>同期ビジネス イベントの追跡
BAM にイベント データを送信する最も簡単な方法は、DirectEventStream クラスのインスタンスを使用することです。 このクラスでは、アプリケーションの現在のトランザクション (存在する場合) のコンテキストで、BAM プライマリ インポート データベースにイベント データを直接保存します。  
  
 この操作中にエラーが発生した場合、メソッドを呼び出すと、呼び出し元のアプリケーションに例外がスローされて戻されます。 たとえば、UpdateActivity に渡された項目の名前が BAM アクティビティ定義と一致しない場合、または BAM 定義をまだ展開していなかった場合に、この現象が発生します。 これにより、呼び出し元のアプリケーションでは BAM データを保存するときに、すべてのエラーをキャッチして、回復できます。その結果、この BAM データを後から容易に管理できます。  
  
 呼び出し元のアプリケーションは、BAM がすべてのストアド プロシージャやトリガーを実行するまで待機する必要があるため、データを同期的に保存することはパフォーマンスに影響する場合があります。  
  
## <a name="see-also"></a>参照  
 [非同期ビジネス イベントの追跡](../core/asynchronous-business-event-tracking.md)