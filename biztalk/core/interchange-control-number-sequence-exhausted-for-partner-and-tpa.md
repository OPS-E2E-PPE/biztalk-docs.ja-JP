---
title: パートナーと TPA のインターチェンジ制御番号シーケンスが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e77c0574-bc51-4690-a7f6-5702f6486f05
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad35d7ddd35b6f21b2aef73cd7ddf12fe42ebcc2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331695"
---
# <a name="interchange-control-number-sequence-exhausted-for-partner-and-tpa"></a>パートナーと TPA のインターチェンジ制御番号シーケンス
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                         |
| 製品バージョン |                                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                     |
|    イベント ID     |                                                                                 -                                                                                  |
|  イベント ソース   |                                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                       |
|    コンポーネント    |                                                                             EDI エンジン                                                                             |
|  シンボル名  |                                                                 EdiControlNumberExhaustedForParty                                                                  |
|  メッセージ テキスト   | パートナーのインターチェンジ制御番号シーケンスが '{1}'for 'TPA{2}'。 シーケンスをリセット{2}- BizTalk Server 管理コンソールを使用して EDI のプロパティ。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server でのアグリーメントのインターチェンジ制御の範囲が使い果たされたために、ドキュメントを処理できなかったことを示します{2}します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、制御番号をリセットするチェック ボックスをオンしてください、{2}契約または増加コントロール番号の範囲または契約書に制御番号の範囲指定に対するリセット ボタンをクリックします。