---
title: ルーティング オーケストレーションの実行中に例外が発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68ec8921-ba05-496e-8dcc-fd8994fcb8b7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 917349fe1157bc672ad3f3897f504625c59e7ba3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007323"
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-routing-orchestration"></a>ルーティング オーケストレーションの実行中に例外が発生しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------|
|  製品名   |       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| 製品バージョン |                   [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                   |
|    イベント ID     |                                               -                                                |
|  イベント ソース   |     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI     |
|    コンポーネント    |                                        バッチ処理エンジン                                         |
|  シンボル名  |                                 ExceptionOccuredDuringRouting                                  |
|  メッセージ テキスト   | ルーティング オーケストレーションの実行中に例外が発生しました。 ErrorMessage = {0} |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、ErrorMessage フィールドに示されたエラー状態のために、ルーティング オーケストレーションが XML バッチ要素の各コピーを正しく処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ErrorMessage フィールドからエラーの状態を特定し、エラーを解決してメッセージを再送信します。