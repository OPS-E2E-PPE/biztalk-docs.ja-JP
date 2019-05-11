---
title: 不明または無効なトランザクション セット制御番号 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6064b974-e8cd-4486-abc2-010afe0d956e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e247e75d7ac1f789ee3c1747e89c1f737c6d71cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394438"
---
# <a name="missing-or-invalid-transaction-set-control-number"></a>トランザクション セット制御番号が見つからないか無効です
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                    X12TsMissingOrInvalidTsControlNumberDescription                     |
|  メッセージ テキスト   |                   トランザクション セット制御番号が見つからないか無効です                    |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、トランザクション セット制御番号 (ST02 フィールド) が見つからないか無効な値であったため、受信または送信パイプラインでインターチェンジを処理できなかったことを示します。 トランザクション セット制御番号は英数字である必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
1.  各トランザクション セットにトランザクション セット制御番号があることを確認します。  
  
2.  各トランザクション セット制御番号が英数字であることを確認します。