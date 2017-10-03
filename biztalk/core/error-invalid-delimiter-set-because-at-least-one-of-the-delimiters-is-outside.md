---
title: "無効な区切り記号の許容範囲外にあるため、区切り記号の少なくとも 1 つの設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1286559-765b-4728-945d-cf3386e1ba06
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c70722adc1a099d340b862d38574b44391954aa4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-delimiter-set-because-at-least-one-of-the-delimiters-is-outside-the-allowed-range"></a>1 つ以上の区切り記号が有効範囲外であるため、設定されている区切り記号は無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|DelimiterOutOfRange|  
|メッセージ テキスト|無効な区切り記号が設定されています ({0})。1 つ以上の区切り記号が、有効範囲である 0 ～ 127 の範囲外です。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジの 1 つ以上の区切り記号が、ASCII 文字セットの値の範囲外だったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの各区切り記号が ASCII 文字セットの範囲内であることを確認し、インターチェンジを再送信してもらいます。