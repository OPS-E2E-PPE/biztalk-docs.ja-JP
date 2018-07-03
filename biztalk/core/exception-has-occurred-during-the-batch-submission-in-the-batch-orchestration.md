---
title: バッチ処理オーケストレーションでバッチ送信中に例外が発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c58b2fa9-d036-4e09-a0f8-77a2f983881a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 838e9aff43dd260fd4af8e46ca88782c2389dfc7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971531"
---
# <a name="an-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a>バッチ処理オーケストレーションでのバッチ送信中に例外が発生しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------|
|  製品名   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                  |
| 製品バージョン |                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                              |
|    イベント ID     |                                                          -                                                          |
|  イベント ソース   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                |
|    コンポーネント    |                                                   バッチ処理エンジン                                                   |
|  シンボル名  |                                                  ExceptionOccured                                                   |
|  メッセージ テキスト   | バッチ処理オーケストレーションでのバッチ送信中に例外が発生しました。 バッチ Id = {0}、エラー メッセージ {1} |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、ErrorMessage フィールドに示されたエラー状態のために、バッチ処理オーケストレーションがバッチにバッチ要素を追加できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ErrorMessage フィールドからエラーの状態を判断し、エラーを解決してメッセージを再送信します。