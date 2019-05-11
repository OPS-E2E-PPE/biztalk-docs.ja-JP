---
title: 一致する変換見つかりません DocType 送信ポートで |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23f62ac7-3849-49fe-a765-2be72880a4c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd58b772afe9695d526038f622d968c75b75d252
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263391"
---
# <a name="no-matching-transform-found-for-doctype-in-send-port"></a>送信ポートで DocType の検出と一致するない変換
## <a name="details"></a>詳細  
  
|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  製品名   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| 製品バージョン |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    イベント ID     |                                                   -                                                    |
|  イベント ソース   |         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI         |
|    コンポーネント    |                                               EDI エンジン                                               |
|  シンボル名  |                             NoMatchingTransformFoundForSendPortAndDocType                              |
|  メッセージ テキスト   | Doctype と一致する変換が見つかりません{0}送信ポートで{1}します。 ExplorerOM の情報と一貫性がありません。 |
  
## <a name="explanation"></a>説明  
 このエラーは、指定された DocType および SendPort に一致する変換が見つからなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ように進めます。  
  
1.  BizTalk 管理コンソールを開き、トランスポートを特定トランスポート名を右クリックします。  
  
2.  **[プロパティ]** をクリックします。  
  
3.  ポートの種類の一覧で、適切なポートを選択します。 をクリックして**構成**です。  
  
4.  [ポート名] 送信ポートのプロパティ ダイアログ ボックスでをクリックして**送信マップ**左側のウィンドウでします。  
  
5.  マップがここに記載されていると、適切なドキュメントの種類に対応していることを確認します。