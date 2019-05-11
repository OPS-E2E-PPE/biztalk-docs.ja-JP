---
title: 解析中に発生したエラーです。 インターチェンジ内の Edifact 機能グループには、次のエラーが発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77ca78b3-8a1f-4da5-9c15-524ab6802457
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2b818d745366b84b41f1b44399fd699ebd68987
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389007"
---
# <a name="error-encountered-during-parsing-the-edifact-functional-group-in-interchange-had-the-following-errors"></a>解析中に発生したエラーです。 インターチェンジ内の Edifact 機能グループには、次のエラーが発生しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| 製品バージョン |                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    イベント ID     |                                                                                       -                                                                                       |
|  イベント ソース   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                             |
|    コンポーネント    |                                                                                  EDI エンジン                                                                                   |
|  シンボル名  |                                                                       EfactFunctionalGroupReceiveError                                                                        |
|  メッセージ テキスト   | 解析中に発生したエラーです。 Edifact 機能グループ id '{0}'、id を持つインターチェンジ内で'{1}'、送信者 id '{2}'、受信者 id'{3}' 次のエラーが発生しました。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントを示します、EDI 受信パイプラインでは、識別された機能グループで、示されたエラーのため、受信 EDIFACT インターチェンジの解析中にエラーが発生しました。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用してグループのエラーを特定し、製品のヘルプで問題の解決方法を確認します。