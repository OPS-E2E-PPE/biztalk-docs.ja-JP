---
title: ドキュメント参照 URL ノード |Microsoft ドキュメント
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
ms.openlocfilehash: c7939a7e74483b8df192530fd9da2deafeda0681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238970"
---
# <a name="document-reference-url-nodes"></a>ドキュメント参照 URL ノード
ドキュメント参照 URL ノードは、ナレッジ ワーカーが作成した監視モデルから開発者がインポートする、アクティビティ定義ファイル内に存在します。 ドキュメント参照 URL ノードには、このアクティビティに関連するドキュメントが格納されている場所への参照が含まれます。 たとえば注文書の承認ワーク フローを表すアクティビティなど、すべての種類のドキュメントが対象になります。ドキュメント参照 URL は、基になる注文書を指すこともあります。  
  
## <a name="working-with-document-reference-url-nodes"></a>ドキュメント参照 URL ノードの操作  
 ドキュメント参照 URL のデータ ソースは、通常、 **MessageRefURL** BizTalk Server システムのプロパティです。 URL を保存するカスタム スキーマを使用して、カスタム スキーマからドキュメント参照 URL にプロパティをマップすることもできます。  
  
 ドキュメント参照 URL に関する注意事項を次に示します。  
  
-   1 つ以上のドキュメント参照 URL を追加できますが、各ノードの名前はアクティビティ内で一意である必要があります。  
  
-   **MessageRefURL**ドキュメント参照 URL ノードを設定するために必要なプロパティは、値は、WSS、FILE および FTP のトランスポート アダプターの場合のみ設定されます。  
  
-   ビジネス エンドユーザーは、BAM ポータルでこの参照を表示できますが、参照 URL の主な目的はカスタム ユーザー インターフェイスの開発者にアクセスするために使用できるように関連するドキュメントの情報をエンドユーザーに提示するようにします。  BAM ポータルでドキュメントの参照を表示する方法の詳細については、次を参照してください。[関連ドキュメント](../core/related-documents.md)です。  
  
## <a name="see-also"></a>参照  
 [TPE アクティビティ ビューのノード](../core/tpe-activity-view-nodes.md)