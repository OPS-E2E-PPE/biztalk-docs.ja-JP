---
title: BizTalk ビジネス アクティビティの監視が構成されていない EDI AS2 状態レポート用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f46c1c8-2771-4b16-8fb1-71952792ac4a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58b6326829f6077b52acdca24d87b81acb3bc481
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349039"
---
# <a name="biztalk-business-activity-monitoring-has-not-been-configured-for-edi-as2-status-reporting"></a>BizTalk ビジネス アクティビティの監視が構成されていない EDI AS2 状態レポート用
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                              |
| 製品バージョン |                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                          |
|    イベント ID     |                                                                      -                                                                      |
|  イベント ソース   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                            |
|    コンポーネント    |                                                                 AS2 エンジン                                                                  |
|  シンボル名  |                                                                      -                                                                      |
|  メッセージ テキスト   | EDI および AS2 状態レポート用 BizTalk ビジネス アクティビティの監視が構成されていません。 そのため、状態レポート機能を無効化されます。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、EDI および AS2 状態レポートが無効である BizTalk 構成ウィザードを使ってビジネス アクティビティ監視 (BAM) が構成されていないためにことを示します。 BAM インフラストラクチャは、EDI および AS2 状態レポートの前提条件です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、BizTalk 構成ウィザードを実行し、ビジネス アクティビティの監視を構成します。