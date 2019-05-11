---
title: 必須のセグメントがありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e459a22-8de5-426a-a46a-1d0ab72b532d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05a2c3a1ed86e57a307c5b7e335febff87ce53cf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380134"
---
# <a name="mandatory-segment-missing"></a>必須のセグメントがありません
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                         X12MandatorySegmentMissingDescription                          |
|  メッセージ テキスト   |                               必須のセグメントがありません                                |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、メッセージ スキーマで要求されている (minOccurs が 0 より大きい) セグメントがインターチェンジに含まれていなかったため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、メッセージ スキーマで要求されているすべてのセグメントがインターチェンジに含まれていることを確認し、メッセージを再送信してもらいます。