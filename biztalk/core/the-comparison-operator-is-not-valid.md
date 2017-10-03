---
title: "比較演算子が有効ではありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8383230d-9bf6-4bc5-9300-4cfd0ad38f28
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12652fbd59fde08d8321c6fdd85bb0998ce8ccc6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-comparison-operator-is-not-valid"></a>比較演算子が無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|バッチ処理エンジン|  
|シンボル名|InvalidComparisonOperator|  
|メッセージ テキスト|比較演算子が無効です。 例外メッセージ = {0}|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、[バッチ フィルター] ダイアログ ボックスの行に入力された比較演算子が、プロパティと値に対して有効ではなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。 [バッチ フィルター] グリッドの行に入力された比較演算子が、プロパティと値に対して有効なことを確認します。