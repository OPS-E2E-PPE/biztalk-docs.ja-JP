---
title: 区切り記号が一意で、フィールドではないと、コンポーネントの区切り記号が同じ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cba15b30-b07d-4caa-8c43-6b4d8c4ca81c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a40e429d8d34f2accd5d755741a174fc972985d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352180"
---
# <a name="delimiters-are-not-unique-field-and-component-separator-are-the-same"></a>区切り記号が一意ではなく、フィールドとコンポーネントの区切り記号が同じです
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                                           -                                            |
|  メッセージ テキスト   |         区切り記号が一意ではなく、フィールドとコンポーネントの区切り記号が同じです          |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、データ要素とコンポーネントの区切り記号の値が同じだったため、EDI 送信パイプラインで送信インターチェンジを処理できなかったことを示します。 X12 インターチェンジでは、データ要素の区切り記号は ISA セグメントの 4 番目の文字の位置にある文字であり、コンポーネントの区切り記号は ISA16 フィールドの文字です。 EDIFACT インターチェンジでは、データ要素の区切り記号は UNA2 フィールドの文字であり、コンポーネントの区切り記号は UNA1 フィールドの文字です。 保存されたバッチ シナリオでは、同じ値を持つ 2 つの区切り記号が存在する (ただし、エラー状態を引き起こす) 可能性があります。つまり、インターチェンジがパススルー送信を経由して受信され、次にメッセージ ボックス内の XML ファイルとして送信ポートによって取得される場合です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、データ要素、またはコンポーネントの区切り記号のどちらかの値を変更し、インターチェンジを再送信します。