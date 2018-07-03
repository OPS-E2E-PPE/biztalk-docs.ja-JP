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
ms.openlocfilehash: e2bc9775da2fcbef756774c576074b471e808484
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977091"
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