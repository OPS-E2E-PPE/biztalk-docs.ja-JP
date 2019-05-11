---
title: 無効な時間 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6942eb77-3ef1-460c-ac4f-8f1339c25d1b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c305afe09a7ff116d04554bb1c1962a137274945
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330092"
---
# <a name="invalid-time"></a>時刻が無効です
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                              X12Ta1InvalidTimeDescription                              |
|  メッセージ テキスト   |                                      時刻が無効です                                      |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、データ要素の時刻値が、EDI スキーマで指定されたデータ型に準拠していなかったか、または X12 インターチェンジの GS05 フィールド ヘッダーの時刻値が、サービス スキーマ (BaseArtifacts.dll 内の X12ServiceSchema) に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。 X12 の場合、サービス スキーマは、GS05 フィールドの時刻を X12_TM データ型として、4 ～ 8 文字の長さで定義します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、データ要素の時刻値が、EDI スキーマで指定されたデータ型に準拠しているか、または X12 インターチェンジの GS05 ヘッダーの時刻値がサービス スキーマに準拠していることを確認し、インターチェンジを再送信してもらいます。