---
title: "例外管理フレームワーク |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b5aebc0-2467-4f48-a385-056507ed1c1e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 593937dca387d79a127117ee96005b3dc48fbdc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="exception-management-framework"></a>例外管理フレームワーク
ESB 例外管理フレームワーク内で発生する可能性がありますのあるすべての例外を管理するためメッセージ指向の統合されたエラーの生成メカニズムを提供する、[!INCLUDE[prague](../includes/prague-md.md)]環境。 ESB 例外管理フレームワークでは、メッセージ BizTalk Server できませんでしたメッセージのルーティング機構からに加えて、例外の発行サービス経由で公開された例外のメッセージを受信できます。  
  
 フレームワークは、エラー メッセージの作成、発行、および BizTalk Server 2006 で初めて導入された、BizTalk Server 失敗したメッセージのルーティング機能をレプリケートする、オーケストレーション プロセスからの管理の API を提供します。 さらに、フレームワークを拡充、ビジネス アクティビティ監視 (BAM) 追跡と表示の例外管理データベースに、最終的な出力を公開および報告における、ESB で適用するすべての例外を正規化する機能を提供します。管理ポータル。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ESB 例外管理フレームワークをサポートする、次のパイプライン コンポーネントが含まれています。  
  
-   **例外エラー プロセッサ パイプライン コンポーネント。**このコンポーネントは、ESB 例外出口に関連付けられているパイプラインの一部として含まれています。 この出口は、ルーティング機構、BizTalk Server の失敗したメッセージによって生成される例外だけでなく、すべての ESB で生成されたエラー メッセージをサブスクライブします。 コンポーネントのルートが ESB 例外 ESB 管理ポータル、管理データベースへのメッセージをエラーまたは構成することを別の場所にルーティングします。 パイプライン コンポーネントは、すべてのエラー メッセージとメタデータを含む例外を拡充し、それらを共通の形式に正規化します。  
  
-   **BAM の追跡のパイプライン コンポーネント。**このコンポーネントをインターセプトし、BizTalk Server BAM サブシステム内での例外情報を記録し、例外管理フレームワーク内で例外エラー Processor パイプラインによって排他的に使用されます。 提供される[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]省略可能な追跡機能と例外についての BAM の使用方法を示す例を示します。  
  
 例外管理フレームワークの詳細については、次を参照してください。 [ESB 例外管理を使用して](../esb-toolkit/using-esb-exception-management.md)です。