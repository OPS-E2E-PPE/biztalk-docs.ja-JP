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
ms.openlocfilehash: f7e539cbc4a8a7227815c7d836b61b028bcee2f5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990627"
---
# <a name="reading-batch-descriptions-from-database-failed"></a>データベースからのバッチの説明の読み取りが失敗しました
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                                 LoadBatchFiltersFailed                                 |
|  メッセージ テキスト   |     データベースからのバッチの説明の読み取りが失敗しました。 エラー:{0}します。 スタック トレース:{1}します。      |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server が、受信メッセージのコンテキスト プロパティを比較するために構成されたバッチ用に指定されたフィルターを読み込めなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、管理データベースが起動していて、接続できることを確認します。