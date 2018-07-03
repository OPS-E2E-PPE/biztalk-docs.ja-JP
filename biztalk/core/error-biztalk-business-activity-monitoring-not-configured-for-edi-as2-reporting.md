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
ms.openlocfilehash: eb2a6b9d6eaa6ac14f51c7f05e40a9f6ccffccd5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010531"
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
 このエラー/警告/情報イベントは、ビジネス アクティビティの監視 (BAM) が BizTalk 構成ウィザードを使用して構成されていないため、EDI/AS2 状態レポート機能が有効になっていないことを示します。 EDI/AS2 状態レポート機能を使用するには BAM インフラストラクチャが必要です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、BizTalk 構成ウィザードを実行し、ビジネス アクティビティの監視を構成します。