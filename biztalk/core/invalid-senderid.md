---
title: Senderid が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be8055ab-8aba-49ac-ad33-fb33d4ff3e8b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61ae69c91cc5e44d29e0f99abff9198632a02553
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381234"
---
# <a name="invalid-senderid"></a>SenderId が無効です
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                            X12Ta1InvalidSenderIdDescription                            |
|  メッセージ テキスト   |                                    SenderId が無効です                                    |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、ISA06 フィールドの送信者 ID または UNB2.1 フィールドの送信者 ID が、サービス スキーマ (BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema) で確立されたデータ型と桁数に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ISA06 フィールドが X12_AN データ型で、15 桁 (末尾のスペースの有無とは無関係) であるか、または UNB2.1 フィールドが EDIFACT_AN データ型で、1 ～ 35 文字の範囲であることを確認します。 インターチェンジを再送信します。