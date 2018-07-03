---
title: 区切り記号が一意でない、セグメントとコンポーネント区切り記号が同じ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13c41899-02af-4678-a4ad-f3dc48c1fdfb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6068b13502b8893fd5065957b6dd73072236126
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983779"
---
# <a name="delimiters-are-not-unique-segment-and-component-separators-are-the-same"></a>区切り記号が一意ではなく、セグメントとコンポーネントの区切り記号が同じです
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                                           -                                            |
|  メッセージ テキスト   |        区切り記号が一意ではなく、セグメントとコンポーネントの区切り記号が同じです        |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、セグメント終端記号とコンポーネント区切り記号が同じ値であったため、EDI 送信パイプラインで送信インターチェンジを処理できなかったことを示します。 X12 インターチェンジでは、セグメント終端記号は ISA セグメントの最後の文字位置にある文字であり、コンポーネント区切り記号は ISA16 フィールド内の文字です。 EDIFACT インターチェンジでは、セグメント終端記号は UNA6 フィールド内の文字であり、コンポーネント区切り記号は UNA1 フィールド内の文字です。 保存されたバッチ シナリオでは、同じ値を持つ 2 つの区切り記号が存在する (ただし、エラー状態を引き起こす) 可能性があります。つまり、インターチェンジがパススルー送信を経由して受信され、次にメッセージ ボックス内の XML ファイルとして送信ポートによって取得される場合です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジのセグメント終端記号またはコンポーネント区切り記号のいずれかの値を変更し、インターチェンジを再送信します。