---
title: 例外管理フレームワーク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b5aebc0-2467-4f48-a385-056507ed1c1e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fc334dd93c0ad53737b1fe36d50355cecae565a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017844"
---
# <a name="exception-management-framework"></a>例外管理フレームワーク
ESB 例外管理フレームワークでは、BizTalk Server 環境内で発生するすべての例外を管理するための統一されたメッセージ指向の障害生成メカニズムを提供します。 ESB 例外管理フレームワークでは、メッセージ BizTalk Server できませんでしたメッセージのルーティング メカニズムから以外にも、例外の発行サービス経由で公開された例外メッセージを受信できます。  
  
 フレームワークは、エラー メッセージの作成、発行、および BizTalk Server 2006 で初めて導入された、BizTalk Server 失敗したメッセージのルーティング機能をレプリケートする、オーケストレーション プロセスからの管理の API を提供します。 さらに、フレームワークはビジネス アクティビティ監視 (BAM) 追跡、および最終的な出力を表示するため、例外管理データベースに公開および、ESB でのレポートの適用、拡充、すべての例外を正規化するための機能を提供します。管理ポータル。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ESB 例外管理フレームワークをサポートする次のパイプライン コンポーネントが含まれています。  
  
- <strong>例外エラー プロセッサ パイプライン コンポーネント。</strong>このコンポーネントは、- 傾斜オフ ESB 例外に関連付けられているパイプラインの一部として含まれています。 この無効-ごとの傾斜増加は、BizTalk Server の失敗したメッセージ ルーティング機構によって生成される例外だけでなく、すべての ESB で生成されたエラー メッセージをサブスクライブします。 コンポーネントのルートが ESB 例外管理 ESB 管理ポータルのデータベースにメッセージをエラーまたは構成できます。 別の場所にルーティングします。 パイプライン コンポーネントは、によってすべてのエラー メッセージとメタデータを持つ例外が追加されましたし、それらを共通の形式に正規化します。  
  
- <strong>BAM の追跡のパイプライン コンポーネント。</strong>このコンポーネントをインターセプトし、BizTalk Server BAM サブシステム内での例外情報を記録し、例外管理フレームワーク内で例外フォールト プロセッサ パイプラインで排他的に使用します。 提供される[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]省略可能な追跡機能と例外についての BAM の使用方法を示すサンプルに示します。  
  
  例外管理フレームワークの詳細については、[ESB 例外管理を使用して](../esb-toolkit/using-esb-exception-management.md)を参照してください。