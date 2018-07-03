---
title: このインスタンスがパートナーの [Batching Service] ウィンドウの外側が |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e420d75-11fd-4221-9d97-814ca6e48c81
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a741439b5d6691a3218811568087450f2008b0ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966483"
---
# <a name="this-instance-is-outside-the-batching-service-window-for-the-partner"></a>このインスタンスはパートナーの [Batching Service] ウィンドウ内にありません
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                    バッチ処理エンジン                                     |
|  シンボル名  |                              OutsideBatchingServiceWindow                              |
|  メッセージ テキスト   |          このインスタンスはパートナーの [Batching Service] ウィンドウ内にありません          |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、バッチ処理オーケストレーションのインスタンスがパーティのアクティベーションの範囲外であったため、インスタンスを開始できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、パーティの [EDI のプロパティ] の [インターチェンジのバッチ作成用の設定] ページを開き、オーケストレーション インスタンスがアクティベーションの範囲内にあることを確認します。 そうでない場合、開始時間プロパティを変更し、クリックして**開始**します。