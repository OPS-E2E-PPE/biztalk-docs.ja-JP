---
title: 無効な区切り記号の許容範囲外である少なくとも 1 つの区切り記号の設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1286559-765b-4728-945d-cf3386e1ba06
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebda7e3ebfe2adc0084b672a2f66ed1ad639c943
ms.sourcegitcommit: c3070a7a3f332857357f056dc632829b43869c17
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2018
ms.locfileid: "51630367"
---
# <a name="invalid-delimiter-set-because-at-least-one-of-the-delimiters-is-outside-the-allowed-range"></a>1 つ以上の区切り記号が有効範囲外であるため、設定されている区切り記号は無効です
## <a name="details"></a>詳細  
  
|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  製品名   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| 製品バージョン |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    イベント ID     |                                                   -                                                    |
|  イベント ソース   |         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI         |
|    コンポーネント    |                                               EDI エンジン                                               |
|  シンボル名  |                                          DelimiterOutOfRange                                           |
|  メッセージ テキスト   | 無効な区切り記号セット{0}、区切り記号の少なくとも 1 つが、0 127 までからの許容範囲外 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジの 1 つ以上の区切り記号が、ASCII 文字セットの値の範囲外だったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの各区切り記号が ASCII 文字セットの範囲内であることを確認し、インターチェンジを再送信してもらいます。
