---
title: "整数プロパティの値が有効な整数ではありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa97f3dd-4a01-4007-b23a-820cbebbc083
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32aebb74d937bb6b57d463598e178ad4d1ca280b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-integer-property-value-is-not-a-valid-integer"></a>整数プロパティの値が有効な整数ではありません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|バッチ処理エンジン|  
|シンボル名|InvalidIntegerPropertyValue|  
|メッセージ テキスト|整数プロパティの値が有効な整数ではありません|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、必要なプロパティが整数値であるが、入力された値が整数値ではなかったため、[バッチ フィルター] ダイアログ ボックスの行のプロパティとして入力された値が無効なことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。 整数値である必要があるプロパティとして入力された値が、実際に整数値であることを確認します。