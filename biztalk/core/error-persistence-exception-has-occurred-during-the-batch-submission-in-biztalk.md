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
ms.openlocfilehash: e8a1277dd26fcb2036e3378f7fa6d22067a1f7e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020920"
---
# <a name="a-persistence-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a>バッチ処理オーケストレーションでのバッチ送信中に永続化例外が発生しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                     |
| 製品バージョン |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                 |
|    イベント ID     |                                                                                             -                                                                                              |
|  イベント ソース   |                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                   |
|    コンポーネント    |                                                                                      バッチ処理エンジン                                                                                       |
|  シンボル名  |                                                                                PersistenceExceptionOccured                                                                                 |
|  メッセージ テキスト   | バッチ処理オーケストレーションでのバッチ送信中に永続化例外が発生しました。 バッチ Id = {0}、ErrorMessage ={1}します。 送信ポートのサブスクリプションを確認して修正してください。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジをサブスクライブした送信ポートがなかったため、BizTalk Server が、バッチ化されたインターチェンジを送信できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、送信ポートには、次のフィルター プロパティを設定して送信ポートがサブスクライブをバッチに確認します。 EDI です。DestinationPartyName = \<PartyName\>、EDI です。BatchEncodingType = EDIFACT または X12、および EDI です。ToBeBatched = False。