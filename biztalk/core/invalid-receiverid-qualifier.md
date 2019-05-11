---
title: ReceiverId が無効な修飾子 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52d60f7e-6f16-424d-91b8-dc8181206249
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e023f205252b04dc5122cfa8c01b617758a25771
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381329"
---
# <a name="invalid-receiverid-qualifier"></a>ReceiverId が無効な修飾子
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                      X12Ta1InvalidReceiverIdQualifierDescription                       |
|  メッセージ テキスト   |                              ReceiverId が無効な修飾子                              |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、エントリのため、受信パイプラインが受信インターチェンジが処理しないことを示します [isa07] フィールドの受信者の修飾子 (x12 インターチェンジ) または受信者コードの修飾子 (EDIFACT の [unb3.2] フィールドインターチェンジの場合) では、サービス スキーマ (X12ServiceSchema または EdifactServiceSchema) で設定されている列挙の値が一致しませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ISA07 フィールドまたは UNB3.2 フィールドが、サービス スキーマで設定されている列挙のいずれかの値と一致するようにします。 インターチェンジを再送信します。