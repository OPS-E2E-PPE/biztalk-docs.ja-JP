---
title: "バイトのプロパティの値が無効です |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8599688-9f05-4983-8850-9ac1479ce9cc
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5789ae17b5127b58de45e5c4764b4ef490c43f1f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-byte-property-value-is-not-valid"></a>バイト型プロパティの値が無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|バッチ処理エンジン|  
|シンボル名|InvalidBytePropertyValue|  
|メッセージ テキスト|バイト型プロパティの値が無効です|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、必要なプロパティがバイト値であるが、入力された値がバイト値ではなかったため、[バッチ フィルター] ダイアログ ボックスの行のプロパティとして入力された値が無効なことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。 バイト値である必要があるプロパティとして入力された値が、実際にバイト値であることを確認します。