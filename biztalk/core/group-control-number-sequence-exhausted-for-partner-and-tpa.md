---
title: パートナーと TPA のグループの制御番号のシーケンスが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf341f8d-02ec-4618-a980-c8ac90654b1a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5ff33fb039c1cd4e88e173bb657471ce9f2c738
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387589"
---
# <a name="group-control-number-sequence-exhausted-for-partner-and-tpa"></a>グループ制御番号シーケンスがパートナーと TPA の
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                      |
| 製品バージョン |                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                  |
|    イベント ID     |                                                                              -                                                                               |
|  イベント ソース   |                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                    |
|    コンポーネント    |                                                                          EDI エンジン                                                                          |
|  シンボル名  |                                                              EdiControlNumberExhaustedForParty                                                               |
|  メッセージ テキスト   | パートナー グループ制御番号のシーケンスが '{1}'for 'TPA{2}'。 シーケンスをリセット{2}- BizTalk Server 管理コンソールを使用して EDI のプロパティ。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server でアグリーメントにグループ コントロールの範囲が使い果たされたために、ドキュメントを処理できなかったことを示します{2}します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、制御番号をリセットするチェック ボックスをオンしてください、{2}契約または増加コントロール番号の範囲または契約書に制御番号の範囲指定に対するリセット ボタンをクリックします。