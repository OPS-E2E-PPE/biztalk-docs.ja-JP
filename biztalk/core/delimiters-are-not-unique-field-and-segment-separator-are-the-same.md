---
title: "区切り記号が一意ではない、フィールドとセグメントの区切り記号は、同じ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1441434a-e969-4803-8e44-c7738d9b23ed
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 440ffb1213936fba4b08a8ee478f6c141eba38fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="delimiters-are-not-unique-field-and-segment-separator-are-the-same"></a>区切り記号が一意ではなく、フィールドとセグメントの区切り記号が同じです
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|-|  
|メッセージ テキスト|区切り記号が一意ではなく、フィールドとセグメントの区切り記号が同じです|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、データ要素区切り記号とセグメント区切り記号が同じ値であったため、EDI 送信パイプラインで送信インターチェンジを処理できなかったことを示します。 X12 インターチェンジでは、データ要素の区切り記号は ISA セグメントの 4 番目の文字位置にある文字であり、セグメント区切り記号は ISA セグメントの最後の文字位置にある文字です。 EDIFACT インターチェンジでは、データ要素の区切り記号は UNA2 フィールド内の文字であり、セグメント区切り記号は UNA6 フィールド内の文字です。 保存されたバッチ シナリオでは、同じ値を持つ 2 つの区切り記号が存在する (ただし、エラー状態を引き起こす) 可能性があります。つまり、インターチェンジがパススルー送信を経由して受信され、次にメッセージ ボックス内の XML ファイルとして送信ポートによって取得される場合です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジのデータ要素の区切り記号またはセグメント区切り記号のいずれかの値を変更し、インターチェンジを再送信します。