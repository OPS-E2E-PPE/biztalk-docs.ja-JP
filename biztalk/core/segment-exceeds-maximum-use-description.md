---
title: セグメントが説明の最大使用数を超えています。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4e1704a-5d49-4549-af50-d1a89a1e70f0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7a260d68d608bb88cc0252ad2a1ec5c125e2b0a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279815"
---
# <a name="segment-exceeds-maximum-use-description"></a>セグメントが説明されている最大使用数を超えています
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                         X12SegmentExceedsMaximumUseDescription                         |
|  メッセージ テキスト   |                        セグメントが説明されている最大使用数を超えています                         |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、スキーマで許可されているよりも多くの数のセグメントがインターチェンジに含まれていたため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、許可されている最大数を超える数のセグメントがインターチェンジに含まれていないことを確認し、インターチェンジを再送信します。