---
title: バッチ ID と関連付けられているアグリーメントが有効ではないか、または期限切れです。 バッチ処理を続行できません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d92cb07-7646-42b3-90a8-18acbcd145cd
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ace947d1c05774882b1e8f78f7b093f0795ba919
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018292"
---
# <a name="the-agreement-associated-with-batchid-is-not-enabled-or-has-expired-batching-cannot-continue"></a>バッチ ID と関連付けられているアグリーメントが有効ではないか、または期限切れです。 バッチ処理を続行できません
## <a name="details"></a>詳細  
  
|                 |                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------|
|  製品名   |         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
| 製品バージョン |                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                     |
|    イベント ID     |                                                 -                                                  |
|  イベント ソース   |       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI       |
|    コンポーネント    |                                             EDI エンジン                                             |
|  シンボル名  |                                    ErrorBatchAgreementDisabled                                     |
|  メッセージ テキスト   | バッチ Id に関連付けられているアグリーメント{0}が無効または有効期限が切れた。 バッチ処理を続行できません。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、アグリーメントが期限切れのために、BizTalk Server がバッチを開始できなかったか、またはバッチ メッセージを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、指定された ID のバッチが、親アグリーメントの [アグリーメント] プロパティに存在し、その開始日と終了日がアグリーメントの開始日と終了日の範囲内であることを確認します。 また、アグリーメントが有効になっていることを確認します。