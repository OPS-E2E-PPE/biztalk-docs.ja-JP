---
title: 無効なセキュリティ値 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee380da7-c05e-4b9b-84ee-f7ffee90eb0e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ded2a080511992f5e85cda91b39dced703f452f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381208"
---
# <a name="invalid-security-value"></a>セキュリティの値が無効です
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                         X12Ta1InvalidSecurityValueDescription                          |
|  メッセージ テキスト   |                                 セキュリティの値が無効です                                 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、ISA04 フィールドのセキュリティ情報または UNB6.1 フィールドの受信者の参照/パスワードの値が、サービス スキーマ (BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema) で設定されたデータ型と桁数に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ISA04 フィールドが X12_AN データ型で、長さが 10 桁 (末尾のスペースの有無とは無関係) であるか、または UNB6.1 フィールドが EDIFACT_AN データ型で、長さが 1 ～ 14 文字の範囲であることを確認します。 インターチェンジを再送信します。