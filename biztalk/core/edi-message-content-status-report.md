---
title: "EDI メッセージ コンテンツのステータス レポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29acab25-354d-42f0-b6e3-37ebca47addb
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62dbb260bb23e3ed5de7e8d416158a0e142c6c32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edi-message-content-status-report"></a>EDI メッセージ コンテンツのステータス レポート

## <a name="overview"></a>概要
この状態レポートには、トランザクション セットのヘッダーとペイロードが表示されます。 トランザクション セットの詳細ステータス レポート内のトランザクション セットを右クリックし、をクリックしてこのレポートを表示する**トランザクション セットのコンテンツ**です。  
  
 このレポートは、選択した場合にのみ使用可能な**レポート用にトランザクション セット/ペイロードを格納**関連するパーティの EDI のプロパティ ダイアログ ボックスの 全般 ページのプロパティです。  
  
 このレポートには、次の 2 つのコンテンツ ビューが用意されています。  
  
-   トランザクション セットの内容を人間が判読できる形式 (EDI テキスト ファイルなど) で表示する、テキスト形式のビュー。 このビューでは、ST ヘッダー、トランザクション セットのペイロード、および SE トレーラが表示されます。各セグメントは別々の行に表示されます。  
  
-   区切りなしテキスト形式のトランザクション セットの内容と、トランザクション セットに含まれる各 ASCII 文字の 16 進数表記の表を表示する、バイナリ形式のビュー。  
  
