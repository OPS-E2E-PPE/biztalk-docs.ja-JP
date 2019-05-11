---
title: Database が失敗しましたからバッチの説明の読み取り |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f959aa35-d957-45b0-bfac-1134b5087d0c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca3eed2b26b01840104ba1219dd6acde7e2b0ae2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398287"
---
# <a name="reading-batch-descriptions-from-database-failed"></a>データベースからバッチの説明の読み取りに失敗しました
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                                 LoadBatchFiltersFailed                                 |
|  メッセージ テキスト   |     バッチの説明、データベースからの読み取りが失敗しました。 エラー:{0}します。 スタック トレース:{1}します。      |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server が構成されているバッチで受信メッセージのコンテキスト プロパティを比較する指定されたフィルターを読み込むことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、管理データベースが稼働して、接続できることを確認してください。