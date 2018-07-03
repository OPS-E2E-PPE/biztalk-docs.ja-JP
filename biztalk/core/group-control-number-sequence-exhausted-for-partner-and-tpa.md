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
ms.openlocfilehash: 212c9c15cc6ddba30acbbac6cd6bcb983bcb9713
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976627"
---
# <a name="group-control-number-sequence-exhausted-for-partner-and-tpa"></a>パートナーと TPA のグループ制御番号のシーケンスが終了しました
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
 このエラー/警告/情報イベントは、グループ制御の範囲が {2} のアグリーメントにすべて使用されたため、BizTalk Server がドキュメントを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、チェック ボックスをオンにして {2} アグリーメントの制御番号をリセットするか、制御番号の範囲を大きくするか、またはアグリーメントの制御番号範囲指定に対するリセット ボタンを押します。