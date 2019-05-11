---
title: バッチ処理オーケストレーションでバッチ送信中に永続化例外が発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf6e832f-9d01-46e7-aaf5-2b402d509fac
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99cb8d0456152b5a4e3dc24d9f0d71eeb414eb80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347023"
---
# <a name="a-persistence-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a>バッチ処理オーケストレーションでバッチ送信中に永続化例外が発生しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                     |
| 製品バージョン |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                 |
|    イベント ID     |                                                                                             -                                                                                              |
|  イベント ソース   |                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                   |
|    コンポーネント    |                                                                                      バッチ処理エンジン                                                                                       |
|  シンボル名  |                                                                                PersistenceExceptionOccured                                                                                 |
|  メッセージ テキスト   | バッチ処理オーケストレーションでバッチ送信中に永続化例外が発生しました。 バッチ Id = {0}、ErrorMessage ={1}します。 送信ポート サブスクリプションを確認し、それらを修正してください。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server 送信できなかったこと、バッチ インターチェンジのインターチェンジをサブスクライブした送信ポートがないため、ことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、送信ポートには、次のフィルター プロパティを設定して、その送信ポートがバッチにはサブスクライブすることを確認します。EDI です。DestinationPartyName = \<PartyName\>、EDI です。BatchEncodingType = EDIFACT または X12、および EDI です。ToBeBatched = False。