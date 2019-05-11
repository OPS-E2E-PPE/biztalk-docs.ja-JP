---
title: 解析中に発生したエラーです。 X12 インターチェンジの機能グループが、次のエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2229c83-89bd-491f-9504-4afbf0084297
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ad6e795290ad6020d403eb1d1e5492633e4ed97
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348556"
---
# <a name="error-encountered-during-parsing-the-x12-functional-group-in-the-interchange-had-the-following-errors"></a>解析中に発生したエラーです。 X12 インターチェンジの機能グループには、次のエラーがありました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                             |
| 製品バージョン |                                                        [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                         |
|    イベント ID     |                                                                                     -                                                                                     |
|  イベント ソース   |                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                           |
|    コンポーネント    |                                                                                EDI エンジン                                                                                 |
|  シンボル名  |                                                                      X12FunctionalGroupReceiveError                                                                       |
|  メッセージ テキスト   | 解析中に発生したエラーです。 X12 機能グループ id '{0}'、id を持つインターチェンジ内で'{1}'、送信者 id '{2}'、受信者 id'{3}' 次のエラーが発生しました。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、EDI が受信することを示しますパイプライン、受信 X12 の解析中にエラーが発生しましたインターチェンジで識別された機能グループ、示されたエラーが原因です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用してグループのエラーを特定し、製品のヘルプで問題の解決方法を確認します。