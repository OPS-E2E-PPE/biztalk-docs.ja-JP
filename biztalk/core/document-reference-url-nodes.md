---
title: ドキュメント参照 URL ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Document Reference URL nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- definition files [BAM], related documents
ms.assetid: 38c8ae50-ed56-451c-9549-db852d4770e5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c9cbc37b48ad6592215723695b54edc17e834b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350962"
---
# <a name="document-reference-url-nodes"></a>ドキュメント参照 URL ノード
ドキュメント参照 URL ノードは、ナレッジ ワーカーが作成した監視モデルから開発者がインポートするアクティビティ定義ファイルに存在します。 ドキュメント参照 URL ノードには、このアクティビティに関連するドキュメントを格納している場所への参照が含まれます。 ドキュメント、購買発注書ドキュメントをポイントして、基になる可能性があります、購買注文の承認ワークフロー ドキュメント参照 URL を表すアクティビティなどの任意の型を指定できます。  
  
## <a name="working-with-document-reference-url-nodes"></a>ドキュメント参照 URL ノードの操作  
 ドキュメント参照 URL のデータ ソースは、通常、 **MessageRefURL** BizTalk Server システムのプロパティ。 Url を保存し、カスタム スキーマからドキュメント参照 URL プロパティをマップするカスタム スキーマを使用することもできます。  
  
 ドキュメント参照 Url に関する注意事項:  
  
-   1 つまたは複数のドキュメント参照 Url を追加できますが、各ノードは、アクティビティ内で一意の名前をいる必要があります。  
  
-   **MessageRefURL**ドキュメント参照 URL ノードを設定するために必要なプロパティは、値は、WSS、FILE および FTP のトランスポート アダプターの場合のみ設定されます。  
  
-   ビジネス エンドユーザーは、BAM ポータルで、この参照を表示できますが、参照 URL の主な目的は、エンドユーザーに提供できるようにカスタム ユーザー インターフェイス開発者へのアクセスを許可するドキュメントの情報を関連付けられています。  BAM ポータルでドキュメントの参照を表示する方法の詳細については、次を参照してください。[関連ドキュメント](../core/related-documents.md)します。  
  
## <a name="see-also"></a>参照  
 [TPE アクティビティ ビューのノード](../core/tpe-activity-view-nodes.md)