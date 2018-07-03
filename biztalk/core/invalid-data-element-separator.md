---
title: 無効なデータ要素区切り記号 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76c50a8b-274f-4f4a-9826-4f6f8123e9d1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3fbc355c6a89bd69364200dcd20ca257fc9dc54
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972595"
---
# <a name="invalid-data-element-separator"></a>データ要素区切り記号が無効です。
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                      X12Ta1InvalidDataElementSeparatorDescription                      |
|  メッセージ テキスト   |                             データ要素区切り記号が無効です。                             |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジ内のセグメント終端記号の値が ASCII 文字セット内の文字に制限されていなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。 X12 で、セグメント終端記号は ISA セグメントの 4 番目の文字として定義されます。 EDIFACT では、セグメント終端記号は UNA2 フィールドです。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、セグメント終端記号 (X12 インターチェンジの ISA セグメントの 4 番目の文字、または EDIFACT インターチェンジの UNA2 フィールド) が、ASCII 文字セットの文字に制限されていることを確認します。 インターチェンジを再送信します。