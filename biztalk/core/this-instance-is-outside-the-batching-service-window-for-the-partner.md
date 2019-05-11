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
ms.openlocfilehash: bc0a60bf52b691795047175186f2707c6839981a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395445"
---
# <a name="this-instance-is-outside-the-batching-service-window-for-the-partner"></a>このインスタンスがパートナーの [Batching Service] ウィンドウの外側には
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                    バッチ処理エンジン                                     |
|  シンボル名  |                              OutsideBatchingServiceWindow                              |
|  メッセージ テキスト   |          このインスタンスがパートナーの [Batching Service] ウィンドウの外側には          |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、パーティのアクティベーションの範囲外のインスタンスであったためは、バッチ処理オーケストレーションのインスタンスを開始できませんでしたを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、パーティの EDI のプロパティの [インターチェンジのバッチ作成の設定] ページを開くし、オーケストレーション インスタンスがアクティベーションの範囲内であることを確認します。 そうでない場合、開始時間プロパティを変更し、クリックして**開始**します。