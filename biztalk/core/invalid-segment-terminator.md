---
title: 無効なセグメント終端記号 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 508dac21-4731-439d-bf4a-a50858f1ffa0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ebd39a1711f4e1af15735f5a6d2e9523c490036
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330474"
---
# <a name="invalid-segment-terminator"></a>セグメント終端記号が無効です
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                       X12Ta1InvalidSegmentTerminatorDescription                        |
|  メッセージ テキスト   |                               セグメント終端記号が無効です                               |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジ内のセグメント終端記号の値が ASCII 文字セット内の文字に制限されていなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。 X12 では、セグメント終端記号は ISA セグメントの最後の文字として定義されます。 EDIFACT では、セグメント終端記号は UNA6 フィールドです。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、セグメント終端記号 (X12 インターチェンジでは ISA セグメントの最後の文字、または EDIFACT インターチェンジの UNA6 フィールド) が、ASCII 文字セットの文字に制限されていることを確認します。 インターチェンジを再送信します。