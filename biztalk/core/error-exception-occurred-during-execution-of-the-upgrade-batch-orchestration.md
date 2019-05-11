---
title: アップグレード バッチ オーケストレーションの実行中に例外が発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2221a498-98aa-43ab-bc4e-34dcbd92dcf0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df73d4fa4d8d59caed5c8e8f34e52d2b60d4c7cf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348433"
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-upgrade-batch-orchestration"></a>アップグレード バッチ オーケストレーションの実行中に例外が発生しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------|
|  製品名   |          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| 製品バージョン |                      [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    イベント ID     |                                                   -                                                   |
|  イベント ソース   |                                          BizTalk Server EDI                                           |
|    コンポーネント    |                                            バッチ処理エンジン                                            |
|  シンボル名  |                                     ExceptionOccuredDuringUpgrade                                     |
|  メッセージ テキスト   | アップグレード バッチ オーケストレーションの実行中に例外が発生しました。 ErrorMessage = {0} |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、ErrorMessage フィールドに示されたエラー状態のために、アップグレード バッチ オーケストレーションでメッセージを正しく処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ErrorMessage フィールドからエラーの状態を判断し、エラーを解決してメッセージを再送信します。